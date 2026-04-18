---
titel: "Gefahrstoff-DB: Abfrage-Rezepte"
typ: skill
ebene:
saule: 2
land_ars:
kreis_ars:
verband_ars:
gemeinde_ars:
land:
kreis:
verband:
gemeinde:
endpoints:
  - brandmeister
extensions:
  - Feuerwehr
  - Gefahrgut
stand: 2026-04-18
beschreibung: "Zentrale Abfrage-Rezepte für RAGSource_db_query auf db_gefahrstoff, db_stoff_aliases und db_uebergabe_regeln. Zuerst laden wenn Stoff- oder Übergabe-Daten benötigt werden — verhindert doppelte Abfragelogik in anderen Skills."
---

## Inhaltsverzeichnis
- un_suche [UN-Nummer → Stoff-Profil aus db_gefahrstoff]
- cas_suche [CAS-Nummer → Stoff-Profil]
- stoffname_suche [Freitext → Alias-Lookup → Profil]
- wgk_filter [Stoffe einer WGK abfragen]
- agw_spalten [AGW/IDLH/Grenzwerte aus Profil lesen]
- uebergabe_abrufen [WGK × Stoffklasse → Übergabe-Regeln]
- ergebnis_lesen [Spalten-Bedeutung, Einheiten, Quell-Attribution]

### un_suche
UN-Nummer normalisieren: 4-stellig, kein "UN"-Präfix.

```json
RAGSource_db_query({
  "db": "gefahrstoff",
  "filter": { "un_nr": "1203" }
})
```

Mehrere Treffer = mehrere Packungsvarianten oder Aggregatzustände (alle aufführen).
Bei 0 Treffern: UN-Nummer per Alias-Lookup prüfen (→ stoffname_suche Schritt 1).

### cas_suche
CAS exakt mit Bindestrichen:

```json
RAGSource_db_query({
  "db": "gefahrstoff",
  "filter": { "cas": "67-56-1" }
})
```

### stoffname_suche
**Schritt 1** — Alias-Lookup (alias_norm ist lowercase, Umlaute ae/oe/ue/ss):

```json
RAGSource_db_query({
  "db": "stoff_aliases",
  "filter": { "alias_norm_like": "benzin" }
})
```

Liefert `cas` (echter CAS-String) oder `BAM:{bamnr}` (Gemisch ohne CAS).

**Schritt 2** — Stoff-Profil:
- Echter CAS → `cas_suche`
- `BAM:{bamnr}` → `RAGSource_db_query({ "db": "gefahrstoff", "filter": { "cas": "BAM:12345" } })`

Kein Alias-Treffer → Freitext-Suche in Hauptbezeichnung:

```json
RAGSource_db_query({
  "db": "gefahrstoff",
  "filter": { "bezeichnung_de_like": "methanol" }
})
```

OR-Suche über mehrere mögliche Bezeichnungen:

```json
RAGSource_db_query({
  "db": "gefahrstoff",
  "any_of": [
    { "bezeichnung_de_like": "aceton" },
    { "bezeichnung_en_like": "acetone" }
  ]
})
```

### wgk_filter
Alle Stoffe einer Wassergefährdungsklasse (für Worst-Case oder Übersicht):

```json
RAGSource_db_query({
  "db": "gefahrstoff",
  "filter": { "rigoletto_wgk": 3 }
})
```

WGK-Werte (Rigoletto/UBA): 0 = nwg (nicht wassergefährdend), 1 = schwach, 2 = deutlich, 3 = stark wassergefährdend.

### agw_spalten
AGW und Grenzwerte sind im Stoff-Profil enthalten (kein separater Query).
Aus dem Ergebnis von `un_suche` oder `cas_suche` lesen:

