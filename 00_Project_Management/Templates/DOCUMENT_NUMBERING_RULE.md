# Document Numbering Rule

## Document Information
| Field | Value |
|---|---|
| Document ID | FRKP-DNR-001 |
| Status | Approved |
| Version | v1.0.0 |
| Last Updated | YYYY-MM-DD |
| Owner | Project Architect |

## Scheme

Layer documents follow the numbering pattern:

```
[PREFIX]-[SEQUENCE]_[TITLE].md
```

Project-management governance documents may use:

```
FRKP-[CATEGORY]-[SEQUENCE]_[TITLE].md
```

| Component | Description | Example |
|---|---|---|
| PREFIX | Layer prefix | RL, KB, AN, FC, MF, IMP, ARCH, BUNDLE |
| CATEGORY | Governance category code when using `FRKP-` | DNR, GOV, RMAP |
| SEQUENCE | Zero-padded sequence number | 001 |
| TITLE | Uppercase descriptive title | FINANCIAL_RISK_OVERVIEW |

## Category Codes

| Code | Folder | Description |
|---|---|---|
| INDEX | 00 | Project Index |
| RMAP | 00/Roadmap | Roadmap |
| BLOG | 00/Backlog | Backlog |
| CUR | 00/CurrentWork | Current work status |
| CLOG | 00 | Changelog |
| SPR | 00/Sprint | Sprint status |
| DNR | 00 | Document numbering rules |
| DSR | 00 | Document status rules |
| VP | 00 | Version policy |
| RCHK | 00/Reviews | Review checklist |
| GOV | 00/Governance | Governance document |
| RL | 01 | Reference Library entry |
| KB | 02 | Knowledge Base article |
| AN | 03 | Analysis document |
| FC | 04 | Formula Catalog entry |
| MF | 05 | Mathematical Foundation document |
| IMP | 06 | Implementation Guide document |
| ARCH | 07 | Architecture document |
| BUNDLE | 08 | Bundle review document |
| AST | 09 | Asset |
| GLOSS | 10 | Glossary term |
| VOL | 11 | Volume |
| VOLCH | 11 | Volume chapter |
| APX | 12 | Appendix entry |

## Version Numbering in Filename
For documents with multiple versions, append `_v{major}.{minor}.{patch}`:

```
KB-201_FINANCIAL_RISK_OVERVIEW_v1.0.0.md
```

## Change History
| Date | Version | Author | Change |
|---|---|---|---|
| YYYY-MM-DD | v1.0.0 | | Initial numbering rule |
