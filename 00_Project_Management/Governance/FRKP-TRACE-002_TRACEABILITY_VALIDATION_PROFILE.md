# FRKP-TRACE-002 - Traceability Validation Profile

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-TRACE-002 |
| Title | Traceability Validation Profile |
| Status | Active Validation Profile |
| Owner | FRKP Publishing Office |
| Created | 2026-06-29 |
| Related Documents | FRKP-TRACE-000; FRKP-TRACE-001 |

---

# 1. Purpose

This profile defines validation criteria for the Traceability Contracts introduced by FRKP-TRACE-000.

It is conceptual and does not implement validators, modify Core Contracts, change Editorial Contracts, edit publications, or update indexes.

---

# 2. Severity Levels

| Severity | Meaning |
| --- | --- |
| Blocking | Must be resolved or formally deferred before publication freeze or release. |
| High | Required for publication readiness, but may enter review queue before remediation. |
| Medium | Required for repeatability and agent readiness. |
| Low | Improves auditability but does not block near-term review. |

---

# 3. Validation Profile

| Contract | PASS Criteria | FAIL Criteria | Severity | Automation Level | Responsible Capability |
| --- | --- | --- | --- | --- | --- |
| TC-001 Knowledge Mapping | Every knowledge-bearing document or publication section has a resolvable KO mapping or reviewed candidate mapping. | KO references are absent, unresolved, or semantically incompatible with the content. | High | SEMI-AUTO | Knowledge |
| TC-002 Capability Mapping | Every capability-bearing artifact maps to a resolvable CAP or candidate CAP with responsible domain assigned. | CAP references are absent, unresolved, or mapped to an unrelated capability. | High | SEMI-AUTO | Governance |
| TC-003 Evidence Mapping | Required claims, KOs, formulas, and architecture assertions map to EVD records with sufficient review state. | Evidence references are absent, unresolved, insufficient, or not applicable to the claim. | Blocking | SEMI-AUTO | Knowledge |
| TC-004 Publication Mapping | Source documents map to expected bundle, volume, handbook, or publication units with complete coverage. | Source-to-publication coverage is missing, duplicated without explanation, or inconsistent with approved scope. | High | AUTO | Publishing |
| TC-005 Master Index Synchronization | Governed indexes contain current IDs, titles, statuses, locations, and publication states. | Index omits required artifacts, records stale status, or conflicts with repository state. | Blocking | AUTO | Governance |
| TC-006 Bundle Completeness | Bundle scope, source documents, review document, metadata, and required references are present. | Required bundle artifacts are missing or scope cannot be reconciled. | Blocking | AUTO | Publishing |
| TC-007 Workflow Traceability | Each workflow stage records contract execution result, owner, automation class, review need, and handoff. | Workflow results are narrative-only, missing owners, or cannot support repeatable review. | Medium | SEMI-AUTO | Review |
| TC-008 Release Traceability | Release or freeze decision consumes traceability status, blockers, deferrals, and index state. | Release decision omits unresolved traceability failures or lacks governance authority for deferral. | Blocking | MANUAL | Governance |

---

# 4. Responsible Capability Rules

| Capability | Responsibility |
| --- | --- |
| Knowledge | KO mapping, EVD candidate mapping, evidence applicability preparation. |
| Engineering | Deterministic repository checks, ID format checks, file existence checks, link resolution support. |
| Editorial | Publication readability, section placement, editorial readiness, semantic coherence. |
| Governance | Contract authority, capability authority, index authority, release/freeze decisions. |
| Publishing | Publication mapping, bundle completeness, handbook structure, navigation handoff. |
| Review | Independent challenge, score worksheet review, residual risk, gate recommendation. |

---

# 5. Contract Execution Result Format

Future execution records should use this minimum format:

| Field | Required |
| --- | --- |
| Contract ID | Yes |
| Target Artifact | Yes |
| Automation Level | Yes |
| Responsible Capability | Yes |
| Input Evidence | Yes |
| Validation Result | Yes: PASS, FAIL, CONDITION, or NOT REVIEWED |
| Severity | Yes |
| Review Required | Yes |
| Recommended Action | Yes for FAIL or CONDITION |
| Source Modification Authorized | Yes/No |

---

# 6. Bundle-007 Validation Example

| Bundle-007 Finding | Contract | Current Result | Required Next Step |
| --- | --- | --- | --- |
| EVD references absent | TC-003 | CONDITION | Prepare candidate EVD mappings; route semantic and financial review. |
| CAP references absent | TC-002 | CONDITION | Prepare candidate CAP mappings; route governance review. |
| KO references absent | TC-001 | CONDITION | Prepare candidate KO mappings; route knowledge/editorial review. |
| FRKP-DOC-100 stale/incomplete for Bundle-007 | TC-005 | CONDITION | Prepare governance-controlled index synchronization decision input. |
| No reusable execution log | TC-007 | CONDITION | Create reusable traceability execution record in PLAN-030. |
| Release/freeze depends on unresolved traceability conditions | TC-008 | CONDITION | Require review outcomes before release certification. |

No Bundle-007 P2 work is completed by this example.

---

# 7. Overall Verdict Logic

| Verdict | Rule |
| --- | --- |
| GO | All Blocking contracts PASS; all High contracts PASS or have reviewed non-blocking deferral; release authority recorded where applicable. |
| CONDITIONAL GO | No unresolved unreviewed Blocking FAIL; one or more CONDITION items have owner, contract, and validation path. |
| NO-GO | Any unresolved Blocking FAIL lacks deferral authority, or traceability state cannot be reconstructed. |

For PLAN-029, the validation profile supports:

CONDITIONAL GO - Traceability Framework Established with Validation Recommendations
