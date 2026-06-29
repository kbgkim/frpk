# FAEP-CAP-000 — Capability Discovery Guide

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-CAP-000 |
| Document Name | Capability Discovery Guide |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-CAP-001; FAEP-FOUNDATION-000; FAEP-FOUNDATION-001; FAEP-VALIDATION-000; FAEP-VALIDATION-001; FAEP-CONTRACT-000; FAEP-CONTRACT-001; FRKP-003; FRKP-004; FRKP-005; PLAN-016; PLAN-020 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-020 |

---

# 1. Purpose

This guide defines the process for discovering Candidate Capabilities from FAEP Reference Implementations.

FAEP Foundation v1.0 has been declared frozen. Future Foundation evolution must originate from validated Reference Implementations. Capability Discovery is the mechanism by which existing implementation patterns are identified, documented, and classified before any standardization effort.

**Capabilities must be discovered, not designed.**

---

# 2. Capability Discovery Philosophy

## 2.1 Extraction, Not Invention

A capability is eligible for discovery only if it is already demonstrated by an actual Reference Implementation. Speculative, theoretical, or aspirational capabilities are explicitly excluded from the Candidate Capability Registry.

## 2.2 Evidence-Backed Classification

Every Candidate Capability entry must reference at least one concrete implementation in FRKC, FRKP, or Risk Platform. The evidence may reference specific documents, code modules, workflows, or governance artifacts that demonstrate the capability's existence.

## 2.3 Multi-Source Validation Preference

Capabilities demonstrated by multiple Reference Implementations receive higher validation priority. Single-source capabilities are recorded as Candidates but flagged for cross-program validation before any Capability Standard can be created.

## 2.4 Foundation Preservation

Capability Discovery does not modify the FAEP Foundation. No Core Contracts, Standards, Specifications, frozen artifacts, or repository structure shall be altered during discovery.

---

# 3. Capability Domains

Capabilities are grouped into five domains:

| Domain | Code | Description |
| --- | --- | --- |
| Knowledge | KNW | Capabilities related to canonical knowledge storage, evidence, ontology, terminology, cross-references, metadata, and knowledge versioning |
| Publishing | PUB | Capabilities related to document authoring, publication lifecycle, bundle management, navigation, and evidence-driven publishing workflows |
| Execution | EXE | Capabilities related to formula compilation, runtime execution, determinism, execution modes, governance guards, and computational workflows |
| Governance | GOV | Capabilities related to planning, architecture decisions, contract lifecycle, validation frameworks, standards management, and program governance |
| AI-Ready | AI | Capabilities related to AI agent orchestration, session management, RAG corpus preparation, semantic retrieval, context assembly, and machine-readable citations |

---

# 4. Classification Criteria

## 4.1 Candidate Capability

A capability qualifies as a Candidate Capability when:

- It is implemented in at least one Reference Implementation (FRKC, FRKP, or Risk Platform).
- It is documented with sufficient detail to identify the capability's boundary.
- The implementation evidence is accessible and verifiable.
- The capability is not already fully specified by a FAEP Core Contract or Standard.

## 4.2 Backlog Capability

A capability qualifies as a Backlog Capability when:

- It is described in Foundation or architecture documents but not yet implemented in any Reference Implementation.
- It is observed in a single Reference Implementation but the pattern is speculative or the implementation is incomplete.
- It is aspirational (future phase) with no current implementation evidence.

## 4.3 Excluded

The following are not registered as capabilities:

- Foundation Core Contracts (already standardized).
- FAEP Standards (already standardized).
- Implementation-specific internal patterns with no cross-program relevance.
- Capabilities that would duplicate existing Core Contracts or Standards.

---

# 5. Discovery Process

```
Reference Implementation
    → Capability Observation
    → Evidence Collection
    → Domain Classification
    → Provider / Consumer Mapping
    → Overlap Analysis
    → Candidate Registration (FAEP-CAP-001)
    → Validation Priority Assignment
```

### Stage 1: Observation

Identify a pattern, process, or feature demonstrated by a Reference Implementation that is not fully specified by a FAEP Core Contract or Standard.

### Stage 2: Evidence Collection

