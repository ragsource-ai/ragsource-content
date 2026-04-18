---
titel: "Gefahrstoff-Einsatz (C-Einsatz): Handlungsanleitung"
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
  - Gefahrenabwehrrecht
stand: 2026-04-18
beschreibung: "Vollständige Handlungsanleitung für das LLM beim Chemikalien-Einsatz (C-Einsatz nach FwDV 500): Stoff-Identifikation, Gefahrengruppe, PSA-Auswahl, Einsatzbereiche, Grenzwertbeurteilung, Dekon-Stufen, Übergabe. Für brandmeister.ai — ab Phase G3 vollständig einsetzbar."
---

## Vor diesem Skill

Bevor du mit diesem Skill arbeitest, lade:
1. **SKILL_db_gefahrstoff_abfrage** — alle DB-Abfragemuster (im Catalog nach "Gefahrstoff-DB: Abfrage-Rezepte" suchen)
2. **D_FwDV_500_ABC_Einsatz** — Verfahrenstext bei spezifischen Rückfragen:
   ```json
   RAGSource_get({
     "source": "D_FwDV_500_ABC_Einsatz",
     "sections": [
       "1.5.3.2 Erstmaßnahmen (GAMS-Regel)",
       "4.1 Einteilung in Gefahrengruppen (C-Einsatz)",
       "1.3.1.2 Schutzkleidung (Formen 1–3)",
       "1.5.3.5 Gefahren-, Absperr- und Übergangsbereich",
       "1.5.3.6 Dekontamination"
     ]
   })
   ```
3. Erst dann: Nutzeranfrage beantworten.

## Inhaltsverzeichnis
- erstmassnahmen [GAMS-Regel + Informationsstufen 1–4]
- stoff_identifizieren [UN bekannt / Stoffname bekannt / Stoff unbekannt]
- gefahrengruppe [C-Gefahrengruppe I / II / III bestimmen]
- psa_auswahl [Schutzkleidung Form 1 / 2 / 3 entscheiden]
- einsatzbereiche [Gefahren- / Übergangs- / Absperrbereich einrichten]
- grenzwert_beurteilung [ETW / AEGL-2 / AGW — Beurteilungswert-Hierarchie]
- dekon [Dekon-Stufe I / II / III — Auswahl und Fristen]
- uebergabe [Übergabe an Behörde, AwSV-Pflichten, WGK-Meldung]
- nachsorge [Registrierung, ärztliche Überwachung]

---

### erstmassnahmen
**GAMS-Regel** (FwDV 500 § 1.5.3.2) — Erstmaßnahmen jeder Einsatzkraft ohne Sonderausrüstung:

```
G — Gefahr erkennen     (Gefahrguttafel, GHS-Piktogramme, Kennzeichnung lesen)
A — Absperren           (Gefahrenbereich vorläufig 50 m, Windrichtung beachten)
M — Menschenrettung     (Mindest-PSA: Form 1 + Isoliergerät)
S — Spezialkräfte alarmieren (ABC-Zug, Leitstelle, ggf. TUIS/ATF)
```

Gleichzeitig: Sofort-Dekon einrichten (→ dekon), Brandschutz sicherstellen.

**Informationsstufen** (Verfahren nach FwDV 500 § 1.5.1 i.V.m. vfdb-Richtlinie 10/05):

| Stufe | Quelle | Maßnahme |
|---|---|---|
| 1 | Sofortinformation | Gefahrzettel, Gefahrguttafel lesen (Klasse + UN-Nr) |
| 2 | Kurzinformation | Begleitpapiere, Sicherheitsdatenblatt, ERI-Cards |
| 3 | Detaillierte Information | DB-Abfrage (→ stoff_identifizieren), Nachschlagewerke |
| 4 | Experteninformation | ATF, TUIS-Notruf, BAM +49 30 18 455 5000 |

**Fahrzeugaufstellung** (FwDV 500 § 1.5.3.1):
- Mit dem Wind anfahren, Fahrzeuge nicht in Senken oder im Gefahrenbereich
- Mindestabstand 50 m zum gemeldeten Objekt bei unklarer Lage
- Fahrzeuge im Gefahrenbereich gelten als kontaminiert — nicht wegfahren

---

### stoff_identifizieren

