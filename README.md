# RAGSource Content

[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![Rechtsquellen](https://img.shields.io/badge/Rechtsquellen-621%2B-blue.svg)](regelungsrahmen/)
[![Skills](https://img.shields.io/badge/Skills-6-8A2BE2.svg)](skills/)
[![CI](https://github.com/ragsource-ai/ragsource-content/actions/workflows/trigger-deploy.yml/badge.svg)](https://github.com/ragsource-ai/ragsource-content/actions/workflows/trigger-deploy.yml)

Öffentliche Wissensbasis für KI-Assistenten — Rechtstexte, Skills und Policies als strukturiertes Markdown.

---

## Was ist das hier?

Dieses Repository enthält die **öffentliche Wissensbasis** des RAGSource-Frameworks: Gesetze, Satzungen, Verordnungen und LLM-Handlungsanleitungen (Skills) als Markdown-Dateien mit strukturierten Metadaten.

Die Artikel bilden die Grundlage für KI-Assistenten wie [amtsschimmel.ai](https://amtsschimmel.ai) und [brandmeister.ai](https://brandmeister.ai). Der dazugehörige Server-Code liegt in [ragsource-server](https://github.com/ragsource-ai/ragsource-server): er liest diese Dateien, indexiert sie in einer D1-Datenbank und stellt sie über eine MCP-Schnittstelle für LLMs bereit.

**Aktuell:** 621+ Rechtsquellen + 6 Skills aus EU-, Bundes-, Landes-, Kreis- und Gemeinderecht

---

## Normenhierarchie

| Ebene | Ordner | Beispiele |
|-------|--------|-----------|
| EU-Recht | `regelungsrahmen/EU/` | DSGVO, ArbZRL |
| Bundesrecht | `regelungsrahmen/Bund/Bundesrecht/` | BauGB, VwVfG, FwDV |
| Landesrecht BW | `regelungsrahmen/Laender_und_Kommunen/bw/Landesgesetze/` | GemO BW, LBO, FwG BW |
| Verwaltungsvorschriften BW | `regelungsrahmen/Laender_und_Kommunen/bw/VwVen/` | VwV-Feuerwehr, VwV-Abfall |
| Kreisrecht | `regelungsrahmen/Laender_und_Kommunen/bw/Lkr_GP/Kreisrecht/` | Kreissatzungen Göppingen |
| Verbandsrecht | `regelungsrahmen/Laender_und_Kommunen/bw/Lkr_GP/GVB_*/` | Verbandssatzungen |
| Ortsrecht | `regelungsrahmen/Laender_und_Kommunen/bw/Lkr_GP/BBO/` | Satzungen Bad Boll |
| Tarifrecht | `regelungsrahmen/Tarifvertraege/` | TVöD, TV-L, AVR |
| Skills | `skills/` | LLM-Handlungsanleitungen |

---

## Wie funktioniert das?

Jede Datei beginnt mit YAML-Frontmatter, das den Artikel klassifiziert. Der Server liest **ausschließlich das Frontmatter** — nicht den Dateipfad. Die Ordnerstruktur dient der menschlichen Orientierung.

```yaml
---
titel: Feuerwehrsatzung der Gemeinde Bad Boll
ebene: gemeinde
saule: regelungsrahmen
land_ars: "08"
kreis_ars: "08117"
verband_ars: "081175009"
gemeinde_ars: "081175009012"
land: Baden-Württemberg
kreis: Göppingen
verband: GVV Raum Bad Boll
gemeinde: Bad Boll
gueltig_ab: 2021-03-25
endpoints:            # leer = universell für alle Deployments
  - amtsschimmel
extensions:           # thematische Zuordnung
  - Feuerwehr
---
```

### Vollständiges Frontmatter-Schema

**Pflichtfelder:**

| Feld | Werte | Beschreibung |
|------|-------|--------------|
| `titel` | Freitext | Vollständiger Titel des Rechtsdokuments |
| `ebene` | `eu` \| `bund` \| `land` \| `kreis` \| `verband` \| `gemeinde` | Normenhierarchie |
| `saule` | `regelungsrahmen` \| `2` | Säule 1 = Rechtstexte; Säule 2 = Skills |

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
| `gueltig_ab` | `2021-03-25` | Inkrafttreten (ISO-Format); bei konsolid. Fassungen: letzte Änderung |
| `stand` | `2025-12-01` | Letzte inhaltliche Änderung |
| `url` | `https://...` | Quell-URL des Originaldokuments |
| `status` | `published` \| `ausser_kraft` | Gültigkeitsstatus |
| `endpoints` | `[amtsschimmel]` | Tenancy: welche Deployments sehen die Quelle (leer = alle) |
| `extensions` | `[Feuerwehr]` | Thematische Zuordnung (OR-verknüpft bei Suche) |

### Markdown-Struktur

```markdown
## Inhaltsverzeichnis

- § 1 Aufgaben
- § 2 Begriffsbestimmungen

## Kapitel I — Allgemeine Bestimmungen   ← Strukturüberschrift, kein eigener Inhalt

### § 1 Aufgaben                          ← Abrufbare Einheit (einzeln abholbar)
Volltext...

### § 2 Begriffsbestimmungen
Volltext...
```

**Trennregel:** Jedes `###`-Heading öffnet einen neuen, einzeln abrufbaren Abschnitt. `##`-Headings (außer `## Inhaltsverzeichnis`) sind reine Strukturüberschriften und landen im Body der nachfolgenden Section.

---

## Dateinamen-Schema

`{PREFIX}_{Rechtsnatur}_{Kurztitel}.md`

| Präfix | Ebene | Beispiel |
|--------|-------|---------|
| `EU_` | EU-Recht | `EU_DSGVO.md` |
| `D_` | Bundesrecht | `D_BauGB.md` |
| `BW_` | Landesrecht BW | `BW_FwG.md` |
| `BW_VWV_` | Verwaltungsvorschriften BW | `BW_VWV_Feuerwehr.md` |
| `Lkr_GP_` | Kreisrecht Göppingen | `Lkr_GP_Kreissatzung.md` |
| `Lkr_KON_` | Kreisrecht Konstanz | `Lkr_KON_Kreissatzung.md` |
| `GVB_` | Verbandsrecht | `GVB_GVV_BadBoll_Verbandssatzung.md` |
| `BBO_` | Ortsrecht Bad Boll | `BBO_Satzung_Feuerwehr.md` |
| `KON_` | Ortsrecht Konstanz | `KON_Satzung_Hauptsatzung.md` |
| `SKILL_` | Skills (Säule 2) | `SKILL_gefahrstoff_einsatz.md` |

Abgelaufene Dokumente liegen in `ausser_kraft/`-Unterordnern und tragen `status: ausser_kraft` im Frontmatter.

---

## Skills (Säule 2)

Neben Rechtstexten enthält das Repository **Skills** — LLM-Handlungsanleitungen für domänenspezifische Workflows (Einsatztaktik, Gefahrstoffabfragen, Rechtsfragen). Sie liegen im `skills/`-Ordner und werden vom Server wie Rechtsquellen indexiert, aber mit `saule: 2` und `typ: skill` klassifiziert.

---

## Mitmachen

Fehlende Rechtstexte? Fehler gefunden? Beiträge sind willkommen — siehe [CONTRIBUTING.md](CONTRIBUTING.md).

Alle Inhalte müssen **öffentlich zugänglich und lizenzrechtlich frei verwendbar** sein (amtliche Werke nach § 5 UrhG oder vergleichbar).

Projektleitung: **Christian Traub** — alle PRs werden manuell geprüft.

---

## CI/CD

Push auf `main` → automatischer DB-Rebuild via [ragsource-server](https://github.com/ragsource-ai/ragsource-server) → **live in ~2 Minuten**.

---

## Lizenz

**CC-BY 4.0** — siehe [LICENSE](LICENSE)

Amtliche Werke (§ 5 UrhG) sind gemeinfrei; die redaktionelle Aufbereitung und Strukturierung steht unter CC-BY 4.0.

---

<p align="center">
  <br>
  Made with ❤️ for Open Source AI
  <br><br>
  This project started from a personal need: reliable, citable knowledge<br>
  for firefighters, public servants, and everyone who needs to get things right.<br>
  <br>
  <strong>It belongs to everybody.</strong>
</p>
