# FRKP-EDITORIAL-005 - AI-Assisted Publication Workflow

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-EDITORIAL-005 |
| Document Name | AI-Assisted Publication Workflow |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance; Editorial Workflow |
| Owner | FRKP Publishing Office |
| Plan | PLAN-035E |
| Related Documents | FRKP-PROGRAM-000; FRKP-PROGRAM-001; FRKP-EDITORIAL-003; FRKP-EDITORIAL-004; BUNDLE-007-REVIEW-PACKAGE; PLAN-035A |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |

---

# 1. Purpose

This document establishes the official AI-assisted publication workflow for the FRKP Publishing Program.

The workflow defines provider-neutral responsibilities, stage inputs, stage outputs, completion criteria, review gates, and repository execution responsibilities for AI-assisted publication work.

This document is a governance specification only. It does not implement automation, modify Bundle-007, modify publication contents, change FAEP Foundation artifacts, change standards, change contracts, change the Execution Model, or change the Validation Framework.

---

# 2. Background

Bundle-007 validated an AI-assisted publication workflow using the following provider sequence:

```text
OpenCode
  -> Codex
    -> GPT
      -> Codex
        -> GPT
```

The validated workflow separated authoring, engineering review, review package generation, semantic review, repository application, freeze review, and publication readiness. PLAN-035A produced the engineering review package for GPT review and confirmed that the repository is the only source of truth for publication handoff artifacts.

This document standardizes that validated workflow as a reusable FRKP publication governance pattern.

---

# 3. Workflow Overview

## 3.1 Workflow Diagram

```text
Authoring
  |
  v
Engineering Review
  |
  v
Review Package
  |
  v
Semantic Review
  |
  v
Repository Apply
  |
  v
Freeze Review
  |
  v
Publication
```

## 3.2 Stage Summary

| Stage | Purpose | Primary Output |
| --- | --- | --- |
| Authoring | Produce governed source content or draft publication artifacts within approved scope. | Draft artifacts or candidate governance documents. |
| Engineering Review | Validate repository state, structure, deterministic references, and bounded correction readiness. | Engineering review findings and readiness state. |
| Review Package | Create a structured handoff for semantic, financial, architecture, and publication review. | Review package with reading order, matrices, and open review areas. |
| Semantic Review | Review meaning, domain correctness, traceability suitability, and publication risk. | Semantic review findings and verdict. |
| Repository Apply | Apply approved corrections or approved governance additions to the repository. | Patch-level repository update. |
| Freeze Review | Confirm scope lock, residual conditions, and freeze readiness. | Freeze recommendation or freeze certificate input. |
| Publication | Publish approved frozen content under FRKP publication governance. | Official publication artifact or publication notice. |

---

# 4. Capability Model

Capabilities are stable. Providers are replaceable.

| Capability | Responsibility |
| --- | --- |
| Authoring Capability | Creates draft content, candidate governance documents, review narratives, or publication-ready text within approved scope. |
| Engineering Validation Capability | Verifies branch state, synchronization, file presence, metadata, cross-references, deterministic consistency, and patch safety. |
| Semantic Review Capability | Reviews conceptual coherence, terminology, meaning, assumptions, and unresolved editorial questions. |
| Financial Review Capability | Reviews financial, regulatory, formula, risk, capital, and quantitative claims. |
| Architecture Review Capability | Reviews platform structure, component responsibility, workflow alignment, architecture boundaries, and architecture-impacting conditions. |
| Publication Review Capability | Reviews publication metadata, readiness, reading order, package completeness, navigation, and publication-facing conditions. |
| Freeze Approval Capability | Determines whether scope and content can be frozen, whether residual risks are acceptable, and whether change control can begin. |
| Repository Update Capability | Applies approved repository changes, preserves unrelated work, and records the final repository state. |
| Governance Capability | Maintains plan records, lifecycle state, escalation outcomes, provider-neutral standards, and final workflow verdicts. |

---

# 5. Provider Mapping

Provider mappings are operational assignments, not governance requirements.

Current provider mapping:

| Capability | Current Provider |
| --- | --- |
| Authoring Capability | OpenCode |
| Engineering Validation Capability | Codex |
| Semantic Review Capability | GPT |
| Financial Review Capability | GPT |
| Architecture Review Capability | GPT |
| Publication Review Capability | GPT |
| Repository Update Capability | Codex |
| Freeze Approval Capability | GPT; governance owner |
| Governance Capability | Codex; GPT; FRKP Publishing Office |

Providers may be replaced without changing this workflow. Conformance is based on capability responsibility, review evidence, and gate outcome, not on any specific provider or product.

---

# 6. Inputs / Outputs

## 6.1 Authoring

| Field | Definition |
| --- | --- |
| Input | Approved plan scope, source repository, FRKP governance documents, bundle or publication target, editorial standards, and applicable constraints. |
| Output | Draft source documents, candidate governance documents, or publication draft artifacts. |
| Completion Criteria | Draft artifacts are present, scoped to the approved plan, internally coherent, and ready for repository-safe engineering review. |

## 6.2 Engineering Review

| Field | Definition |
| --- | --- |
| Input | Draft artifacts, repository state, required branch, remote tracking branch, file inventory, deterministic review rules, and approved plan constraints. |
| Output | Engineering review findings, repository verification result, deterministic correction candidates, and readiness status. |
| Completion Criteria | Branch and synchronization are verified, repository is treated as the only source of truth, deterministic findings are documented, and no unrelated files are modified. |

## 6.3 Review Package

