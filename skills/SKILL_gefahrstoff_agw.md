---
titel: "Gefahrstoff-Grenzwerte: AGW / IDLH / ETW"
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
  - Arbeitsrecht
stand: 2026-04-18
beschreibung: "Grenzwert-Beurteilung für C-Einsätze: AGW (TRGS 900), IDLH (NIOSH), ETW/AEGL-2 Hierarchie, PSA-Entscheidung aus Grenzwert-Vergleich. Für brandmeister.ai — ergänzendes Skill zu SKILL_gefahrstoff_einsatz."
---

## Vor diesem Skill
1. Stoff-Profil via `RAGSource_db_query` laden (→ SKILL_db_gefahrstoff_abfrage § agw_spalten)
2. Bei detaillierten TRGS-900-Fragen: `RAGSource_get({ "source": "D_TRGS_900" })` — falls Volltext nötig

## Inhaltsverzeichnis
- grenzwert_hierarchie [Welcher Wert gilt wann — Rangfolge]
- agw_lesen [AGW-Wert aus DB interpretieren]
- idlh_lesen [IDLH aus DB interpretieren]
- psa_entscheidung [Grenzwert → PSA-Form-Empfehlung]
- fehlender_wert [Was tun wenn kein Grenzwert in DB]

### grenzwert_hierarchie
**Beurteilungswerte für C-Gefahrstoffe im Einsatz** (FwDV 500 § 1.5.2):

| Rang | Wert | Bedeutung | In DB |
|---|---|---|---|
| 1 | ETW | Einsatztoleranzwert (vfdb 10/01) — primär für Einsatzkräfte | nicht in DB |
| 2 | AEGL-2 | Störfall-Konzentrationsleitwert für 4h — irreversible Schäden | nicht in DB |
| 3 | AGW | Arbeitsplatzgrenzwert (TRGS 900, 8h-TWA) — untere Orientierung | `trgs900_agw_ppm` |
| — | IDLH | Immediately Dangerous to Life/Health (NIOSH, US) | `pubchem_idlh` |

**ALARA-Prinzip**: Stets so niedrig wie vernünftigerweise erreichbar, unabhängig vom Grenzwert.

ETW und AEGL-2 sind nicht in der DB — bei Bedarf: vfdb-Richtlinie 10/01 oder CAMEO/NOAA-Datenbank heranziehen, Leitstelle einbinden (Informationsstufe 4).

### agw_lesen
AGW (Arbeitsplatzgrenzwert) aus Stoff-Profil:
- `trgs900_agw_ppm`: ppm v/v, 8h-Schichtmittelwert
- `trgs900_agw_mg_m3`: mg/m³, 8h-Schichtmittelwert
- `trgs900_art`: Sonderbemerkungen:
  - **H** = Hautresorption möglich → Form 2 PSA auch bei gas-/dampfförmigem Stoff
  - **Y** = Spitzenbegrenzt → kein Kurzzeitüberschreitungsfaktor erlaubt
  - **EU** = EU-verbindlicher Bindewert

Der AGW ist der **Arbeitsschutz-Grenzwert** für 8h-Tagesexposition — kein Einsatz-Grenzwert. Im Feuerwehreinsatz (typisch < 1h) kann ein höherer Wert als der AGW tolerierbar sein, ETW/AEGL-2 ist der korrekte Maßstab. AGW dient als untere Orientierung: wenn Konzentration < AGW → kein unmittelbares Risiko.

**Einsatz-Kontext**: TRGS 900 gilt für Arbeitnehmer unter GefStoffV. FwDV 500 erklärt C-Einsatz der Feuerwehr für gleichwertig zu GefStoffV-Anforderungen (FwDV 500 Einleitung).

### idlh_lesen
IDLH (Immediately Dangerous to Life or Health) aus `pubchem_idlh`:
- NIOSH-Wert, US-Recht — nicht rechtsverbindlich in DE
- String mit Einheit (z.B. "2 ppm", "50 mg/m³"), bei "Ca." = krebsverdächtig (Kanzerogenität)
- IDLH = Konzentration bei 30min-Exposition ohne PSA ohne irreversiblen Schaden

Verwendung im Einsatz:
- Wenn Messung > IDLH → Gefahrenbereich sofort evakuieren, Form 3 PSA Pflicht
- Wenn kein ETW/AEGL vorhanden und Messung < IDLH: Form 2 kann ausreichen

NULL bei `pubchem_idlh` = kein NIOSH-Wert für diesen Stoff (nicht: sicher).

### psa_entscheidung
**PSA aus Grenzwertvergleich** (zusammen mit FwDV 500 § 1.3.1.2 — Form-Definitionen dort nachlesen):

| Messlage | Empfehlung |
|---|---|
| Konzentration > IDLH | Form 3 + vollständige Isolation |
| Konzentration im IDLH-Bereich oder ETW-Bereich | Form 3 |
| Konzentration zwischen AGW und IDLH | Form 2 (mind.) |
| Konzentration < AGW, kein Hautresorptions-H | Form 1 oder Form 2 |
| Keine Messung, unbekannter Stoff | Form 3 (Worst-Case) |
| GG IIIC / Erkundung ohne Erkenntnisse | Form 3 |

Bei **H-Kennzeichnung** in `trgs900_art`: immer Form 2 oder Form 3, unabhängig von Konzentration.

Isoliergerät unter Form-3-Anzug: maximal 30 Minuten Einsatzdauer (FwDV 500 § 1.3.1.1).

### fehlender_wert
Wenn kein AGW/IDLH in DB (alle Spalten NULL):

1. GHS-Signalwort prüfen: `pubchem_ghs_signal` = "Danger" → erhöhte Vorsicht, Form 2 Minimum
2. H-Codes prüfen: `pubchem_ghs_hazards` auswerten
   - H200-H299 = physikalische Gefahr (Explosiv/Entzündlich)
   - H300-H399 = Gesundheitsgefahr (akut toxisch, ätzend, sensibilisierend...)
   - H400-H499 = Umweltgefahr (WGK-relevant)
   - H330, H331 = Inhalationstoxizität → Form 2 Minimum, bei H330 Form 3
3. Wenn auch keine GHS-Daten: Worst-Case-Annahme Form 3, Experten einbinden (Stufe 4)
4. Relevante Quellen: vfdb-Richtlinie 10/01 (ETW-Liste), AEGL-Datenbank (EPA), TUIS-System
