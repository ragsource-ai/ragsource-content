# RAGSource Content: Regelungsrahmen

[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![Quellen](https://img.shields.io/badge/Quellen-621%2B-blue.svg)](regelungsrahmen/)
[![CI](https://github.com/ragsource-ai/ragsource-content/actions/workflows/trigger-deploy.yml/badge.svg)](https://github.com/ragsource-ai/ragsource-content/actions/workflows/trigger-deploy.yml)

Öffentliche Rechtstexte für kommunale KI-Assistenten — Gesetze, Satzungen und Verordnungen als strukturiertes Markdown.

---

## Was ist das hier?

Dieses Repository enthält den **öffentlichen Rechtstext-Bestand** des RAGSource-Frameworks.
Die Artikel bilden die Wissensbasis für KI-Assistenten wie [amtsschimmel.ai](https://amtsschimmel.ai) und [brandmeister.ai](https://brandmeister.ai), die Kommunen und Behörden bei Verwaltungsaufgaben unterstützen.

Jede Markdown-Datei entspricht einem Rechtsdokument (Gesetz, Satzung, Verordnung) oder einer LLM-Handlungsanleitung (Skill) mit strukturierten Metadaten. Der RAGSource-Server liest diese Dateien, indexiert sie in einer D1-Datenbank und stellt sie über eine MCP-Schnittstelle für KI-Systeme bereit.

**Aktuell:** 621+ Quellen aus EU-, Bundes-, Landes-, Kreis- und Gemeinderecht + Tarifverträge

---

## Normenhierarchie

| Ebene | Ordner | Beispiele |
|-------|--------|-----------|
| EU-Recht | `regelungsrahmen/EU/` | DSGVO, ArbZRL |
| Bundesrecht | `regelungsrahmen/Bund/Bundesrecht/` | BauGB, VwVfG, FwDV |
| Landesrecht BW | `regelungsrahmen/Laender_und_Kommunen/bw/Landesgesetze/` | GemO BW, LBO, FwG BW |
| Verwaltungsvorschriften BW | `regelungsrahmen/Laender_und_Kommunen/bw/VwVen/` | VwV-Feuerwehr, VwV-Abfall |
| Kreisrecht | `regelungsrahmen/Laender_und_Kommunen/bw/Lkr_GP/Kreisrecht/` | Kreissatzungen GP |
| Verbandsrecht | `regelungsrahmen/Laender_und_Kommunen/bw/Lkr_GP/GVB_*/` | Verbandssatzungen |
| Ortsrecht | `regelungsrahmen/Laender_und_Kommunen/bw/Lkr_GP/BBO/` | Satzungen Bad Boll |
| Tarifrecht | `regelungsrahmen/Tarifvertraege/` | TVöD, TV-L, AVR |
| Skills (Säule 2) | `skills/` | LLM-Handlungsanleitungen |

---

## Wie funktioniert das?

Jede Datei beginnt mit YAML-Frontmatter, das den Artikel klassifiziert:

```yaml
---
titel: Feuerwehrsatzung der Gemeinde Bad Boll
ebene: gemeinde
saule: regelungsrahmen
# ARS-Felder (maschinell, für Geo-Filterung)
land_ars: "08"
kreis_ars: "08117"
verband_ars: "081175009"
gemeinde_ars: "081175009012"
land: Baden-Württemberg
kreis: Göppingen
verband: GVV Raum Bad Boll
gemeinde: Bad Boll
gueltig_ab: 2021-03-25
endpoints:            # Tenancy: leer = universell für alle Deployments
  - amtsschimmel
extensions:           # Themen: thematische Zuordnung
  - Feuerwehr
---
```

Der Server klassifiziert Artikel **ausschließlich anhand des Frontmatters** — nicht anhand des Dateipfads. Die Ordnerstruktur dient der menschlichen Orientierung.

### Vollständiges Frontmatter-Schema

**Pflichtfelder:**

| Feld | Werte | Beschreibung |
|------|-------|--------------|
| `titel` | Freitext | Vollständiger Titel des Rechtsdokuments |
| `ebene` | `eu` \| `bund` \| `land` \| `kreis` \| `verband` \| `gemeinde` | Normenhierarchie |
| `saule` | `regelungsrahmen` | Säule 1 (Rechtstexte); Skills haben `saule: 2` |

**Geo-Felder (ARS = Amtlicher Regionalschlüssel):**

Nur die Felder setzen, die zur `ebene` passen (bund = keine, land = `land_ars`, usw.):

| Feld | Beispiel | Beschreibung |
|------|---------|--------------|
| `land_ars` | `"08"` | 2-stellig, Bundesland |
| `kreis_ars` | `"08117"` | 5-stellig, Landkreis |
| `verband_ars` | `"081175009"` | 9-stellig, Gemeindeverband |
| `gemeinde_ars` | `"081175009012"` | 12-stellig, Gemeinde |
| `land` | `Baden-Württemberg` | Klartext zum ARS (Lesehilfe) |
| `kreis` | `Göppingen` | Klartext zum ARS |
| `verband` | `GVV Raum Bad Boll` | Klartext zum ARS |
| `gemeinde` | `Bad Boll` | Klartext zum ARS |

**Weitere optionale Felder:**

| Feld | Beispiel | Beschreibung |
|------|---------|--------------|
| `quelle` | `Gemeinderatsbeschluss 25.03.2021` | Herkunft des Dokuments |
| `gueltig_ab` | `2021-03-25` | Datum des Inkrafttretens (ISO-Format) |
| `stand` | `2025-12-01` | Letzte inhaltliche Änderung |
| `url` | `https://...` | Quell-URL des Originaldokuments |
| `status` | `published` \| `ausser_kraft` | Gültigkeitsstatus |
| `endpoints` | `[amtsschimmel]` | Tenancy: welche Deployments sehen die Quelle (leer = alle) |
| `extensions` | `[Feuerwehr]` | Themen: thematische Zuordnung |
| `rechtsrang` | `1`–`6` | Normenhierarchie-Ebene (wird vom Server abgeleitet) |

### Markdown-Struktur

Jede Datei enthält nach dem Frontmatter ein optionales Inhaltsverzeichnis und den Volltext. Die Heading-Ebenen haben feste Bedeutung:

```markdown
## Inhaltsverzeichnis

- § 1 Aufgaben
- § 2 Begriffsbestimmungen

## Kapitel I — Allgemeine Bestimmungen   ← Strukturüberschrift, kein Inhalt

### § 1 Aufgaben                          ← Abrufbare Einheit (einzeln abholbar)
Volltext...

### § 2 Begriffsbestimmungen
Volltext...
```

**Trennregel:** Jedes `###`-Heading öffnet einen neuen, einzeln abrufbaren Abschnitt. `##`-Headings (außer `## Inhaltsverzeichnis`) sind reine Strukturüberschriften.

---

## Dateinamen-Schema

`{PREFIX}_{Rechtsnatur}_{Kurztitel}.md`

| Präfix | Ebene | Beispiel |
|--------|-------|---------|
| `EU_` | EU-Recht | `EU_DSGVO.md` |
| `D_` | Bundesrecht | `D_BauGB.md` |
| `BW_` | Landesrecht BW | `BW_FwG.md` |
| `BW_VWV_` | VwVen BW | `BW_VWV_Feuerwehr.md` |
| `Lkr_GP_` | Kreisrecht Göppingen | `Lkr_GP_Kreissatzung.md` |
| `KON_` | Ortsrecht Konstanz | `KON_Satzung_Hauptsatzung.md` |
| `BBO_` | Ortsrecht Bad Boll | `BBO_Satzung_Feuerwehr.md` |
| `SKILL_` | Skills (Säule 2) | `SKILL_gefahrstoff_einsatz.md` |

Abgelaufene Dokumente liegen in `ausser_kraft/`-Unterordnern und tragen `status: ausser_kraft` im Frontmatter.

---

## Mitmachen

Fehlende Rechtstexte? Fehler gefunden? Beiträge sind willkommen — siehe [CONTRIBUTING.md](CONTRIBUTING.md).

Alle Inhalte müssen **öffentlich zugänglich und lizenzrechtlich frei verwendbar** sein (amtliche Werke nach § 5 UrhG oder vergleichbar).

Projektleitung: **Christian Traub** — alle PRs werden manuell geprüft.

---

## CI/CD

Bei Push auf `main` wird automatisch ein Rebuild der RAGSource-Datenbank ausgelöst. Neue Artikel sind typischerweise **innerhalb von 2 Minuten live**.

---

## Lizenz

**CC-BY 4.0** — siehe [LICENSE](LICENSE)

Amtliche Werke (§ 5 UrhG) sind gemeinfrei; die redaktionelle Aufbereitung und Strukturierung steht unter CC-BY 4.0.

Powered by [RAGSource](https://github.com/ragsource-ai)