| Spalte | Inhalt | Quelle |
|---|---|---|
| `trgs900_agw_ppm` | Arbeitsplatzgrenzwert in ppm (8h-TWA) | BAuA TRGS 900 |
| `trgs900_agw_mg_m3` | AGW in mg/m³ | BAuA TRGS 900 |
| `trgs900_art` | Bemerkungen: H=Hautresorption, Y=Spitzenbegrenzt, EU=EU-Bindewert | BAuA TRGS 900 |
| `pubchem_idlh` | IDLH (Immediately Dangerous to Life/Health) als String mit Einheit | NIOSH via PubChem |
| `pubchem_niosh_rel_twa` | NIOSH REL TWA (US-Wert) | NIOSH via PubChem |
| `pubchem_niosh_rel_stel` | NIOSH REL STEL (US-Kurzzeit) | NIOSH via PubChem |
| `pubchem_osha_pel` | OSHA PEL (US-Wert) | NIOSH via PubChem |
| `pubchem_ghs_signal` | "Danger" oder "Warning" (GHS-Signalwort) | NIH PubChem |
| `pubchem_ghs_hazards` | H-Codes kommagetrennt (z.B. "H225,H301,H311") | NIH PubChem |

NULL bedeutet: Quelle hat keinen Eintrag — nicht: Stoff ist unbedenklich.

### uebergabe_abrufen
Übergabe-Regeln nach WGK und ADR-Stoffklasse (bam_klasse-Wert aus Stoff-Profil):

```json
RAGSource_db_query({
  "db": "uebergabe_regeln",
  "filter": { "wgk": 2, "stoffklasse": "3" }
})
```

**Phase G4 — Tabelle noch nicht vollständig befüllt.** Bei 0 Treffern:
Übergabe-Regeln aus AwSV §§ 24, 25 und WHG § 32 ableiten:
```json
RAGSource_get({ "source": "D_AwSV", "sections": ["§ 24", "§ 25"] })
```

Tabellen-Spalten bei Treffer:
- `kanalisation_freigabe`: "nein" | "nur nach UWB-Freigabe" | "bedingt" | "ja"
- `kanalisation_bedingungen`: Freitext-Bedingungen
- `avv_schluessel_primaer`: AVV-Schlüssel 6-stellig (z.B. "130701")
- `entsorgungspfad`: Freitext Entsorgungsweg
- `benachrichtigung_pflicht`: JSON-Array von Behörden/Stellen
- `benachrichtigung_schwelle_liter`: Mengenschwelle für Meldepflicht
- `rechtsgrundlage_source_id`: z.B. "D_AwSV"
- `rechtsgrundlage_section_ref`: z.B. "§ 24 Abs. 1"

### ergebnis_lesen
**Quell-Attribution** — Präfix zeigt die Datenquelle:
- `bam_*` — BAM Datenbank Gefahrgut (Bundesanstalt für Materialforschung, ADR-Transportrecht, ~2-Jahres-Zyklus)
- `rigoletto_*` — UBA Rigoletto (Wassergefährdungsklassen nach AwSV § 66, fortlaufend)
- `trgs900_*` — BAuA TRGS 900 (Arbeitsplatzgrenzwerte, deutsches Recht, 1–2×/Jahr)
- `pubchem_*` — NIH PubChem / NIOSH LCSS (US-Grenzwerte und GHS-Daten, gemeinfrei)
- `erg_*` — ERG 2024 (Phase G5, noch nicht importiert → NULL)

**Widersprüche** zwischen Quellen werden nicht aufgelöst — alle Werte separat nennen.

**Gemische ohne CAS** (z.B. Benzin, Dieselkraftstoff): Primärschlüssel ist `BAM:{bamnr}`, CAS-Spalte enthält diesen synthetischen Schlüssel. Rigoletto-/PubChem-/TRGS-Daten sind bei diesen Einträgen NULL.

**Mehrere Treffer bei UN-Suche** sind Normalfall (verschiedene Packungsgruppen, Aggregatzustände, Handelsvarianten). Alle Treffer aufführen.