**a) UN-Nummer bekannt** (z.B. auf oranger Gefahrguttafel, Begleitpapieren):
- UN normalisieren: 4-stellig, kein Präfix
- DB-Abfrage → SKILL_db_gefahrstoff_abfrage § un_suche
- Lesen: `bam_klasse`, `bam_vpgruppe`, `bam_gefahrnr`, `rigoletto_wgk`, `pubchem_ghs_hazards`

Die **Gefahrnummer** (obere Zahl auf ADR-Tafel) gibt Ersthinweis: 33=entzündbar+leichtflüchtig, 66=sehr toxisch, 80=ätzend, 90=umweltgefährlich.

**b) Stoffname oder CAS bekannt**:
- DB-Abfrage → SKILL_db_gefahrstoff_abfrage § stoffname_suche
- Bei Benzin, Diesel, Heizöl: BAM-Einträge ohne CAS (Gemische) → BAM:{bamnr} als Schlüssel

**c) Stoff unbekannt**:
1. GHS-Piktogramme auf Behälter/Transportdokument auswerten:
   - Flamme → entzündbar (ADR-Klasse 3, 2.1)
   - Totenkopf → akut toxisch
   - Ausrufezeichen → gesundheitsschädlich / reizend
   - Ätzwirkung → korrosiv (ADR-Klasse 8)
   - Umwelt → wassergefährdend (WGK beachten → Worst-Case: WGK 3)
   - Gas unter Druck → Druckgas (ADR-Klasse 2)
   - Explodierende Bombe → explosiv (ADR-Klasse 1)
2. Bis zur Identifikation: Worst-Case-Annahmen (GG IIC, WGK 3, Form 2 PSA)
3. Leitstelle für Parallelrecherche einbinden (Informationsstufe 4)

---

### gefahrengruppe
**C-Gefahrengruppe bestimmen** (FwDV 500 § 4.1):

```
Gefahrengruppe IC:
- Haushaltschemikalien ≤ 1.000 kg, keine besonderen Gefahren
- Verpackungsgruppe III (geringe Gefahr) nach ADR/GGVSEB

Gefahrengruppe IIC:
- C-Gefahrstoffe > 1.000 kg
- Verpackungsgruppe II (mittlere Gefahr)
- Industriechemikalien in laborüblichen Mengen
- Schwimmbäder mit Chloranlage, Kühlanlagen mit Ammoniak

Gefahrengruppe IIIC:
- Verpackungsgruppe I (hohe Gefahr)
- Betriebsbereiche nach 12. BImSchV (Störfall-Verordnung)
- Sprengstoffe, militärische Munition/Kampfstoffe
- Sehr große Mengen gefährlicher Chemikalien

Transporte: immer mindestens GG IIC — Mengen oft sehr groß!
Anschlag / vorsätzliche Freisetzung: immer GG IIIC.
```

VpGr aus `bam_vpgruppe`-Spalte lesen (I=hoch, II=mittel, III=gering).
Bei mehreren Einflussgrößen: höchste Gefahrengruppe gilt.

> Hinweis: Bereiche der GG IIIC mit militärischer Munition/Kampfstoffen dürfen auch zur Menschenrettung NICHT ohne sachkundigen Militärangehörigen betreten werden (FwDV 500 § 4.4.2.5).

---

### psa_auswahl
**PSA-Form wählen** (FwDV 500 § 1.3.1.2):

| Situation | PSA-Form |
|---|---|
| Menschenrettung (Minimum) | Form 1 + Isoliergerät |
| Bekannte Gefahrenlage GG IC, kein Gaskontakt | Form 1 |
| Standard C-Einsatz GG IIC / unbekannte Lage | Form 2 |
| GG IIIC / Gas-/Dampfexposition möglich / unbekannter Stoff | Form 3 |
| Erkundung ohne ausreichende Erkenntnisse | Form 3 |

**Form 1**: Brandschutzbekleidung + Schutzhaube — schützt nur vor festen ABC-Gefahrstoffen, kein Spritzschutz.
**Form 2**: Schutzanzug — schützt vor festen und begrenzt flüssigen Gefahrstoffen, NICHT gasdicht.
**Form 3**: Vollständiger Chemikalienschutzanzug — schützt vor festen, flüssigen und gasförmigen Gefahrstoffen; Isoliergerät max. 30 min unter Schutzanzug.

