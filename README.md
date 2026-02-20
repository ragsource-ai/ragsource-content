# RAGSource Content: Regelungsrahmen

Öffentliche Rechtstexte für kommunale KI-Assistenten — Gesetze, Satzungen und Verordnungen als strukturiertes Markdown.

---

## Was ist das hier?

Dieses Repository enthält den **öffentlichen Rechtstext-Bestand** des RAGSource-Frameworks.
Die Artikel bilden die Wissensbasis für KI-Assistenten wie [amtsschimmel.ai](https://amtsschimmel.ai), die Kommunen bei Verwaltungsaufgaben unterstützen.

Jede Markdown-Datei entspricht einem Rechtsdokument (Gesetz, Satzung, Verordnung) mit strukturierten Metadaten. Der RAGSource-Server liest diese Dateien, indexiert sie und stellt sie über eine MCP-Schnittstelle für KI-Systeme bereit.

**Aktuell:** 109 Artikel aus Bundes-, Landes-, Kreis- und Gemeinderecht

---

## Normenhierarchie

| Ebene | Ordner | Beispiele |
|-------|--------|-----------|
| Bundesrecht | `regelungsrahmen/bundesrecht/` | BauGB, VwVfG |
| Landesrecht BW | `regelungsrahmen/landesrecht-bw/` | GemO BW, LBO, FwG BW |
| Kreisrecht Göppingen | `regelungsrahmen/kreisrecht-goeppingen/` | Kreissatzungen |
| GVV Raum Bad Boll | `regelungsrahmen/gvv-bad-boll/` | Verbandssatzung |
| Ortsrecht Bad Boll | `regelungsrahmen/ortsrecht-bad-boll/` | 37 Gemeindesatzungen |
| Tarifrecht | `regelungsrahmen/tarifrecht/` | TVöD, TV-L, AVR |

---

## Wie funktioniert das?

Jede Datei beginnt mit YAML-Frontmatter, das den Artikel klassifiziert:

```yaml
---
titel: Feuerwehrsatzung der Gemeinde Bad Boll
ebene: gemeinde
saule: regelungsrahmen
# ARS-Felder (maschinell, fuer Geo-Filterung)
land_ars: "08"
kreis_ars: "08117"
verband_ars: "081175009"
gemeinde_ars: "081175009012"
# Klartext-Felder (Lesehilfe, fuer Obsidian + LLM-Response)
land: Baden-Wuerttemberg
kreis: Goeppingen
verband: GVV Raum Bad Boll
gemeinde: Bad Boll
keywords:
  - Feuerwehr
  - Feuerwehrkommandant
fragen:
  - "Wie wird der Feuerwehrkommandant gewaehlt?"
---
```

Der Server klassifiziert Artikel **ausschließlich anhand des Frontmatters** — nicht anhand des Dateipfads. Die Ordnerstruktur dient der menschlichen Orientierung und kann jederzeit angepasst werden.

### Vollständiges Frontmatter-Schema

**Pflichtfelder:**

| Feld | Werte | Beschreibung |
|------|-------|--------------|
| `titel` | Freitext | Vollständiger Titel des Rechtsdokuments |
| `ebene` | `bund` \| `land` \| `kreis` \| `verband` \| `gemeinde` | Normenhierarchie |
| `saule` | `regelungsrahmen` | Immer so in diesem Repo |

**Geo-Felder (ARS = Amtlicher Regionalschluessel):**

Nur die Felder setzen, die zur `ebene` passen (bund = keine, land = `land_ars`, usw.):

| Feld | Beispiel | Beschreibung |
|------|---------|--------------|
| `land_ars` | `"08"` | 2-stellig, Bundesland |
| `kreis_ars` | `"08117"` | 5-stellig, Landkreis |
| `verband_ars` | `"081175009"` | 9-stellig, Gemeindeverband |
| `gemeinde_ars` | `"081175009012"` | 12-stellig, Gemeinde |
| `land` | `Baden-Wuerttemberg` | Klartext zum ARS (Lesehilfe) |
| `kreis` | `Goeppingen` | Klartext zum ARS |
| `verband` | `GVV Raum Bad Boll` | Klartext zum ARS |
| `gemeinde` | `Bad Boll` | Klartext zum ARS |

**Weitere optionale Felder:**

| Feld | Beispiel | Beschreibung |
|------|---------|--------------|
| `quelle` | `Gemeinderatsbeschluss 25.03.2021` | Herkunft des Dokuments |
| `gueltig_ab` | `2021-03-25` | Datum des Inkrafttretens |
| `status` | `published` \| `draft` | Veroeffentlichungsstatus |
| `projekte` | `[amtsschimmel]` | Projekt-Sichtbarkeit (leer = alle) |
| `keywords` | `[Feuerwehr, Satzung]` | Suchbegriffe fuer den Volltext-Index |
| `fragen` | `["Wie wird ...?"]` | Typische Nutzerfragen |
| `querverweise` | `[Hauptsatzung ...]` | Verwandte Artikel (exakte Titel) |

---

## Mitmachen

Fehlende Rechtstexte? Fehler gefunden? Beiträge sind willkommen.

1. Repository forken
2. Feature-Branch anlegen (`git checkout -b add-gemeindeordnung-by`)
3. Frontmatter-Schema einhalten (siehe oben)
4. Pull Request erstellen

Alle Inhalte müssen **öffentlich zugänglich und lizenzrechtlich frei verwendbar** sein (amtliche Werke nach § 5 UrhG oder vergleichbar).

Projektleitung: **Christian Traub** — alle PRs werden manuell geprüft.

---

## CI/CD

Bei Push auf `main` wird automatisch ein Rebuild der RAGSource-Datenbank ausgelöst. Neue Artikel sind typischerweise **innerhalb von 2 Minuten live**.

---

## Lizenz

**CC-BY 4.0** — siehe [LICENSE](LICENSE)

Powered by [RAGSource](https://ragsource.ai)
