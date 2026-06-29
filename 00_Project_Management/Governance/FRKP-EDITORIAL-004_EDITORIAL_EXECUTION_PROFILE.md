# FRKP-EDITORIAL-004 - Editorial Execution Profile

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-EDITORIAL-004 |
| Document Name | Editorial Execution Profile |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance; Editorial Execution |
| Owner | FRKP Publishing Office |
| Plan | PLAN-027 |
| Related Documents | FRKP-EDITORIAL-000; FRKP-EDITORIAL-001; FRKP-EDITORIAL-002; FRKP-EDITORIAL-003; FAEP-AI-000 |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |

---

# 1. Purpose

This document is the execution profile catalog for all Editorial Contracts registered by FRKP-EDITORIAL-001.

It specifies trigger, input, output, PASS rule, FAIL rule, automatic resolution, and required review type for each contract. It does not execute the contracts.

---

# 2. Execution Profile Catalog

## 2.1 EC-001 - Navigation

| Field | Value |
| --- | --- |
| Execution Trigger | Governed markdown document enters bundle review, publication review, freeze candidate review, or index synchronization. |
| Input | Document file; expected navigation pattern; known parent bundle/layer; neighboring documents when applicable. |
| Output | Navigation validation result and correction candidate when deterministic. |
| PASS Rule | Navigation block exists; breadcrumb and required fields exist; local links resolve or are explicitly None. |
| FAIL Rule | Navigation block missing; required field missing; link broken; parent relationship invalid. |
| AUTO Resolution | Yes. Add or correct deterministic navigation fields only. |
| Requires Semantic Review | No |
| Requires Financial Review | No |
| Requires Architecture Review | No |

## 2.2 EC-002 - Related Documents

| Field | Value |
| --- | --- |
| Execution Trigger | Bundle scope changes, document joins bundle scope, or related-document review is requested. |
| Input | Source document; bundle deliverable list; known upstream, downstream, and peer relationships. |
| Output | Related Documents validation result and deterministic correction candidate. |
| PASS Rule | Mandatory bundle peers and required upstream/downstream documents are present with resolving links. |
| FAIL Rule | Mandatory related document missing; linked ID mismatch; related-document link broken. |
| AUTO Resolution | Yes for known bundle relationships. |
| Requires Semantic Review | No for known peers; Yes for new relationship proposals. |
| Requires Financial Review | No |
| Requires Architecture Review | Yes only when a proposed relationship changes bundle architecture. |

## 2.3 EC-003 - Cross References

| Field | Value |
| --- | --- |
| Execution Trigger | Bundle review, publication review, or related-document correction creates required formal cross-reference entries. |
| Input | Source document; required target IDs; target titles; locators; relationship types when defined. |
| Output | Cross-reference validation result and correction candidate. |
| PASS Rule | Required Cross References section and required rows exist; target IDs and links resolve. |
| FAIL Rule | Required section missing; mandatory target omitted; ID/link mismatch; locator missing. |
| AUTO Resolution | Yes for mandatory known relationships. |
| Requires Semantic Review | No for known relationships; Yes for new semantic relationship types. |
| Requires Financial Review | No |
| Requires Architecture Review | No unless relationship changes architecture meaning. |

## 2.4 EC-004 - Capability References

| Field | Value |
| --- | --- |
| Execution Trigger | Capability-bearing document or section enters traceability, publication, or readiness review. |
| Input | Source section; FAEP-CAP registry; candidate capability identifiers; context summary. |
| Output | CAP mapping scaffold and review queue entry. |
| PASS Rule | CAP IDs are valid, resolve in the registry, and are approved as semantically appropriate. |
| FAIL Rule | Required CAP block missing; CAP ID unresolved; mapping contradicts source content or registry authority. |
| AUTO Resolution | Scaffold only. |
| Requires Semantic Review | Yes |
| Requires Financial Review | No unless capability claim changes financial-domain interpretation. |
| Requires Architecture Review | Yes when mapping affects platform capability boundaries. |

## 2.5 EC-005 - Knowledge Object References

