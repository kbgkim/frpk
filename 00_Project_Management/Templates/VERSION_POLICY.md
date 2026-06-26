# Version Policy

## Document Information
| Field | Value |
|---|---|
| Document ID | FRKP-VP-001 |
| Status | Approved |
| Version | v1.0.0 |
| Last Updated | YYYY-MM-DD |
| Owner | Project Architect |

## Scheme

All documents follow [Semantic Versioning](https://semver.org/):

```
MAJOR.MINOR.PATCH
```

| Component | When to increment | Example |
|---|---|---|
| MAJOR | Breaking changes, restructure, new volume | 2.0.0 |
| MINOR | New content, significant additions | 1.3.0 |
| PATCH | Corrections, formatting, minor edits | 1.0.4 |

## Version Lifecycle

| Version Range | Typical Status | Meaning |
|---|---|---|
| 0.x.x | Draft / Review | Pre-release, may change significantly |
| 1.x.x | Approved / Frozen | First stable release |
| 1.x.x+ | Published | Released, immutable |
| 2.x.x | Approved / Frozen / Published | Major revision |

## Version in Filename

```
FRKP-KB-0001_v1.2.3.md
```

## Repository-Level Versioning

The repository itself follows the same scheme. The current version is maintained in:

- `VERSION` file at repository root (if automated builds require it)
- `CHANGELOG.md` release history
- Git tags: `v1.0.0`, `v1.1.0`, etc.

## Breaking Change Policy

- MAJOR version bumps require documented rationale in CHANGELOG.
- Breaking changes to document numbering or structure require approval.
- Superseded documents are archived, not deleted.

## Change History
| Date | Version | Author | Change |
|---|---|---|---|
| YYYY-MM-DD | v1.0.0 | | Initial version policy |
