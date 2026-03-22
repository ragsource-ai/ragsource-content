# Changelog

Wesentliche Änderungen am RAGSource Content-Bestand.
Format basiert auf [Keep a Changelog](https://keepachangelog.com/de/1.0.0/).

---

## [Unreleased]

---

## [2026-03-22] — Bundesrecht Erweiterung

### Hinzugefügt
- Tarifvertragsgesetz (TVG)
- Arbeitsgerichtsgesetz (ArbGG)
- Entgeltfortzahlungsgesetz (EntgFG, zweite Fassung konsolidiert)
- Europawahlordnung (EuWO 1988)
- Europawahlgesetz (EuWG)

---

## [2026-03-21] — Wahlrecht + Technisches

### Hinzugefügt
- Bundeswahlordnung (BWO)
- Bundeswahlgesetz (BWahlG)

### Geändert
- `.gitattributes` hinzugefügt: LF-Zeilenenden für alle Markdown-Dateien normalisiert

---

## [2026-03-17/20] — Ortsrecht Konstanz (107 Quellen)

### Hinzugefügt
- **107 Konstanzer Satzungen und Verordnungen** im v2-Format:
  - Hauptsatzung und Geschäftsordnung des Gemeinderats
  - Alle Satzungen und Ordnungen (vollständig validiert, TOC-Konsistenz hergestellt)
- Vollständige ARS-Verlinkung (`083355004043`) für alle Konstanzer Quellen

---

## [2026-03-08/13] — Bundesrecht Erweiterung

### Hinzugefügt
- Bürgerliches Gesetzbuch (BGB, alle 5 Bücher)
- Betriebsverfassungsgesetz (BetrVG)
- Nachweisgesetz (NachwG)
- Kündigungsschutzgesetz (KSchG)
- Entgeltfortzahlungsgesetz (EntgFG)
- Bundesmeldegesetz (BMG)
- Einkommensteuergesetz (EStG)
- Lohnsteuer-Durchführungsverordnung (LStDV)

---

## [2026-02-28] — Initialbestand

### Hinzugefügt
- Initialer Bestand: Bundesrecht, Landesrecht BW, Kreisrecht Göppingen, GVV Raum Bad Boll, Ortsrecht Bad Boll, Tarifrecht
- Frontmatter-Schema v2 (ARS-basierte Geo-Filterung, `ebene`, `saule`)
- CI/CD-Pipeline: Automatischer RAGSource-DB-Rebuild bei Push auf `main`