Am Dekon-Platz: Form 2 als Einmalschutzanzug + Kombinationsfilter ABEK2-P3.

**Hautresorption prüfen**: `trgs900_art`-Spalte enthält "H" bei Hautresorption → Form 2 Mindestanforderung auch bei gasförmigem Stoff.

---

### einsatzbereiche
**Drei Bereiche einrichten** (FwDV 500 § 1.5.3.5):

```
Windrichtung →
┌──────────────── ABSPERRBEREICH (grün) — min. 100 m ────────────────┐
│    ┌──────────── ÜBERGANGSBEREICH (gelb) — min. 50 m ─────────────┐ │
│    │    ┌──────── GEFAHRENBEREICH (rot) — min. 50 m ─────────┐   │ │
│    │    │              • Schadenobjekt                        │   │ │
│    │    └─────────────────────────────────────────────────────┘   │ │
│    └──────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────┘
         Dekon-Platz: windzugewandt, außerhalb Gefahrenbereich
```

**Gefahrenbereich (rot)**: Zutritt nur mit geeigneter PSA. Markieren + sichern durch Feuerwehr.
**Übergangsbereich (gelb)**: Zutritt für Einsatz-/Unterstützungskräfte + zu dekontaminierende Personen.
**Absperrbereich (grün)**: Zutritt nur für erforderliche Kräfte. Sichern mit Polizei abstimmen.

Rauchen, Essen, Trinken im Gefahren- und Übergangsbereich verboten.

**Sonderfall Explosivstoffe / druckverflüssigte Gase unter Brandeinwirkung** (GG IIIC):
Gefahrenbereich **500 m**, Absperrbereich **1.000 m** — erst nach Erkundung verkleinern.

**4A-Regel** (FwDV 500 Anlage 2 — für alle Einsatzkräfte):
- **Abstand** halten — je größer der Abstand, desto geringer Konzentration
- **Aufenthaltsdauer** begrenzen — Penetration/Permeation steigt mit Zeit
- **Abschirmung** nutzen — massive Deckungen reduzieren Konzentration
- **Abschalten** — Anlagen/Behälter sichern/schließen soweit möglich und sinnvoll

---

### grenzwert_beurteilung
**Beurteilungswert-Hierarchie** (FwDV 500 § 1.5.2) für C-Gefahrstoffe:

1. **ETW** (Einsatztoleranzwert, vfdb-Richtlinie 10/01) — primär für Einsatzkräfte
2. **AEGL-2** für 4h-Exposition — Schwellenwert für irreversible Schäden
3. **AGW** (TRGS 900, 8h-TWA) — als untere Orientierung, Arbeitsplatzkonzept

Immer ALARA-Prinzip: so niedrig wie vernünftigerweise erreichbar.

**AGW aus DB lesen** (→ SKILL_db_gefahrstoff_abfrage § agw_spalten):
- `trgs900_agw_ppm` und `trgs900_agw_mg_m3` — deutscher Rechtsgrenzwert
- `pubchem_idlh` — US-NIOSH IDLH (Lebensgefahr-Schwellenwert), guter Vergleichswert
- Präfix `pubchem_` = US-Wert; nicht rechtsverbindlich in DE, aber einsatzpraktisch relevant

**Wenn keine Messung möglich**: Worst-Case-PSA (Form 3) bis Messung verfügbar.
Nachweisgeräte-Reihenfolge: Gaswarngerät / Ex-Schutz → Mehrgaswarngerät → Prüfröhrchen → PID.

---

### dekon
**Dekon-Pflicht**: Ab GG IIC ist eine Dekontamination durchzuführen. Einsatzkräfte werden vor Betreten des Gefahrenbereichs registriert.

**Dekon-Stufen** (FwDV 500 § 1.5.3.6 + Anlage 3):

**Stufe I — Sofort-Dekon** (zeitgleich mit erstem Trupp einrichten!):
- Bei PSA-Schaden, Hautkontamination, Atemluftmangel, Verletzung
- Nicht an Dekon-Platz gebunden — Ort danach als kontaminiert absperren
- C-Einsatz: kontaminierte Hautstellen sofort mit Wasser abspülen (nicht abreiben!)