| Field | Definition |
| --- | --- |
| Input | Engineering review findings, bundle or publication source documents, prior approved plan context, known open conditions, and review requirements. |
| Output | Structured review package containing summary, reading order, coverage matrices, open review areas, traceability status, and recommended next review. |
| Completion Criteria | Review package is complete enough for semantic, financial, architecture, and publication review without modifying source documents. |

## 6.4 Semantic Review

| Field | Definition |
| --- | --- |
| Input | Review package, source documents, traceability conditions, financial or architecture review needs, and publication readiness criteria. |
| Output | Semantic findings, financial findings when applicable, architecture findings when applicable, publication findings, candidate traceability mappings, and review verdict. |
| Completion Criteria | Findings are explicit, unresolved conditions have owner and review type, and the verdict is GO, CONDITIONAL GO, or NO-GO. |

## 6.5 Repository Apply

| Field | Definition |
| --- | --- |
| Input | Approved semantic review outputs, approved remediation instructions, repository branch, and bounded file scope. |
| Output | Patch-level repository update, updated governance or publication artifacts, and verification record. |
| Completion Criteria | Only approved files are changed, unrelated work is preserved, verification is recorded, and no implementation or release occurs unless separately approved. |

## 6.6 Freeze Review

| Field | Definition |
| --- | --- |
| Input | Applied repository state, review reports, residual condition register, quality gate status, and freeze criteria. |
| Output | Freeze recommendation, residual risk register, change-control readiness, or freeze certificate input. |
| Completion Criteria | Scope is locked or blockers are documented, residual risks are accepted or rejected, and freeze authority can issue a decision. |

## 6.7 Publication

| Field | Definition |
| --- | --- |
| Input | Frozen content, freeze approval, publication authorization, publication metadata, and required indexes. |
| Output | Official publication artifact, publication notice, publication index update, and downstream handoff. |
| Completion Criteria | Publication is authorized by FRKP Publishing Office, published artifacts match the frozen baseline, and downstream consumers are notified. |

---

# 7. Review Gates

## 7.1 Engineering Gate

| Criterion | Requirement |
| --- | --- |
| Branch verification | Required branch is active before work begins. |
| Synchronization verification | Local branch is synchronized with the tracked remote or divergence is explicitly documented. |
| Repository source of truth | Repository documents are the only source of truth. |
| Scope control | Work is limited to the approved plan and bounded files. |
| Deterministic checks | File presence, metadata, links, references, and inventory checks are recorded where applicable. |

## 7.2 Semantic Gate

| Criterion | Requirement |
| --- | --- |
| Conceptual coherence | Claims, definitions, and terminology are internally consistent. |
| Domain correctness | Financial, regulatory, mathematical, and risk claims are reviewed by the appropriate capability. |
| Traceability suitability | KO, CAP, EVD, source, and publication mappings are either approved or recorded as conditions. |
| Review verdict | Review returns GO, CONDITIONAL GO, or NO-GO. |

## 7.3 Publication Gate

| Criterion | Requirement |
| --- | --- |
| Publication readiness | Metadata, related documents, cross-references, reading order, and publication status are reviewable and complete. |
| Quality conditions | Open publication conditions have owners and verification methods. |
| Scope integrity | Publication package does not contain unauthorized content expansion. |
| Authorization readiness | FRKP Publishing Office can authorize or reject publication based on recorded evidence. |

## 7.4 Freeze Gate

| Criterion | Requirement |
| --- | --- |
| Review completion | Required engineering, semantic, financial, architecture, and publication reviews are complete or explicitly waived by governance authority. |
| Residual risk | Residual conditions are accepted, assigned, or rejected. |
| Scope lock | No new content scope remains open. |
| Change control | Post-freeze changes are limited to approved correction classes. |
| Freeze decision | Freeze authority issues GO, CONDITIONAL GO, or NO-GO. |

---

# 8. Deliverables

| Deliverable | Description |
| --- | --- |
| Workflow Diagram | Defines the standard ordered path from Authoring to Publication. |
| Capability Matrix | Assigns responsibilities by capability rather than provider. |
| Provider Mapping | Records current provider assignments while preserving provider replaceability. |
| Review Gates | Defines Engineering, Semantic, Publication, and Freeze gate requirements. |
| Future Runtime Readiness | Defines automation-ready boundaries without implementation. |

---

# 9. Future Runtime Readiness

This workflow is designed to be automation-ready without requiring current implementation.

Future runtime support may include:

| Runtime Area | Candidate Scope |
| --- | --- |
| Workflow Orchestration | Stage routing, handoff state, gate status, and provider assignment records. |
| Repository Validation | Branch, synchronization, file inventory, metadata, cross-reference, and link checks. |
| Review Package Generation | Bounded assembly of review packages from approved source documents and plan context. |
| Review Queue Management | Routing of semantic, financial, architecture, publication, and freeze review items. |
| Evidence Capture | Gate evidence, verdicts, residual conditions, and publication readiness records. |

Future runtime work requires a separate approved plan. This document does not create a CLI, CI job, repository migration, publication release, or automation implementation.

---

# 10. Preservation Statement

This workflow standard does not modify:

- FAEP Foundation.
- Standards.
- Contracts.
- Bundle contents.
- Publication contents.
- Execution Model.
- Validation Framework.
- Bundle-007 source documents.
- Published handbook contents.

No implementation, repository migration, publication edit, release, or freeze action was performed by this document.

---

# 11. Final Verdict

GO — AI-Assisted Publication Workflow Standard Established

---

# 12. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial AI-Assisted Publication Workflow standard created by PLAN-035E |