| Field | Value |
| --- | --- |
| Execution Trigger | Knowledge-bearing document or section enters traceability, publication, or readiness review. |
| Input | Source section; KO authority or mapping model; candidate KO identifiers; context summary. |
| Output | KO mapping scaffold and review queue entry. |
| PASS Rule | KO IDs are valid, resolvable, and approved as appropriate to the section content. |
| FAIL Rule | Required KO block missing; KO unresolved; KO mapping is unsupported or contradictory. |
| AUTO Resolution | Scaffold only. |
| Requires Semantic Review | Yes |
| Requires Financial Review | No unless KO mapping affects formula, regulation, capital, or risk interpretation. |
| Requires Architecture Review | No unless KO boundary changes architecture classification. |

## 2.6 EC-006 - Evidence References

| Field | Value |
| --- | --- |
| Execution Trigger | Evidence-bearing document, factual claim, formula claim, regulatory claim, or publication package enters traceability review. |
| Input | Source document or section; evidence register; EVD candidate set; claim context. |
| Output | Evidence mapping scaffold, unresolved evidence findings, and review queue entry. |
| PASS Rule | Required EVD references exist, resolve to the evidence authority, and are approved as supporting the claims. |
| FAIL Rule | Required evidence block missing; EVD unresolved; evidence not certified where required; claim unsupported. |
| AUTO Resolution | Scaffold only. |
| Requires Semantic Review | Yes |
| Requires Financial Review | Yes for financial, regulatory, capital, formula, or risk claims. |
| Requires Architecture Review | No unless evidence supports architecture claims. |

## 2.7 EC-007 - Bundle Integrity

| Field | Value |
| --- | --- |
| Execution Trigger | Bundle audit, freeze candidate review, release readiness review, or bundle scope synchronization. |
| Input | Bundle review file; expected deliverable list; layer inventory; plan and lifecycle status. |
| Output | Bundle integrity validation result and correction candidate for inventory/status discrepancies. |
| PASS Rule | Bundle lists all included deliverables; listed files exist; layer count and lifecycle state match approved scope. |
| FAIL Rule | Deliverable missing; present deliverable omitted; lifecycle state contradicts approved plan or freeze state. |
| AUTO Resolution | Yes for inventory corrections; No for lifecycle authority disputes. |
| Requires Semantic Review | No |
| Requires Financial Review | No |
| Requires Architecture Review | Yes when scope, lifecycle, or architecture boundary is disputed. |

## 2.8 EC-008 - Master Index Synchronization

| Field | Value |
| --- | --- |
| Execution Trigger | Governed document, bundle state, layer index, publication index, or master index changes. |
| Input | Master index; layer indexes; bundle review; governed document inventory. |
| Output | Index synchronization validation result and deterministic correction candidate. |
| PASS Rule | Current governed documents and bundle states are represented; links resolve; status matches approved records. |
| FAIL Rule | Active bundle or document missing; stale status; deliverable matrix incomplete; index link broken. |
| AUTO Resolution | Yes. |
| Requires Semantic Review | No |
| Requires Financial Review | No |
| Requires Architecture Review | No |

## 2.9 EC-009 - Publication Metadata

| Field | Value |
| --- | --- |
| Execution Trigger | Governed artifact creation, publication review, freeze candidate review, or metadata audit. |
| Input | Document file; expected ID; metadata field requirements; lifecycle state. |
| Output | Metadata validation result and deterministic correction candidate. |
| PASS Rule | Document Information table exists; required fields exist; document ID matches file identity and status is recorded. |
| FAIL Rule | Metadata block missing; ID mismatch; required field absent; version/status missing where required. |
| AUTO Resolution | Yes for field presence and ID corrections; No for disputed owner or status values. |
| Requires Semantic Review | No |
| Requires Financial Review | No |
| Requires Architecture Review | No |

## 2.10 EC-010 - Editorial Readiness

