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

All documents follow the numbering pattern:

```
FRKP-[CATEGORY]-[SEQUENCE]
```

| Component | Description | Example |
|---|---|---|
| FRKP | Fixed project prefix | FRKP |
| CATEGORY | 3–4 letter category code | KB, VOL, FML, GLOSS |
| SEQUENCE | Zero-padded 4-digit number | 0001 |

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
| REF | 01 | Reference entry |
| KB | 02 | Knowledge Base article |
| FML | 03 | Formula catalog entry |
| GLOSS | 04 | Glossary term |
| VOL | 05 | Volume |
| VOLCH | 05 | Volume chapter |
| ARCH | 06 | Architecture document |
| APX | 07 | Appendix entry |
| AST | 09 | Asset |

## Version Numbering in Filename
For documents with multiple versions, append `_v{major}.{minor}.{patch}`:

```
FRKP-KB-0001_v1.0.0.md
```

## Change History
| Date | Version | Author | Change |
|---|---|---|---|
| YYYY-MM-DD | v1.0.0 | | Initial numbering rule |