Document the implementation evidence: specific files, modules, workflows, governance artifacts, or code that demonstrate the capability.

### Stage 3: Classification

Assign the capability to one of the five domains. If cross-domain, record the primary domain and secondary domains.

### Stage 4: Provider / Consumer Mapping

Identify which Reference Implementation(s) provide the capability and which consume it.

### Stage 5: Overlap Analysis

Compare against existing Candidate Capabilities and Core Contracts to identify:
- Exact duplicates (merge or eliminate).
- Partial overlaps (note relationship).
- Hierarchical relationships (parent/child capability).

### Stage 6: Registration

Record the capability in FAEP-CAP-001 with all required metadata.

### Stage 7: Priority Assignment

Assign validation priority based on cross-program relevance, maturity, and strategic importance.

---

# 6. Registry Rules

| Rule | Description |
| --- | --- |
| CR-001 | Capability IDs follow the pattern CAP-{DOMAIN}-{NNN} |
| CR-002 | IDs are assigned sequentially within each domain |
| CR-003 | Capability entries are immutable once registered (status may change) |
| CR-004 | A capability may be reclassified from Candidate to Backlog if evidence proves insufficient |
| CR-005 | A capability may be promoted to Capability Standard only through a future PLAN |
| CR-006 | No Capability Standard shall be created in the same PLAN that discovers the capability |

---

# 7. Relationship to FAEP Contract Lifecycle

Candidate Capabilities are a separate concern from Candidate Contracts (FAEP-CONTRACT-001).

| Artifact | Purpose | Lifecycle |
| --- | --- | --- |
| Candidate Contract | Contract proposal for cross-program validation | FAEP-CONTRACT-000 |
| Candidate Capability | Discovered implementation pattern | FAEP-CAP-000 / FAEP-CAP-001 |

A Candidate Capability may inform a future Candidate Contract, but the two registries are independent. Capability Discovery identifies what implementations *can do*. Contract proposals define how implementations *shall interoperate*.

---

# 8. Validation Priority Model

| Priority | Criteria |
| --- | --- |
| P1 — Critical | Demonstrated in 2+ Reference Implementations; high cross-program relevance; gap in Core Contracts |
| P2 — High | Demonstrated in 1 implementation; high cross-program potential; clear boundary |
| P3 — Medium | Demonstrated in 1 implementation; medium cross-program relevance |
| P4 — Low | Single implementation; narrow scope; speculative cross-program value |

---

# 9. Preservation Statement

FAEP-CAP-000 does not modify:
- FAEP Foundation v1.0 frozen artifacts.
- FAEP Core Contracts (CC-*).
- FAEP Standards (FAEP-STD-000 through FAEP-STD-006).
- FAEP Specifications (FRKP-003, FRKP-004, FRKP-005).
- FAEP Governance documents (FAEP-000, FAEP-001, FAEP-002).
- FAEP ADR Registry (FAEP-ADR-000).
- FAEP Contract Governance (FAEP-CONTRACT-000, FAEP-CONTRACT-001).
- FAEP Validation Framework (FAEP-VALIDATION-000, FAEP-VALIDATION-001).
- FAEP Foundation Governance (FAEP-FOUNDATION-000, FAEP-FOUNDATION-001, FAEP-FOUNDATION-002).
- Bundle structure or repository layout.

FAEP-CAP-000 does not perform:
- Implementation.
- Code.
- Repository migration.
- Commits.
- Releases.

---

# 10. Cross-References

| Reference | Relationship |
| --- | --- |
| FAEP-CAP-001 | Candidate Capability Registry — records all discovered capabilities |
| FAEP-FOUNDATION-001 | Foundation Evolution Policy — three-layer architecture for capability validation |
| FAEP-VALIDATION-000 | Reference Implementation Validation Framework — validation methodology |
| FAEP-VALIDATION-001 | Reference Implementation Score Model — capability maturity evaluation |
| FAEP-CONTRACT-000 | Contract Lifecycle Standard — separate but related lifecycle |
| FAEP-CONTRACT-001 | Candidate Contract Registry — separate registry for contract proposals |
| PLAN-020 | Capability Discovery plan that created this guide and registry |

---

# Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Capability Discovery Guide created by PLAN-020 |
