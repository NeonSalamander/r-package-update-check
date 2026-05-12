# 🪶 R-package-update-check

> A skill that automatically collects and describes new CRAN packages published in the last week — and saves the result as a ready-to-use Markdown digest.

**English** | [Русский](README.ru.md)

---

## What it does

Every week hundreds of new R packages appear on CRAN. R-package-update-check scans the registry, fetches metadata for each new package, and produces a structured `.md` digest with plain-language descriptions, categories, dependencies, and direct links.

**One prompt → one Markdown file, ready to publish or share.**

---

## Quick start

1. Install the skill into your AI assistant environment (see [Installation](#installation))
2. Open a conversation and type:

   > *"Show new CRAN packages this week"*

3. The assistant fetches the data, generates descriptions, and returns a `cran-digest-YYYY-MM-DD.md` file for download.

---

## Output format

Each digest follows this structure:

```
# New CRAN Packages: 2025-06-07 — 2025-06-13

> Digest generated automatically by R-package-update-check.
> Total new packages in period: 42

## Contents by Category
- Statistics: 8
- Visualization: 6
- Machine Learning: 11
- ...

## Packages

### awesome-pkg (0.1.0)
**What it does:** ...
**Domain:** Machine Learning
**Dependencies:** torch, R6, cli
**License:** MIT
**Author/Maintainer:** Jane Doe
**Link:** https://cran.r-project.org/package=awesome-pkg
```

---

## Supported parameters

You can refine the request in plain language — no configuration files needed:

| Parameter | Default | Example |
|---|---|---|
| Period | 7 days | *"for the last 14 days"* |
| Language | Language of your prompt | *"descriptions in Russian"* |
| Topic filter | none | *"only visualization packages"* |
| File name | `cran-digest-YYYY-MM-DD.md` | *"save as weekly-cran.md"* |
| Max packages | all | *"top 20 most interesting"* |

---

## Installation

### Requirements

- An AI assistant with skill/agent support enabled (e.g. Claude, OpenClaw, Hermes, or any compatible runtime)
- The skill files from this repository

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/NeonSalamander/r-package-update-check.git
   ```

2. Copy `SKILL.md` (Russian) or `SKILL-en.md` (English) into your assistant's skills directory.

3. Restart your assistant or reload skills — the skill will appear in the available skills list automatically.

---

## Repository structure

```
r-package-update-check/
├── SKILL.md          # Skill definition — Russian
├── SKILL-en.md       # Skill definition — English
├── README.md         # This file
└── README.ru.md      # Russian README
```

---

## Data sources

| Source | URL | Used for |
|---|---|---|
| CRAN by date | `cran.r-project.org/web/packages/available_packages_by_date.html` | List of new packages |
| crandb API | `crandb.r-pkg.org/{pkg}` | Package metadata (primary) |
| CRAN DESCRIPTION | `cran.r-project.org/web/packages/{pkg}/DESCRIPTION` | Metadata fallback |

---

## Language support

Skill files are available in two languages. The description language in the generated digest follows the language of your prompt — no extra configuration needed.

| File | Skill language | Digest language |
|---|---|---|
| `SKILL.md` | Russian | Follows prompt |
| `SKILL-en.md` | English | Follows prompt |

---

## Contributing

Issues and pull requests are welcome. If you want to add support for a new output format, additional data sources, or a new language version of the skill — feel free to open a PR.

---

## License

MIT
