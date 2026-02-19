# RAGSource Content: Regelungsrahmen

Oeffentliche Rechtstexte fuer das [RAGSource-Framework](https://github.com/ragsource-ai/ragsource) -- Gesetze, Satzungen und Verordnungen als Markdown mit strukturiertem YAML-Frontmatter.

## Zweck

Dieses Repository ist die **Saeule 1 (Regelungsrahmen)** der RAGSource-Wissensarchitektur. Es enthaelt oeffentliche Rechtstexte auf allen fuenf Ebenen der Normenhierarchie:

| Ebene | Ordner | Beispiele |
|-------|--------|-----------|
| Bund | `regelungsrahmen/bund/` | BauGB, StGB, VwVfG |
| Land BW | `regelungsrahmen/land-bw/` | GemO BW, LBO, FwG BW |
| Landkreis Goeppingen | `regelungsrahmen/lkr-goeppingen/` | Kreissatzungen |
| GVV Raum Bad Boll | `regelungsrahmen/gvv-bad-boll/` | Verbandssatzung |
| Gemeinde Bad Boll | `regelungsrahmen/gem-bad-boll/` | 37 Gemeindesatzungen |

## Frontmatter-Schema

Jede Markdown-Datei beginnt mit YAML-Frontmatter. Die Build-Pipeline des RAGSource-Servers liest diese Metadaten und laedt sie in die Datenbank.

### Pflichtfelder

```yaml
---
titel: Feuerwehrsatzung der Gemeinde Bad Boll
ebene: gemeinde          # bund | land | kreis | gvv | gemeinde
saule: regelungsrahmen   # immer "regelungsrahmen" in diesem Repo
---
```

### Optionale Felder

```yaml
gemeinde: bad-boll       # Gemeinde-Slug (bei ebene: gemeinde)
bundesland: bw           # Wird aus gemeinde auto-resolved
landkreis: goeppingen    # Wird aus gemeinde auto-resolved
quelle: Gemeinderatsbeschluss vom 25.03.2021
gueltig_ab: 2021-03-25
status: published        # published | draft
projekte:                # Projekt-Zuordnung (Performance-Filter)
  - amtsschimmel
keywords:                # Suchbegriffe fuer FTS5-Retrieval
  - Feuerwehr
  - Feuerwehrkommandant
fragen:                  # Typische Nutzerfragen
  - "Wie wird der Feuerwehrkommandant gewaehlt?"
querverweise:            # Verwandte Artikel (exakte Titel)
  - Hauptsatzung der Gemeinde Bad Boll
```

### Projekt-Tagging

Das `projekte`-Feld steuert, welche RAGSource-Projekte diesen Artikel sehen:

| Wert | Bedeutung |
|------|-----------|
| `projekte: [amtsschimmel, brandmeister]` | Nur fuer diese Projekte sichtbar |
| `projekte: [amtsschimmel]` | Nur fuer amtsschimmel sichtbar |
| Feld fehlt oder leer | Fuer **alle** Projekte sichtbar (universell) |

## Ordnerstruktur

```
ragsource-content/
└── regelungsrahmen/
    ├── bund/
    ├── land-bw/
    ├── lkr-goeppingen/
    ├── gvv-bad-boll/
    └── gem-bad-boll/
```

Die Ordnerstruktur dient der menschlichen Orientierung. Der Server klassifiziert Artikel ausschliesslich anhand des Frontmatters (`ebene`, `gemeinde`, `bundesland`).

## Build-Pipeline

Bei Push auf `main` wird ein `repository_dispatch` an das Server-Repo (`ragsource-ai/ragsource`) gesendet. Die dortige GitHub Action:

1. Checkt dieses Repo aus
2. Scannt alle `.md`-Dateien rekursiv
3. Liest Frontmatter + Content
4. Schreibt alles in die D1-Datenbank
5. Deployed den Cloudflare Worker

## Mitmachen

1. Fork erstellen
2. Feature-Branch anlegen
3. Frontmatter-Schema einhalten (siehe oben)
4. Pull Request erstellen

Projektleitung: Christian Traub

## Lizenz

CC-BY 4.0 -- siehe [LICENSE](LICENSE)

Powered by [RAGSource](https://github.com/ragsource-ai/ragsource)
