---
titel: "FwDV-Navigation: Dienstvorschriften abrufen"
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
stand: 2026-04-18
beschreibung: "Rezept für das LLM zum effizienten Abruf von FwDV-Inhalten: Catalog → TOC → Get-Workflow für alle Feuerwehr-Dienstvorschriften. Welche FwDV für welche Frage, Abschnitte direkt ansteuern."
---

## Inhaltsverzeichnis
- fwdv_welche [Übersicht: Welche FwDV für welchen Einsatzbereich]
- abruf_workflow [Catalog → TOC → Get — Standardablauf]
- abschnitt_direkt [Direkt-Zugriff auf bekannte Abschnitte]
- zitieren [Wie FwDV-Inhalte korrekt zitieren]

### fwdv_welche
Überblick — welche FwDV für welche Anfrage (Catalog-Suche verwenden, kein Volltext):

| FwDV | Inhalt | Typische Fragen |
|---|---|---|
| D_FwDV_500_ABC_Einsatz | ABC-Einsatz (Strahlen/Bio/Chem), GAMS, PSA, Dekon, Gefahrengruppen | "Was tun bei Chemikalienunfall?", "GAMS-Regel", "Dekon-Stufen" |
| D_FwDV_1 | Grundtätigkeiten — Löscheinsatz | Leiterlegen, Schlauchlegen, Wasserversorgung |
| D_FwDV_2 | Ausbildung der Freiwilligen Feuerwehren | Ausbildungsinhalte, Mindestanforderungen |
| D_FwDV_3 | Einheiten im Lösch- und Hilfeleistungseinsatz | Führungsstruktur, Befehlsgebung |
| D_FwDV_7 | Atemschutz | Atemschutzgeräteträger, Überwachung |
| D_FwDV_10 | Tragbare Leitern | Leiterarten, Aufstellung, Sicherheit |
| D_FwDV_100 | Führung und Leitung im Einsatz | Führungssystem, FEZ, Lagebild |

Catalog-Suche:
```json
RAGSource_catalog()
```
→ Skills-Block erscheint zuerst; Quellen-Block nach Relevanz sortiert. FwDVen unter `endpoint: brandmeister`, `extensions: Feuerwehr`.

### abruf_workflow
**Standard-Ablauf** für unbekannte FwDV oder unbekannten Abschnitt:

**Schritt 1** — Catalog: Quelle identifizieren
```json
RAGSource_catalog()
```
→ FwDV-Eintrag finden, ID notieren (z.B. `D_FwDV_500_ABC_Einsatz`)

**Schritt 2** — TOC: Abschnitte sichten
```json
RAGSource_toc({ "source": "D_FwDV_500_ABC_Einsatz" })
```
→ `###`-Überschriften = abrufbare Einheiten; `##`-Überschriften = Navigation

**Schritt 3** — Get: Zielabschnitt laden
```json
RAGSource_get({
  "source": "D_FwDV_500_ABC_Einsatz",
  "sections": ["1.5.3.2 Erstmaßnahmen (GAMS-Regel)"]
})
```

Mehrere Abschnitte in einem Aufruf möglich (max. 50 §§ gesamt pro Get-Aufruf):
```json
RAGSource_get({
  "source": "D_FwDV_500_ABC_Einsatz",
  "sections": [
    "1.5.3.2 Erstmaßnahmen (GAMS-Regel)",
    "1.5.3.6 Dekontamination",
    "Anlage 2: 4A-Regel für ABC-Einsätze"
  ]
})
```

### abschnitt_direkt
Häufig benötigte Abschnitte in D_FwDV_500_ABC_Einsatz (direkt ohne TOC abrufbar):

**GAMS und Erstmaßnahmen:**
`"1.5.3.2 Erstmaßnahmen (GAMS-Regel)"`

**Gefahrengruppen allgemein:**
`"1.2.1 Gefahrengruppen"` (gibt auch `"1.2 Einsatzgrundlagen"`)

**PSA / Schutzkleidung Formen 1–3:**
`"1.3.1.2 Schutzkleidung (Formen 1–3)"`

**Atemschutz (ABC-spezifisch):**
`"1.3.1.1 Atemschutz"`

**Bereiche (Gefahren-/Übergangs-/Absperrbereich):**
`"1.5.3.5 Gefahren-, Absperr- und Übergangsbereich"`

**Dekon-Stufen I/II/III:**
`"1.5.3.6 Dekontamination"`

**C-Gefahrengruppen:**
`"4.1 Einteilung in Gefahrengruppen (C-Einsatz)"`

**C-Einsatz Erkundung und Beurteilung:**
`"4.4.1 Erkundung und Beurteilung (C-Einsatz)"`

**C-Einsatz Einsatzmaßnahmen:**
`"4.4.2 Einsatzmaßnahmen (C-Einsatz)"`

**4A-Regel:**
`"Anlage 2: 4A-Regel für ABC-Einsätze"`

**Dekon-Matrix:**
`"Anlage 3: Dekon-Matrix für die Feuerwehr"`

### zitieren
FwDV-Inhalte sind Feuerwehr-Dienstvorschriften — amtliche Regelwerke, herausgegeben durch den Ausschuss für Feuerwehrangelegenheiten, Katastrophenschutz und zivile Verteidigung (AFKzV). Rechtsverbindlichkeit durch Übernahme in Landesrecht.

**Korrekte Zitierform**:
> Gemäß FwDV 500, Teil I, § 1.5.3.2 (GAMS-Regel) gilt: „G — Gefahr erkennen, A — Absperren, M — Menschenrettung durchführen, S — Spezialkräfte alarmieren."

Immer:
- FwDV-Nummer + Kurztitel
- Teilangabe (Teil I / Teil II / Anlage)
- Abschnittsnummer + Überschrift
- Wörtliches Zitat aus `RAGSource_get`-Ergebnis, keine Paraphrase
