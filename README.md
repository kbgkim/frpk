# Financial Risk Knowledge Platform (FRKP)

## Vision
A comprehensive, authoritative, and well-governed knowledge platform covering financial risk management — from foundational concepts to advanced quantitative methods, regulatory frameworks, and risk engine architecture.

## Objectives
1. **Single Source of Truth** — All financial risk knowledge curated in one governed repository.
2. **Rigorous Governance** — Every document follows a defined lifecycle: Draft → Review → Approved → Frozen → Published.
3. **Cross-Referenced** — Glossary terms, formulas, knowledge articles, and volumes are fully interconnected.
4. **Extensible** — Designed for 500–1000 Markdown documents across 11 top-level directories.
5. **Project-Managed** — Work is organized by Epic → Feature → Sprint → Task → Deliverable.
6. **Audit-Ready** — Full version history, decision logs, and archival of superseded content.

## Repository Structure

```
FRKP/
├── 00_Project_Management/   Governance, planning, templates
├── 01_Reference_Library/    External references and citations
├── 02_Knowledge_Base/       Risk knowledge articles
├── 03_Formula_Catalog/      Formulas, models, notation
├── 04_Glossary/             Terminology and definitions
├── 05_Volumes/              Long-form risk volumes
├── 06_Architecture/         Risk engine design documentation
├── 07_Appendix/             Supporting material
├── 08_Output/               Generated artifacts (gitignored)
├── 09_Assets/               Images, diagrams, style files
├── 99_Archive/              Superseded and historical content
└── docs/                    Site generation support
```

## Document Lifecycle

```
Draft → Review → Approved → Frozen → Published
```

Each state has specific transition rules. See `00_Project_Management/Templates/DOCUMENT_STATUS_RULE.md`.

## Document Numbering

Every document receives a unique ID:

```
FRKP-[CATEGORY]-[0001]
```

See `00_Project_Management/Templates/DOCUMENT_NUMBERING_RULE.md` for category codes and rules.

## Version Policy

All documents follow [Semantic Versioning](https://semver.org/) (MAJOR.MINOR.PATCH). See `00_Project_Management/Templates/VERSION_POLICY.md`.

## How to Contribute

1. **Read the governance documents** in `00_Project_Management/`.
2. **Use templates** from `00_Project_Management/Templates/`.
3. **Follow the document lifecycle** — start as Draft, progress through Review to Published.
4. **Cross-reference** — link glossary terms, formula IDs, and related KB articles.
5. **Never delete** — superseded content moves to `99_Archive/`.
6. **Commit discipline** — one logical change per commit; descriptive messages.

## License

See `LICENSE` file.
