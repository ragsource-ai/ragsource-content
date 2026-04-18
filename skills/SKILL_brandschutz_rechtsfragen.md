---
titel: "Brandschutz: Rechtsfragen LBO / Sonderbauvorschriften"
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
  - Baurecht
  - Gefahrenabwehrrecht
stand: 2026-04-18
beschreibung: "Handlungsanleitung für Brandschutz-Rechtsfragen: LBO-Zuständigkeit, Musterbauordnung, Sonderbauvorschriften, Feuerwehrzufahrten, Rauchabzug, Sprinkler. Verweis-Workflow für Landesbauordnungen und VBDS/Sonder-VwVen."
---

## Vor diesem Skill
Catalog laden um verfügbare LBO und Sonderbauvorschriften zu sehen:
```json
RAGSource_catalog()
```
→ Quellen mit `extensions: Baurecht` und `ebene: land` identifizieren.
→ Für GP1-Benutzer: auch `brandmeister-gp1` enthält LBO BW + VwVen.

## Inhaltsverzeichnis
- rechtsquellen [Welche Gesetze/VwVen für welche Fragen]
- lbo_abrufen [LBO-Abschnitte gezielt laden]
- sonderbauvorschriften [Sonder-VwVen und Typenvorschriften]
- feuerwehrzugang [Feuerwehrzufahrten, -aufstellflächen, Hydrantenabstand]
- abwehrender_brandschutz [Abgrenzung zur FwDV-Zuständigkeit]

### rechtsquellen
**Brandschutzrecht im deutschen Mehrebenensystem**:

| Ebene | Rechtsquelle | Inhalt |
|---|---|---|
| Bund | keine eigene LBO | Muster-Vorschriften (MBO, MLAR, MLüAR) ohne Bindewirkung |
| Land BW | LBO BW | Baugenehmigung, Brandschutzanforderungen, Rettungswege |
| Land BW | VwV-OBG | Ordnungsbehördliche Verordnung |
| Land BW | IndBauRL | Sonderbauvorschriften Industriebau |
| Land BW | VwV Stationäre Feuerlöschanlagen | Sprinkler-Anwendung |

Wichtige Normen (privatrechtlich, trotzdem Pflichtbezug in Baugenehmigung):
- DIN 14090 (Flächen für die Feuerwehr)
- DIN 14461 (Löschwasserleitungen)
- DIN VDE 0833 (Gefahrenmeldeanlagen)

**Catalog-Suche für LBO-Fragen**:
```json
RAGSource_catalog()
```
Dann: Quelle mit `id` beginnend mit `BW_` für Landesrecht BW identifizieren.

### lbo_abrufen
**Workflow** für LBO-spezifische Anfragen:

1. TOC der LBO BW laden:
```json
RAGSource_toc({ "source": "BW_LBO" })
```
2. Relevante §§ identifizieren (Feuerwehr-relevante Abschnitte: §§ 15, 34–38 bei LBO BW)
3. Gezielt laden:
```json
RAGSource_get({
  "source": "BW_LBO",
  "sections": ["§ 15 Wände, Pfeiler und Stützen"]
})
```

Wenn Quelle-ID unbekannt: `RAGSource_catalog()` → Einträge mit `ebene: land` und `extensions: Baurecht` suchen.

**Keine LBO im Catalog**: Nutzer darauf hinweisen, dass LBO-Volltext nicht verfügbar ist — auf landesrecht-bw.de verweisen oder GP1-Instanz nutzen.

### sonderbauvorschriften
Sonderbauvorschriften (VwVen, Richtlinien) ergänzen die LBO für besondere Gebäudetypen:

| Vorschrift | Anwendungsbereich | Catalog-ID (falls verfügbar) |
|---|---|---|
| IndBauRL BW | Industriegebäude > 1.600 m² | `BW_VWV_IndBauRL` |
| VkVO BW | Versammlungsstätten | `BW_VWV_VkVO` |
| MLAR | Leitungsanlagen (Muster, ohne LandR) | im Catalog prüfen |
| VStättVo BW | Versammlungsstätten LBO-Ausführung | im Catalog prüfen |

Procedure: Catalog → Quelle identifizieren → TOC → relevante Abschnitte per Get laden.

Fehlt eine Richtlinie im Catalog: Direkt auf Quelldokument verweisen (BAuA, LBO-Erlass des IM BW) und Nutzer auf Eigenrecherche hinweisen.

### feuerwehrzugang
**Feuerwehrzufahrten und -aufstellflächen** — typisch geregelt in:
- LBO BW § 5 (Abstandsflächen) + § 15 (Wege für die Feuerwehr)
- DIN 14090 "Flächen für die Feuerwehr auf Grundstücken" (privatrechtlich, meist als AiB einbezogen)
- Gemeindliche Satzungen (in RAGSource als Ortsrecht, z.B. `KON_Satzung_Stellplatz`)

**Hydrantenabstand**: Regelungen in DIN 14090 + Wasserversorgungskonzept der Gemeinde. Nicht bundeseinheitlich.

**Smoke-Control / Rauchabzug**: 
- Industriegebäude: IndBauRL Abschnitt 6
- Versammlungsstätten: VStättVo § 24 ff.
- Hochhäuser: Hochhausl § 19 ff.

Immer Quellen-Prüfung: Welches Bundesland? → Landesspezifische Ausführungsregeln gelten.

### abwehrender_brandschutz
**Abgrenzung**: Brandschutzrecht in Skills hier = vorbeugender Brandschutz (Baugenehmigung, Vorschriften).
Abwehrender Brandschutz (Einsatztaktik) → FwDV 1/3/7/100 und spezifische Einsatz-Skills.

Für Fragen zum laufenden Einsatz:
- Einsatztaktik → `SKILL_gefahrstoff_einsatz` (C-Einsatz) oder FwDV 1 (Löscheinsatz)
- Führung → FwDV 100
- Atemschutz → FwDV 7

Für Fragen zum vorbeugenden Brandschutz (Baugenehmigung, Bestandsschutz, Nachweise):
→ Diesen Skill verwenden + Catalog nach LBO und VwVen durchsuchen.