**Stufe II — Standard-Dekon** (spätestens 15 min nach erstem PSA-Anlegen):
- Pflicht bei jedem ABC-Einsatz unter PSA
- Dekon-Platz windzugewandt außerhalb Gefahrenbereich
- C-Einsatz: Dekon mit Wasser + ggf. Hilfsmitteln, Reinigungsflüssigkeit auffangen
- Dekon P (Einsatzkräfte mit intakter PSA) vs. Dekon V (Verletzte, beschädigte PSA)
- Nach Dekon: PSA und Geräte ablegen, bei GG IIC Hände/Gesicht/Haare reinigen

**Stufe III — Erweiterte Dekon** (lagebezogen, unverzüglich alarmieren wenn erforderlich):
- Viele zu dekontaminierende Personen, liegende Verletzte, spezielle Stoffe
- Warmduschen nach GG IIC/IIIC-Einsatz, Zelt-Umkleide
- Sanitäts- und Fachkräfte (V-Dekon), Abwassermengen auffangen

**Grundsatz**: Lebensrettende Sofortmaßnahmen gehen vor Dekon — dabei Eigenschutz beachten.
Wer Verdacht auf Kontamination oder Inkorporation hat: Arzt aufsuchen, Registrierung sicherstellen.

**C-spezifisch GG IIC/IIIC**: Alle Personen aus diesen Bereichen gelten als kontaminiert bis zur fachgerechten Reinigung + Bestätigung durch sachkundige Person.

---

### uebergabe
**Grundsatz** (FwDV 500 § 1.5.3.8): Der Gefahrenbereich wird bei ABC-Einsätzen NICHT von der Feuerwehr freigegeben — immer Übergabe an die zuständige Behörde.

**Zuständige Behörde** je nach Schadensart:
- Umweltbehörde (Gewässerschutz, Bodenkontamination → AwSV)
- Gesundheitsbehörde (Kontamination/Vergiftungen)
- Straßenbaulastträger (Transportunfall)

**WGK-Pflichten aus AwSV ableiten**:
1. WGK aus Stoff-Profil lesen: `rigoletto_wgk` (0–3)
2. Übergabe-Regeln abfragen (→ SKILL_db_gefahrstoff_abfrage § uebergabe_abrufen)
3. Bei Treffer: `kanalisation_freigabe`, `benachrichtigung_pflicht`, `avv_schluessel_primaer` lesen
4. Bei Phase G4 (noch nicht vollständig befüllt): AwSV §§ 24, 25 direkt abrufen

**Löschwasserrückhaltung** (FwDV 500 § 1.5.3.4): Wenn Abwasser kontaminiert sein könnte → Ausbreitung verhindern, Behörde informieren.

**Übergabe-Checkliste**:
```
☐ Stoff: Bezeichnung, UN-Nr, CAS, WGK, ADR-Klasse
☐ Menge/Leckrate abgeschätzt
☐ Gefahrenbereich markiert und gesichert
☐ Kanalisation: gesperrt / freigegeben
☐ Löschwasser: zurückgehalten / unkontrolliert
☐ Behörde verständigt: [Umwelt / Gesundheit / Ordnung]
☐ Rechtsgrundlage: [AwSV §, WHG §]
☐ Übergabe an: [Behördenvertreter Name/Stelle]
```

---

### nachsorge
**Registrierung und ärztliche Überwachung** (FwDV 500 § 4.4.3):

Bei Einsätzen in GG IIC oder IIIC: alle Einsatzkräfte namentlich erfassen.

Sofort zum Arzt bei:
- Nachgewiesener oder vermuteter Kontamination (PSA-Schaden, undichter Atemanschluss)
- Inkorporationsverdacht
- Verletzungen
- Einsatz mit sensibilisierenden, krebserregenden oder erbgutverändernden Stoffen

Information an den Rettungsdienst bei kontaminierten Personen:
- Art und vermuteter Stoff
- Grad der Kontamination, betroffene Flächen
- Dauer der Einwirkung
- Bisherige Dekon-Maßnahmen und Erfolg

Späterkrankungen im Zusammenhang mit dem Einsatz: alle Beteiligten erneut zum Arzt.
Dokumentation für Unfallkasse (DGUV) sicherstellen.
