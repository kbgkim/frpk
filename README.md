# Financial Risk Knowledge Platform (FRKP)

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](README.md) > [Home](README.md) > [Repository README](README.md)

---

## Navigation

### Parent Repository

None

### Sibling Layers

- [Reference Library](01_Reference_Library/README.md)
- [Knowledge Base](02_Knowledge_Base/README.md)
- [Analysis](03_Analysis/README.md)
- [Mathematical Foundation](05_Mathematical_Foundation/README.md)
- [Formula Catalog](04_Formula_Catalog/README.md)
- [Implementation Guide](06_Implementation_Guide/README.md)
- [Architecture Guide](07_Architecture/README.md)
- [Bundle Review](08_Bundles/README.md)

### Bundle List

- [BUNDLE-001](08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md)
- [BUNDLE-002](08_Bundles/BUNDLE-002_FRTB_REVIEW.md)
- [BUNDLE-003](08_Bundles/BUNDLE-003_IFRS9_REVIEW.md)
- [BUNDLE-004](08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md)
- [BUNDLE-005](08_Bundles/BUNDLE-005_CVA_REVIEW.md)
- [BUNDLE-006](08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)

### Related Standards

- [FRKP-DOC-100](00_Project_Management/Governance/FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md)
- [FRKP-DOC-001](00_Project_Management/Governance/Standards/FRKP-DOC-001_DOCUMENT_STANDARD.md)
- [FRKP-ID-001](00_Project_Management/Governance/Standards/FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md)
- [FRKP-BUNDLE-001](00_Project_Management/Governance/Standards/FRKP-BUNDLE-001_BUNDLE_STANDARD.md)
- [FRKP-FORM-001](00_Project_Management/Governance/Standards/FRKP-FORM-001_FORMULA_STANDARD.md)
<!-- FRKP-NAV-END -->

## Vision
A comprehensive, authoritative, and well-governed knowledge platform covering financial risk management — from foundational concepts to advanced quantitative methods, regulatory frameworks, and risk engine architecture.

## Objectives
1. **Single Source of Truth** — All financial risk knowledge curated in one governed repository.
2. **Rigorous Governance** — Every document follows a defined lifecycle: Draft → Review → Approved → Frozen → Published.
3. **Cross-Referenced** — Glossary terms, formulas, knowledge articles, and volumes are fully interconnected.
4. **Extensible** — Designed for 500–1000 Markdown documents across the frozen top-level repository structure.
5. **Project-Managed** — Work is organized by Epic → Feature → Sprint → Task → Deliverable.
6. **Audit-Ready** — Full version history, decision logs, and archival of superseded content.

## Repository Structure

```
FRKP/
├── 00_Project_Management/    Governance, planning, templates
├── 01_Reference_Library/     External references and citations
├── 02_Knowledge_Base/        Risk knowledge articles
├── 03_Analysis/              Analysis and insights
├── 04_Formula_Catalog/       Formulas, models, notation
├── 05_Mathematical_Foundation/  Mathematical derivations and proofs
├── 06_Implementation_Guide/  Implementation guidance and examples
├── 07_Architecture/          Risk engine design documentation
├── 08_Bundles/               Thematic content bundles
├── 09_Assets/                Images, diagrams, style files
├── 10_Glossary/              Terminology and definitions (planned)
├── 11_Volumes/               Long-form risk volumes (planned)
├── 12_Appendix/              Supporting material (planned)
├── 13_Output/                Generated artifacts (planned, gitignored)
└── 99_Archive/               Superseded and historical content
```

## Document Lifecycle

```
Draft → Review → Approved → Frozen → Published
```

Each state has specific transition rules. See `00_Project_Management/Templates/DOCUMENT_STATUS_RULE.md`.

## Document Numbering

Layer documents use the repository layer prefix and sequence:

```
KB-201_FINANCIAL_RISK_OVERVIEW.md
```

Project-management governance documents may use the FRKP governance prefix:

```
FRKP-DNR-001_DOCUMENT_NUMBERING_RULE.md
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
