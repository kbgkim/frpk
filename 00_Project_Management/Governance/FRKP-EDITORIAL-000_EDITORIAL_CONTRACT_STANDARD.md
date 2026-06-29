# FRKP-EDITORIAL-000 - Editorial Contract Standard

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-EDITORIAL-000 |
| Document Name | Editorial Contract Standard |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance |
| Owner | FRKP Publishing Office |
| Plan | PLAN-026 |
| Related Documents | FAEP-STD-001; FAEP-STD-002; FAEP-STD-003; FAEP-STD-004; FRKP-PROGRAM-002; FRKP-PROGRAM-004; FRKP-FRKC-001; FRKP-PUB-001 |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |

---

# 1. Purpose

This standard defines the Editorial Contract model for FRKP publication governance.

An Editorial Contract is a reusable editorial rule that can be applied across bundles, documents,
publication volumes, and review artifacts. Editorial Contracts convert recurring editorial findings
into named, classifiable, and executable validation units.

---

# 2. Scope

Editorial Contracts apply to:

- FRKP source documents.
- Bundle review documents.
- Handbook publication artifacts.
- Repository indexes and navigation records.
- Evidence, capability, and knowledge traceability blocks.
- Editorial review and publication quality gate preparation.

Editorial Contracts do not replace FAEP Standards, FRKP standards, Core Contracts, frozen
artifacts, or publication content. They operationalize existing rules for repeatable validation.

---

# 3. Source Standards

| Source | Governing Rule Used by Editorial Contracts |
| --- | --- |
| FAEP-STD-001 | Stable identifiers, naming, evidence ID format, version policy |
| FAEP-STD-002 | Bundle lifecycle, metadata, review checks, evidence baseline |
| FAEP-STD-003 | Evidence lifecycle, traceability chain, evidence integrity |
| FAEP-STD-004 | Navigation, cross-references, semantic links, machine-readable maps |
| FRKP-PROGRAM-002 | Editorial structure, traceability blocks, navigation, references |
| FRKP-PROGRAM-004 | Quality gate dimensions and PASS/FAIL criteria |
| FRKP-FRKC-001 | Evidence-driven publishing workflow and role split |
| FRKP-PUB-001 | Knowledge object and capability mapping model |
| FRKP-005 | Knowledge object contracts and evidence-anchored knowledge model |
| FAEP-CAP-001 | Candidate capability registry and CAP identifier authority |

---

# 4. Contract Definition

Each Editorial Contract shall define:

| Field | Requirement |
| --- | --- |
| Contract ID | Stable ID in the form EC-NNN |
| Name | Short human-readable rule name |
| Purpose | The editorial risk or repeatable decision the contract controls |
| Scope | Artifact types and repository areas covered |
| Applicability | Conditions under which the contract is active |
| Classification | One or more contract classes from Section 5 |
| PASS Criteria | Deterministic or reviewable conditions for success |
| FAIL Criteria | Conditions that cause failure |
| Severity | Blocking, Required, Advisory, or Informational |
| Automatic Resolution | Yes or No |
| Requires GPT Review | Yes or No |
| Automation Class | AUTO, SEMI-AUTO, or MANUAL |
| Validation Level | Level-0 through Level-5 from FRKP-EDITORIAL-002 |
| Source Standards | Standards or governance documents that authorize the contract |

---

# 5. Contract Classification

| Classification | Meaning |
| --- | --- |
| Deterministic | Can be checked by repository parsing, identifier matching, or link validation |
| Semantic | Requires meaning-aware assessment of relationship appropriateness |
| Architectural | Validates consistency with architecture, lifecycle, bundle, or platform model |
| Knowledge | Validates knowledge object, ontology, or canonical source references |
| Publication | Validates publishing structure, navigation, readiness, and reader-facing completeness |
| Governance | Validates registry, index, lifecycle, approval, or standards alignment |

Contracts may have multiple classifications. The primary classification is the one that determines
validation ownership.

---

# 6. Severity Model

| Severity | Meaning | Default Gate Impact |
| --- | --- | --- |
| Blocking | Publication, freeze, or release cannot proceed | FAIL |
| Required | Must be resolved for publication readiness | CONDITIONAL PASS or FAIL |
| Advisory | Improves quality but does not block readiness | PASS with observation |
| Informational | Records context for future automation or review | No gate impact |

---

# 7. Automation Classes

| Automation Class | Meaning |
| --- | --- |
| AUTO | Codex/OpenCode can validate and resolve using deterministic repository edits |
| SEMI-AUTO | Tooling can detect or scaffold resolution, but GPT or human judgment confirms content |
| MANUAL | Requires GPT review, domain review, or governance decision before resolution |

Automatic resolution is separate from deterministic validation. A contract may be deterministically
validated but still require manual or GPT review to decide the correct content.

---

# 8. Validation Determinism

| Validation Type | Description | Examples |
| --- | --- | --- |
| Deterministic | Same repository state always produces same result | Link exists, ID format valid, index entry present |
| Bounded Semantic | Candidate references can be checked against registries, but correctness needs review | CAP or KO relevance to section content |
| Expert Semantic | Domain, architecture, or publication judgment is required | Evidence appropriateness, editorial readiness |

---

# 9. Editorial Contract Lifecycle

Editorial Contracts follow this lifecycle:

```text
Observed Finding -> Rule Extracted -> Candidate Contract -> Registered Contract
-> Validation Model Mapping -> Automated Execution Candidate -> Active Gate Rule
```

Lifecycle rules:

- A recurring issue shall be translated into a rule before repeated manual correction.
- A contract shall cite the standard or governance source that authorizes it.
- Candidate contracts may be registered before full automation exists.
- Contract creation shall not modify the artifacts that triggered the finding.
- Resolution work shall be performed by a later plan that executes the contracts.

---

# 10. Preservation Commitment

This standard does not modify:

- FAEP Foundation.
- Core Contracts.
- Existing Standards.
- Bundle-007 content.
- Frozen artifacts.
- Publication content.

This standard defines reusable editorial governance only.

---

# 11. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Editorial Contract Standard created by PLAN-026 |
