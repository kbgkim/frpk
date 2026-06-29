# FAEP-STD-000 - Standard Catalog

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-STD-000 |
| Document Name | Standard Catalog |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-000; FAEP-001; FAEP-002; FRKP-004; FAEP-STD-001; FAEP-STD-002; FAEP-STD-003; FAEP-STD-004; FAEP-STD-005; FAEP-STD-006; FAEP-ADR-000 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-015 |

---

# 1. Purpose

This document is the official FAEP Standard Catalog. It defines the hierarchy, taxonomy, ownership, lifecycle, and relationship model for all FAEP Standards.

FAEP Standards are platform-level governance rules reusable by every FAEP-conformant project. FRKP standards remain valid as the first Reference Implementation, but platform-wide rules are governed here.

---

# 2. Standard Hierarchy

| Level | Artifact Type | Authority | Scope |
| --- | --- | --- | --- |
| L0 | Program Charter and Governance | FAEP Program Governance Board | Program mission, authority, and program-level governance |
| L1 | FAEP Core Specification | FAEP Architecture Board | Platform contracts, engines, and conformance model |
| L2 | FAEP Standards | FAEP Architecture Board | Reusable governance rules for all programs |
| L3 | Platform Specifications | Platform Project Governance | Platform-specific application of Core contracts and Standards |
| L4 | Reference Implementations | Platform Project Governance | Concrete implementation patterns and validation evidence |
| L5 | Project Procedures | Project Lead | Local operating procedures that do not redefine standards |

Hierarchy rule: lower levels may specialize higher levels but may not weaken or contradict them.

---

# 3. Standard Taxonomy

| Standard ID | Title | Domain | Primary Source | Classification |
| --- | --- | --- | --- | --- |
| FAEP-STD-001 | Document Identification Standard | Identification; Versioning | FRKP-ID-001; FAEP-002 | FAEP Core Standard |
| FAEP-STD-002 | Bundle Standard | Bundle Lifecycle | FRKP-BUNDLE-001; FRKP-004 | FAEP Core Standard |
| FAEP-STD-003 | Evidence Standard | Evidence; Traceability | FRKP-FRKC-001; FRKP-005; FAEP-002 | FAEP Core Standard |
| FAEP-STD-004 | Navigation and Cross-Reference Standard | Navigation; Links; Knowledge Graph | FRKP-DOC-001; FRKP-005 | FAEP Core Standard |
| FAEP-STD-005 | Architecture Decision Standard | Architecture Governance | FRKP-004; FAEP-002; previous plans | FAEP Core Standard |
| FAEP-STD-006 | Release and Freeze Standard | Release; Freeze; Versioning | FRKP-FREEZE-001; FRKP-004; FAEP-002 | FAEP Core Standard |
| FAEP-ADR-000 | Architecture Decision Registry | ADR Registry | PLAN-011 through PLAN-014; FRKP-004; FRKP-005 | FAEP Core Registry |

---

# 4. Standard Ownership

| Role | Responsibility |
| --- | --- |
| FAEP Program Governance Board | Approves new standard domains and resolves standard conflicts |
| FAEP Architecture Board | Owns standard content, standard lifecycle, and architecture alignment |
| Domain Governance Bodies | Propose and maintain domain-specific standard details |
| Platform Project Governance | Applies standards in platform-specific specifications |
| Reference Implementation Owners | Provide validation feedback without redefining FAEP Standards |

Ownership rule: a Reference Implementation may propose standard changes, but FAEP Architecture Board owns approval.

---

# 5. Standard Lifecycle

```text
Proposed -> Draft -> Active -> Frozen -> Superseded -> Archived
```

| State | Meaning | Exit Authority |
| --- | --- | --- |
| Proposed | Standard need identified | FAEP Architecture Board |
| Draft | Standard text under review | FAEP Architecture Board |
| Active | Standard approved for FAEP-wide use | FAEP Architecture Board |
| Frozen | Standard baseline locked for a release or milestone | Release Council |
| Superseded | Replaced by a newer standard or version | FAEP Architecture Board |
| Archived | Retained for audit and historical traceability | FAEP Program Governance Board |

Lifecycle rules:

- Every standard has a Document ID, version, owner, status, related documents, creation date, and revision history.
- Active standards are normative for FAEP-conformant projects.
- Frozen standards are immutable within the frozen baseline.
- Superseded standards remain traceable and must identify the replacement.

---

# 6. Standards, Specifications, and Reference Implementations

| Artifact | Role | Example |
| --- | --- | --- |
| Standard | Defines reusable governance rules | FAEP-STD-002 Bundle Standard |
| Specification | Defines platform contracts and required behavior | FRKP-004 FAEP Core Platform Specification |
| Reference Implementation | Demonstrates and validates standards and specifications | FRKP governance standards and Bundle-007 process |

Relationship rules:

1. Standards define reusable rules.
2. Specifications define platform contracts that may require one or more standards.
3. Reference Implementations demonstrate how standards and specifications work in practice.
4. Implementation details discovered in a Reference Implementation do not become FAEP rules until elevated into a FAEP Standard.
5. FRKP-specific rules remain in FRKP unless they are explicitly generalized into FAEP Standards.

---

# 7. Classification Summary

| Source Rule Area | Classification | Reason |
| --- | --- | --- |
| Unique, stable document IDs | FAEP Core Standard | Applies to every project and enables traceability |
| FRKP layer prefixes RL, KB, AN, FC, MF, IMP, ARCH | FRKP-specific | These are publishing-layer conventions of FRKP |
| Bundle lifecycle and freeze gates | FAEP Core Standard | Reusable delivery governance across knowledge work |
| Operational risk Bundle-007 numbering | FRKP-specific | Historical bundle sequence must be preserved, not generalized |
| Evidence registration, mapping, certification | FAEP Core Standard | Required by Knowledge, Evidence, Document, and Release contracts |
| FRKC canonical knowledge ownership | FRKC-specific with FAEP dependency | FRKC is the canonical knowledge platform, but corpus operations remain FRKC-owned |
| Architecture decision records | FAEP Core Standard | Required for Core Contract and platform architecture governance |
| Risk formula implementation rules | Risk Platform-specific | Computation details belong to the Risk Platform |
| Business platform domain rules | Business Platform-specific | Business domain policies are consumer-platform concerns |

---

# 8. Catalog Governance

The catalog is updated when:

- A new FAEP Standard is created.
- A standard changes status.
- A standard is superseded.
- A new reference implementation validates or challenges a standard.
- A program phase introduces a new governance domain.

---

# 9. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Standard Catalog created by PLAN-015 |