| Field | Value |
| --- | --- |
| Execution Trigger | AUTO and SEMI-AUTO contract results are available for a bundle, publication package, or freeze candidate. |
| Input | Contract results; score model; review findings; unresolved conditions; quality gate requirements. |
| Output | Editorial readiness verdict with conditions, owners, verification method, and publication decision recommendation. |
| PASS Rule | Required lower-level contracts pass or conditions are accepted; no unresolved blocking failure remains; quality gate can be assessed. |
| FAIL Rule | Blocking contract fails; semantic review cannot certify mappings; conditions lack owner or verification method. |
| AUTO Resolution | No. |
| Requires Semantic Review | Yes |
| Requires Financial Review | Yes when unresolved financial, regulatory, formula, or risk claims remain. |
| Requires Architecture Review | Yes when unresolved architecture scope or lifecycle conditions remain. |

---

# 3. Capability Assignment Matrix

| Contract | Primary Capability | Supporting Capability |
| --- | --- | --- |
| EC-001 | Engineering Capability | Publishing Capability |
| EC-002 | Engineering Capability | Knowledge Capability |
| EC-003 | Engineering Capability | Knowledge Capability |
| EC-004 | Knowledge Capability | Editorial Capability; Governance Capability |
| EC-005 | Knowledge Capability | Editorial Capability |
| EC-006 | Knowledge Capability | Financial Review Capability; Editorial Capability |
| EC-007 | Governance Capability | Architect Capability |
| EC-008 | Engineering Capability | Governance Capability |
| EC-009 | Publishing Capability | Governance Capability |
| EC-010 | Editorial Capability | Review Capability; Governance Capability; Architect Capability; Financial Review Capability |

---

# 4. Review Requirement Matrix

| Contract | Semantic Review | Financial Review | Architecture Review |
| --- | :-: | :-: | :-: |
| EC-001 | No | No | No |
| EC-002 | Conditional | No | Conditional |
| EC-003 | Conditional | No | Conditional |
| EC-004 | Yes | Conditional | Conditional |
| EC-005 | Yes | Conditional | Conditional |
| EC-006 | Yes | Conditional | Conditional |
| EC-007 | No | No | Conditional |
| EC-008 | No | No | No |
| EC-009 | No | No | No |
| EC-010 | Yes | Conditional | Conditional |

---

# 5. Execution Order

Contracts shall execute in this order unless a plan defines a narrower approved subset:

1. EC-007 Bundle Integrity.
2. EC-008 Master Index Synchronization.
3. EC-009 Publication Metadata.
4. EC-001 Navigation.
5. EC-002 Related Documents.
6. EC-003 Cross References.
7. EC-006 Evidence References.
8. EC-004 Capability References.
9. EC-005 Knowledge Object References.
10. EC-010 Editorial Readiness.

AUTO contracts run before SEMI-AUTO contracts. MANUAL readiness review runs only after required AUTO and SEMI-AUTO results are available.

---

# 6. Bundle-007 Execution Example

Bundle-007 execution is illustrative only.

| Phase | Contracts | Result Type |
| --- | --- | --- |
| Repository Audit | EC-007; EC-008; EC-009 | Confirm inventory, metadata, index state, and known gaps. |
| Editorial Contracts | EC-001 through EC-010 | Select applicable contracts from the catalog. |
| Automation Profile | EC-001; EC-002; EC-003; EC-007; EC-008; EC-009 | Produce deterministic validation results and correction candidates. |
| Semantic Review | EC-004; EC-005; EC-006; EC-010 | Produce reviewed CAP, KO, EVD, and readiness decisions. |
| Freeze Candidate | EC-010 plus score model | Recommend GO, CONDITIONAL GO, or NO-GO. |

No Bundle-007 source document is modified by this example.

---

# 7. Recommended PLAN-028

| Field | Recommendation |
| --- | --- |
| Plan ID | PLAN-028 |
| Title | Bundle-007 Editorial Contract Execution Pilot |
| Objective | Execute this profile against Bundle-007 P2 findings as a bounded pilot. |
| Required Inputs | PLAN-024 audit, PLAN-025 P1 corrections, PLAN-026 contracts, PLAN-026A capability model, PLAN-027 profiles. |
| Expected Outputs | Contract execution log, deterministic correction candidates, semantic review queue, editorial score, and readiness recommendation. |

---

# 8. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Editorial Execution Profile created by PLAN-027 |
