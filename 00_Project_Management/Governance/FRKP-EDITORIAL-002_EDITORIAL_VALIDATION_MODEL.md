# FRKP-EDITORIAL-002 - Editorial Validation Model

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-EDITORIAL-002 |
| Document Name | Editorial Validation Model |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance |
| Owner | FRKP Publishing Office |
| Plan | PLAN-026 |
| Related Documents | FRKP-EDITORIAL-000; FRKP-EDITORIAL-001; FRKP-PROGRAM-004; FAEP-STD-002; FAEP-STD-003; FAEP-STD-004 |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |

---

# 1. Purpose

This document defines editorial validation levels for executing Editorial Contracts.

The model sequences validation from repository integrity through editorial certification so that
automated checks can run before semantic review and human approval.

---

# 2. Validation Level Summary

| Level | Name | Primary Objective | Typical Automation |
| --- | --- | --- | --- |
| Level-0 | Repository Integrity | Confirm files, IDs, indexes, and repository state are internally consistent | AUTO |
| Level-1 | Navigation | Confirm navigation and related-document paths are present and resolvable | AUTO |
| Level-2 | Traceability | Confirm cross-references and evidence references exist and resolve | AUTO to SEMI-AUTO |
| Level-3 | Knowledge Integrity | Confirm KO and CAP references are valid and semantically appropriate | SEMI-AUTO |
| Level-4 | Publication Readiness | Confirm metadata, bundle integrity, and quality gate inputs are complete | AUTO to MANUAL |
| Level-5 | Editorial Certification | Confirm final editorial verdict and conditions | MANUAL |

---

# 3. Level Definitions

## 3.1 Level-0 - Repository Integrity

| Field | Value |
| --- | --- |
| Purpose | Establish that the repository state can be validated safely and repeatably. |
| Checks | Branch, sync state, file existence, ID/file matching, index synchronization, required registries present. |
| Contracts | EC-008; EC-009 |
| PASS Criteria | Required files exist; governed IDs are stable; indexes reflect known state; no missing registry needed for the run. |
| FAIL Criteria | Required artifact missing; ID mismatch; stale master index for active publication scope. |
| Output | Repository integrity report or index synchronization findings. |

## 3.2 Level-1 - Navigation

| Field | Value |
| --- | --- |
| Purpose | Validate human and AI navigation paths before deeper traceability review. |
| Checks | FRKP-NAV block, breadcrumb, Previous/Next, parent references, Related Documents. |
| Contracts | EC-001; EC-002 |
| PASS Criteria | Navigation structures exist; required links resolve; known bundle peers are represented. |
| FAIL Criteria | Missing navigation block; broken navigation link; required related document omitted. |
| Output | Navigation validation report and deterministic correction candidates. |

## 3.3 Level-2 - Traceability

| Field | Value |
| --- | --- |
| Purpose | Validate explicit document-to-document and document-to-evidence traceability. |
| Checks | Cross References sections, relationship targets, EVD references, evidence authority resolution. |
| Contracts | EC-003; EC-006 |
| PASS Criteria | Required cross-reference and evidence structures exist; IDs follow required patterns; resolvable references are present. |
| FAIL Criteria | Missing required cross-reference section; unresolved EVD ID; unsupported publication claim. |
| Output | Cross-reference and evidence traceability validation report. |

## 3.4 Level-3 - Knowledge Integrity

| Field | Value |
| --- | --- |
| Purpose | Validate semantic mappings to canonical knowledge and capability records. |
| Checks | KO references, CAP references, registry resolution, content appropriateness, source-to-publication alignment. |
| Contracts | EC-004; EC-005 |
| PASS Criteria | KO and CAP references resolve; mappings are appropriate to section content; unsupported mappings are not introduced. |
| FAIL Criteria | Missing required KO or CAP block; malformed or unresolved ID; mapping contradicts content. |
| Output | Candidate mapping report and GPT/human review queue. |

## 3.5 Level-4 - Publication Readiness

| Field | Value |
| --- | --- |
| Purpose | Confirm the bundle or publication package is structurally ready for formal quality gate review. |
| Checks | Bundle deliverables, metadata, lifecycle state, quality gate inputs, deferred items, accepted conditions. |
| Contracts | EC-007; EC-009; EC-010 |
| PASS Criteria | Deliverables and metadata are complete; bundle state is consistent; quality gate can be assessed. |
| FAIL Criteria | Missing deliverable; inconsistent lifecycle state; metadata gaps block quality gate assessment. |
| Output | Publication readiness report. |

## 3.6 Level-5 - Editorial Certification

| Field | Value |
| --- | --- |
| Purpose | Produce the final editorial verdict after lower-level validations and semantic reviews are complete. |
| Checks | Quality gate verdicts, conditions, residual risks, approval readiness. |
| Contracts | EC-010 |
| PASS Criteria | Required lower-level contracts pass or have accepted conditions; reviewers can issue PASS or CONDITIONAL PASS. |
| FAIL Criteria | Critical contract fails; unresolved required condition lacks owner or verification path. |
| Output | Editorial certification verdict. |

---

# 4. Contract-to-Level Matrix

| Contract | Level-0 | Level-1 | Level-2 | Level-3 | Level-4 | Level-5 |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| EC-001 Navigation |  | X |  |  |  |  |
| EC-002 Related Documents |  | X | X |  |  |  |
| EC-003 Cross References |  |  | X |  |  |  |
| EC-004 Capability References |  |  |  | X | X |  |
| EC-005 Knowledge Object References |  |  |  | X | X |  |
| EC-006 Evidence References |  |  | X | X | X |  |
| EC-007 Bundle Integrity | X |  |  |  | X |  |
| EC-008 Master Index Synchronization | X |  |  |  | X |  |
| EC-009 Publication Metadata | X |  |  |  | X |  |
| EC-010 Editorial Readiness |  |  |  |  | X | X |

---

# 5. Execution Order

Editorial validation shall run in this order:

1. Level-0 Repository Integrity.
2. Level-1 Navigation.
3. Level-2 Traceability.
4. Level-3 Knowledge Integrity.
5. Level-4 Publication Readiness.
6. Level-5 Editorial Certification.

Execution rules:

- Later levels should not modify earlier-level facts without rerunning the affected level.
- AUTO contracts should run before SEMI-AUTO or MANUAL contracts.
- SEMI-AUTO contracts may produce candidate mappings but shall not certify semantic correctness.
- MANUAL contracts shall record reviewer, condition, and verification method.

---

# 6. PLAN-026 Validation Use

PLAN-026 establishes the validation model only. It does not execute Bundle-007 P2 remediation.

For Bundle-007, the next executable sequence is:

| Step | Level | Contract Focus |
| --- | --- | --- |
| 1 | Level-0 | EC-008 confirms FRKP-DOC-100 synchronization needs. |
| 2 | Level-1 | EC-002 resolves related-document completeness. |
| 3 | Level-2 | EC-006 scaffolds evidence traceability from FRKC evidence records. |
| 4 | Level-3 | EC-004 and EC-005 map CAP and KO references for review. |
| 5 | Level-4 | EC-007 and EC-009 confirm bundle and metadata readiness. |
| 6 | Level-5 | EC-010 records editorial readiness verdict. |

---

# 7. Preservation Commitment

This validation model does not modify:

- FAEP Foundation.
- Core Contracts.
- Existing Standards.
- Bundle-007 content.
- Frozen artifacts.
- Publication content.

It defines execution levels for later validation and remediation plans.

---

# 8. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Editorial Validation Model created by PLAN-026 |
