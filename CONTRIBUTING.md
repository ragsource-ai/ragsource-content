# Mitmachen / Contributing

*[English version below](#english-version)*

---

## DE: Beiträge zu RAGSource Content

Dieses Repository enthält öffentliche Rechtstexte für kommunale KI-Assistenten. Beiträge — neue Gesetze, aktualisierte Fassungen, Korrekturen — sind willkommen.

### Was wir suchen

- **Neue Rechtsquellen:** Gesetze, Satzungen oder Verordnungen, die im Regelungsrahmen fehlen
- **Aktualisierungen:** Neuere Fassungen bestehender Texte
- **Korrekturen:** Fehler im Frontmatter, falsche Paragraphen-Nummern, Tippfehler im Inhalt
- **Neue Gebietskörperschaften:** Ortsrecht weiterer Gemeinden (Präzedenzfall: Konstanz, Bad Boll)

### Voraussetzungen

Alle Inhalte müssen:

1. **Öffentlich zugänglich** sein (keine urheberrechtlich geschützten Inhalte)
2. **Lizenzrechtlich frei verwendbar** sein — amtliche Werke nach § 5 UrhG oder vergleichbar
3. Das **Frontmatter-Schema** einhalten (siehe unten)
4. Das **Heading-Format** einhalten: `###` für alle abrufbaren Abschnitte (§§, Artikel, Anhänge, numerische Abschnitte). `##` nur für das Inhaltsverzeichnis (`## Inhaltsverzeichnis`) und rein strukturelle Zwischenüberschriften ohne eigenen Inhalt.

### Frontmatter-Pflichtfelder

```yaml
---
titel: Vollständiger Titel des Rechtsdokuments
ebene: bund | land | kreis | verband | gemeinde
saule: regelungsrahmen
# ARS-Felder passend zur Ebene:
land_ars: "08"          # 2-stellig (Bundesland)
kreis_ars: "08117"      # 5-stellig (Landkreis)
verband_ars: "081175009" # 9-stellig (Verband)
gemeinde_ars: "081175009012" # 12-stellig (Gemeinde)
---
```

Vollständiges Schema: siehe [README.md](README.md)

### Workflow

```bash
# 1. Repository forken
# 2. Feature-Branch anlegen
git checkout -b add-[kuerzel]-[beschreibung]

# 3. Datei anlegen (Namensschema: KON_Satzung_Kurzname.md o.ä.)
# 4. Frontmatter und Inhalt nach Schema befüllen
# 5. Pull Request erstellen
```

**Dateinamen-Konvention:** `{GEM}_{Rechtsnatur}_{Kurztitel}.md`
Beispiel: `KON_Satzung_Hauptsatzung.md`, `BB_Satzung_Feuerwehr.md`

### Content Pipeline

Für größere Batches (PDFs → Markdown) steht die [Content Pipeline](https://github.com/ragsource-ai/ragsource) zur Verfügung. Beschreibung: `tools/content-pipeline/README.md`.

### Review-Prozess

Alle PRs werden von **Christian Traub** (Projektleitung) manuell geprüft. Nach dem Merge ist der neue Inhalt typischerweise **innerhalb von 2 Minuten live** (automatisches CI/CD).

### Fragen?

GitHub Issue öffnen oder an **support@amtsschimmel.ai** wenden.

---

## English Version

### Contributing to RAGSource Content

This repository contains public legal texts for municipal AI assistants. Contributions — new laws, updated versions, corrections — are welcome.

### What We're Looking For

- **New legal sources:** Laws, statutes, or ordinances missing from the framework
- **Updates:** Newer versions of existing texts
- **Corrections:** Errors in frontmatter, wrong paragraph numbers, typos
- **New municipalities:** Local ordinances for additional communities

### Requirements

All content must:

1. Be **publicly accessible** (no copyrighted content)
2. Be **freely usable** — official works under § 5 UrhG or equivalent
3. Follow the **frontmatter schema** (see README)
4. Follow the **heading format**: `###` for all retrievable sections (§§, articles, annexes, numbered sections). `##` only for the table of contents (`## Inhaltsverzeichnis`) and purely structural headings with no standalone content.

### Process

Fork → feature branch → PR. All PRs are reviewed manually by the project lead.

After merge, new content is typically **live within 2 minutes** via automatic CI/CD.

### Questions?

Open a GitHub issue or contact **support@amtsschimmel.ai**.
