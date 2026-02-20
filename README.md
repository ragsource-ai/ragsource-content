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
gemeinde: bad-boll
keywords:
  - Feuerwehr
  - Feuerwehrkommandant
fragen:
  - "Wie wird der Feuerwehrkommandant gewählt?"
---
```

Der Server klassifiziert Artikel **ausschließlich anhand des Frontmatters** — nicht anhand des Dateipfads. Die Ordnerstruktur dient der menschlichen Orientierung und kann jederzeit angepasst werden.

### Vollständiges Frontmatter-Schema

**Pflichtfelder:**

| Feld | Werte | Beschreibung |
|------|-------|--------------|
| `titel` | Freitext | Vollständiger Titel des Rechtsdokuments |
| `ebene` | `bund` \| `land` \| `kreis` \| `gvv` \| `gemeinde` | Normenhierarchie |
| `saule` | `regelungsrahmen` | Immer so in diesem Repo |

**Optionale Felder:**

| Feld | Beispiel | Beschreibung |
|------|---------|--------------|
| `gemeinde` | `bad-boll` | Gemeinde-Slug (bei ebene: gemeinde) |
| `bundesland` | `bw` | Wird aus gemeinde auto-resolved |
| `landkreis` | `goeppingen` | Wird aus gemeinde auto-resolved |
| `quelle` | `Gemeinderatsbeschluss 25.03.2021` | Herkunft des Dokuments |
| `gueltig_ab` | `2021-03-25` | Datum des Inkrafttretens |
| `status` | `published` \| `draft` | Veröffentlichungsstatus |
| `projekte` | `[amtsschimmel]` | Projekt-Sichtbarkeit (leer = alle) |
| `keywords` | `[Feuerwehr, Satzung]` | Suchbegriffe für den Volltext-Index |
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
