---
titel: "Arbeitsschutz Feuerwehr: UVV / PSA / ArbSchG"
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
  - Arbeitsrecht
stand: 2026-04-18
beschreibung: "Handlungsanleitung für Arbeitsschutz-Fragen der Feuerwehr: UVV DGUV, PSA-Pflichten, Gefährdungsbeurteilung, GefStoffV, BetrSichV, Einsatz-Nachsorge. Workflow zur Quellen-Navigation im Catalog."
---

## Vor diesem Skill
Catalog laden um verfügbare Arbeitsschutz-Quellen zu sehen:
```json
RAGSource_catalog()
```
→ Quellen mit `extensions: Arbeitsrecht` identifizieren (ArbSchG, BetrSichV, GefStoffV, DGUV-Vorschriften).

## Inhaltsverzeichnis
- rechtsquellen [Überblick: Welche Gesetze für Feuerwehr-Arbeitsschutz]
- psa_pflichten [PSA-Auswahl-Pflichten nach GefStoffV / DGUV]
- gefaehrdungsbeurteilung [GB-Pflicht, Dokumentation, Atemschutzeignung]
- gefahrstoff_bezug [GefStoffV ↔ FwDV 500 — Gleichwertigkeits-Klausel]
- nachsorge_medizin [Ärztliche Vorsorge, G-Untersuchungen, DGUV-Meldung]
- quellen_abrufen [Workflow Catalog → Get für konkrete Paragraphen]

### rechtsquellen
**Arbeitsschutz-Rechtsquellen für Feuerwehren**:

| Rechtsquelle | Inhalt | Bindewirkung |
|---|---|---|
| ArbSchG | Grundpflichten Arbeitgeber/Arbeitnehmer, GB-Pflicht | Bundesrecht |
| GefStoffV | Gefährliche Stoffe im Betrieb, Grenzwerte, PSA | Bundesrecht |
| BetrSichV | Betriebssicherheit, Schutzausrüstung, Prüfpflichten | Bundesrecht |
| DGUV Vorschrift 1 | Grundsätze der Prävention (ehem. BGV A1) | UVV |
| DGUV Vorschrift 49 | Feuerwehren — speziell für hauptamtliche FW | UVV |
| DGUV Information 205-010 | Einsatz bei ABC-Gefahren | Information/Empfehlung |
| DGUV Information 213-850 | Laboratorien (relevant für IIIC-Bereiche) | Information/Empfehlung |
| FwDV 7 | Atemschutz — Grundlage für Atemschutzüberwachung | DV |
| FwDV 500 Teil I | Gleichwertigkeit ABC-Einsatz ↔ GefStoffV | DV |
| TRGS 900 | Arbeitsplatzgrenzwerte Chemikalien | Technische Regel |

Catalog-Suche nach konkreter Quelle:
```json
RAGSource_catalog()
```
→ Einträge mit `extensions: Arbeitsrecht` oder `extensions: Feuerwehr` prüfen.

### psa_pflichten
**Pflicht zur PSA-Bereitstellung** (ArbSchG § 3 Abs. 1, GefStoffV § 10):

Der Träger der Feuerwehr (Arbeitgeber/Unternehmer) ist verantwortlich für:
- Bereitstellung geeigneter PSA (DGUV Vorschrift 1 § 29)
- Funktionsfähigkeit und Prüfung der PSA
- Unterweisung der Einsatzkräfte

Der Einsatzleiter ist verantwortlich für:
- Auswahl der geeigneten PSA je Lage (FwDV 500 § 1.3.1)
- Einhaltung der Schutzmaßnahmen im Einsatz

**PSA-Klassen-Entscheidung im C-Einsatz**: → SKILL_gefahrstoff_einsatz § psa_auswahl oder SKILL_gefahrstoff_agw § psa_entscheidung

**Kontrolle der Schutzkleidung**: Vor Einsatz auf Beschädigungen prüfen (perforierte oder kontaminierte PSA = Dekon V-Fall).

### gefaehrdungsbeurteilung
**Gefährdungsbeurteilung** (ArbSchG § 5, GefStoffV § 6) — Pflicht des Trägers der Feuerwehr:

Für Einsatzbereiche nach GefStoffV sind zu dokumentieren:
- Art, Ausmaß und Dauer der Exposition
- Tätigkeitsbeschreibung und betroffene Bereiche
- Schutzmaßnahmen und deren Wirksamkeit
- Ergebnis der Substitutionsprüfung (bei GefStoffV)

**Atemschutzeignung** (FwDV 7): Alle Atemschutzgeräteträger müssen arbeitsmedizinisch untersucht sein:
- G 26.1: Beurteilung für leichte Atemschutzgeräte
- G 26.2: Beurteilung für mittlere Atemschutzgeräte
- G 26.3: Beurteilung für schwere Atemschutzgeräte (Isoliergeräte)

Atemschutzüberwachung im Einsatz: mindestens ein Sicherheitstrupp, Eintrittszeitpunkt und Luftvorrat registrieren (FwDV 7).

### gefahrstoff_bezug
**Gleichwertigkeits-Klausel FwDV 500** (FwDV 500, Einleitung):

FwDV 500 erklärt den ABC-Einsatz für gleichwertig zu den Anforderungen der Gefahrstoffverordnung (GefStoffV). Feuerwehren, die nach FwDV 500 handeln, erfüllen damit GefStoffV-Anforderungen.

Dies bedeutet konkret:
- TRGS 900 AGW-Werte als Beurteilungsmaßstab (→ SKILL_gefahrstoff_agw)
- PSA-Auswahl nach FwDV 500 §§ 1.3.1.2 und 4.4 erfüllt GefStoffV § 10
- Registrierung und Nachsorge nach FwDV 500 § 4.4.3 erfüllt DGUV-Anforderungen

Rechtstext prüfen:
```json
RAGSource_get({ "source": "D_FwDV_500_ABC_Einsatz", "sections": ["Teil I – Rahmenrichtlinien"] })
```
(Gleichwertigkeitsklausel steht in der Einleitung / Präambel von Teil I)

### nachsorge_medizin
**Arbeitsmedizinische Vorsorge** nach DGUV und GefStoffV:

**Pflichtvorsorge** (DGUV Vorschrift 49 + GefStoffV § 15a):
- G 26.3 Atemschutz (alle Atemschutzgeräteträger)
- G 30 Hitzearbeit (bei heißen Schadenslagen)
- G 37 Bildschirmarbeit (für Disponenten)

**Anlassvorsorge nach Einsatz** (ArbMedVV § 4 Abs. 3):
- Nach Exposition gegenüber krebserzeugenden oder erbgutverändernden Stoffen
- Nach Kontamination oder Inkorporations-Verdacht
- Auf Wunsch des Beschäftigten nach besonders belastendem Einsatz

**DGUV-Meldung bei Unfall/Erkrankung**: Unfälle im Einsatz oder Berufskrankheitsverdacht → Meldung an zuständige Unfallkasse (in BW: Kommunale Unfallversicherung Bayern/BW oder Feuerwehr-Unfallkasse je nach Bundesland).

Registrierung nach FwDV 500 § 4.4.3 (→ SKILL_gefahrstoff_einsatz § nachsorge) sicherstellen — Grundlage für spätere DGUV-Meldung.

### quellen_abrufen
**Workflow für konkrete Paragraphen-Fragen**:

1. Catalog → Quelle identifizieren
```json
RAGSource_catalog()
```
2. TOC wenn Quelle groß oder Abschnitt unbekannt
```json
RAGSource_toc({ "source": "D_ArbSchG" })
```
3. Gezielt laden
```json
RAGSource_get({ "source": "D_ArbSchG", "sections": ["§ 5 Beurteilung der Arbeitsbedingungen"] })
```

**Häufig benötigte Quellen** (Catalog-IDs variieren, immer per Catalog prüfen):
- `D_ArbSchG` — Arbeitsschutzgesetz
- `D_GefStoffV` — Gefahrstoffverordnung
- `D_BetrSichV` — Betriebssicherheitsverordnung
- `D_FwDV_500_ABC_Einsatz` — FwDV 500 (ABC-Einsatz, Gleichwertigkeit GefStoffV)
- `D_FwDV_7` — FwDV 7 Atemschutz
- TRGS 900 — als Anlage zu GefStoffV oder separate Quelle

Wenn Quelle nicht im Catalog: Nutzer darauf hinweisen und auf BAuA-Website verweisen (https://www.baua.de).
