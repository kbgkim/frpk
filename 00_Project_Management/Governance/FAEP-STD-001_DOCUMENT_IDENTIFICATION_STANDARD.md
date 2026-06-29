# FAEP-STD-001 - Document Identification Standard

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-STD-001 |
| Document Name | Document Identification Standard |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-STD-000; FAEP-002; FRKP-ID-001; FRKP-DOC-001 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-015 |

---

# 1. Purpose

This standard defines the FAEP-wide policy for document IDs, program IDs, project IDs, bundle IDs, evidence IDs, architecture IDs, version policy, naming conventions, reserved namespaces, and migration rules.

---

# 2. Identification Principles

| Principle | Rule |
| --- | --- |
| Uniqueness | An ID is unique within its namespace and registry. |
| Stability | Once assigned, an ID is not renamed or reused. |
| Readability | The prefix identifies artifact type or governance domain. |
| Machine-readability | IDs use predictable ASCII tokens and numeric sequences. |
| Backward compatibility | Existing FRKP IDs and Bundle IDs are preserved. |

---

# 3. Document ID Policy

Canonical FAEP document IDs use:

```text
<NAMESPACE>-<CATEGORY>-<NUMBER>
```

or, for top-level program documents:

```text
<NAMESPACE>-<NUMBER>
```

Examples:

```text
FAEP-000
FAEP-STD-001
FAEP-ADR-000
FRKP-ID-001
RL-170
BUNDLE-007
```

Document ID rules:

- The Document ID in the document metadata must match the file identifier.
- Renaming a file does not rename the document ID.
- A document ID may be superseded but not reused.
- Frozen document IDs are immutable.

---

# 4. Program ID

FAEP Program IDs use:

```text
Program-NNN
```

Reserved program ranges:

| Range | Reserved For |
| --- | --- |
| Program-000 | FAEP Core |
| Program-100 | Knowledge Platform |
| Program-200 | Publishing Platform |
| Program-300 | Risk Platform |
| Program-400 | AI Platform |
| Program-500 | Business Platforms |

---

# 5. Project ID

Project IDs use an uppercase project namespace.

| Project Type | Pattern | Example |
| --- | --- | --- |
| Program core | FAEP | FAEP-STD-001 |
| Knowledge platform | FRKC | FRKC-KNW-001 |
| Reference implementation | FRKP | FRKP-ID-001 |
| Risk platform | RISK | RISK-FML-001 |
| Business platform | Project-specific namespace | IB-ARCH-001 |

Project namespaces require FAEP Program Governance approval before first use.

---

# 6. Bundle ID

Bundle IDs use:

```text
BUNDLE-NNN
```

Rules:

- Bundle IDs are sequential within the owning platform.
- Bundle IDs are never reused.
- Existing FRKP Bundle IDs are preserved unchanged.
- Cross-project references include the project context when ambiguity is possible, for example `FRKP:BUNDLE-007`.

---

# 7. Evidence ID

Evidence IDs use:

```text
EVD-NNNNNN
```

Rules:

- Evidence IDs are globally unique within the owning evidence registry.
- Cross-repository evidence references include the evidence authority when needed.
- Certified evidence IDs are immutable.
- Superseded evidence keeps its original ID and points to the replacement.

---

# 8. Architecture ID

Architecture decisions use:

```text
FAEP-ADR-NNN
```

Platform-local architecture decisions may use:

```text
<PROJECT>-ADR-NNN
```

Rules:

- FAEP-wide architecture decisions are registered in FAEP-ADR-000.
- Local ADRs that affect Core contracts must be elevated or linked to a FAEP ADR.
- Historical `AD-NNN` IDs from previous plans are preserved and mapped into the registry.

---

# 9. Version Policy

All governed artifacts use semantic versioning:

```text
MAJOR.MINOR.PATCH
```

| Segment | Use |
| --- | --- |
| MAJOR | Breaking structure, contract, or governance change |
| MINOR | Additive non-breaking change |
| PATCH | Correction, clarification, or typo fix |

Version rules:

- Frozen artifacts require a new version for any substantive change.
- Compatibility between platforms must be explicitly documented.
- Dependency versions must be explicit, not implicit.

---

# 10. Naming Convention

Files use:

```text
<DOCUMENT_ID>_<UPPERCASE_NAME_WITH_UNDERSCORES>.md
```

Rules:

- Use ASCII uppercase tokens and underscores.
- Keep the ID at the beginning of the filename.
- Keep markdown as the source of truth.
- Avoid YAML front matter unless a future FAEP standard explicitly authorizes it.

---

# 11. Reserved Namespaces

| Namespace | Reserved For |
| --- | --- |
| FAEP | Program governance and Core standards |
| FAEP-STD | FAEP Standards |
| FAEP-ADR | FAEP Architecture Decisions |
| Program | Program entities |
| PLAN | Planning records |
| CC | Core Contracts |
| EVD | Evidence records |
| BUNDLE | Bundle records |
| FRKC | Knowledge platform |
| FRKP | Reference implementation |
| RISK | Risk Platform |
| IB | Investment Banking Business Platform |

New namespaces require approval by the FAEP Program Governance Board.

---

# 12. Migration Rules

| Rule | Requirement |
| --- | --- |
| MIG-001 | Do not rename existing frozen artifacts. |
| MIG-002 | Do not renumber existing FRKP documents or Bundle IDs. |
| MIG-003 | Map legacy identifiers to FAEP identifiers through registries. |
| MIG-004 | Preserve link conventions during migration. |
| MIG-005 | Record every migration decision in an ADR or plan. |

---

# 13. Classification

| Rule | Classification | Reason |
| --- | --- | --- |
| Unique, stable IDs | FAEP Core Standard | Required by all traceability chains |
| FRKP governance namespace | FRKP-specific | Local project namespace remains valid but not universal |
| RL/KB/AN/FC/MF/IMP/ARCH prefixes | FRKP-specific | Publishing Reference Implementation layers |
| Program-NNN model | FAEP Core Standard | Defined by FAEP roadmap |
| EVD ID model | FAEP Core Standard | Required by Evidence Engine |
| Business domain namespaces | Business Platform-specific | Allocated per consumer platform |

---

# 14. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Document Identification Standard created by PLAN-015 |
