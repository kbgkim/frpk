# FRKP-EDITORIAL-003 - Editorial Automation Profile

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-EDITORIAL-003 |
| Document Name | Editorial Automation Profile |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance; Editorial Automation |
| Owner | FRKP Publishing Office |
| Plan | PLAN-027 |
| Related Documents | FRKP-EDITORIAL-000; FRKP-EDITORIAL-001; FRKP-EDITORIAL-002; FRKP-EDITORIAL-004; FAEP-AI-000; PLAN-024; PLAN-025; PLAN-026; PLAN-026A |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |

---

# 1. Purpose

This profile defines how registered Editorial Contracts are executed by automation-capable publishing workflows.

It converts the PLAN-026 contract catalog into a provider-neutral execution specification:

```text
Editorial Contract -> Execution Rule -> Validation Rule -> Automation Level
-> Responsible Capability -> Review Requirement
```

This document is not an implementation. It does not modify existing Editorial Contracts, Bundle-007 content, publications, standards, FAEP Foundation artifacts, or candidate registries.

---

# 2. Editorial Execution Model

Editorial execution follows this model:

```text
Editorial Contract
-> Execution Profile
-> Validation
-> Editorial Result
-> Publication Decision
```

| Stage | Definition | Output |
| --- | --- | --- |
| Editorial Contract | Registered reusable rule from FRKP-EDITORIAL-001. | Contract ID, scope, severity, automation class. |
| Execution Profile | Provider-neutral method for running the contract. | Inputs, trigger, output, capability assignment, review requirement. |
| Validation | Deterministic, bounded semantic, or expert semantic check. | PASS, FAIL, or CONDITION with evidence. |
| Editorial Result | Recorded result of one contract execution. | Finding, correction candidate, scaffold, review queue item, or readiness verdict. |
| Publication Decision | Bundle or publication-level decision after contract results are aggregated. | GO, CONDITIONAL GO, or NO-GO. |

---

# 3. Execution Categories

## 3.1 AUTO

| Field | Rule |
| --- | --- |
| Execution method | Repository-safe deterministic inspection or patch-level correction against known files and known identifiers. |
| Validation method | Repeatable file, ID, link, metadata, inventory, and index checks. |
| Expected output | PASS report, deterministic finding, or bounded correction candidate. |
| Failure handling | Record failing artifact, expected value, observed value, and remediation candidate. |
| Escalation rule | Escalate to Governance Capability when correction changes lifecycle state, scope, or authority. |

AUTO contracts: EC-001, EC-002, EC-003, EC-007, EC-008, EC-009.

## 3.2 SEMI-AUTO

| Field | Rule |
| --- | --- |
| Execution method | Generate candidate mappings or traceability scaffolds from approved registries, evidence records, and known document scope. |
| Validation method | Pattern and registry resolution first; semantic appropriateness review second. |
| Expected output | Candidate CAP, KO, or EVD mappings with review status. |
| Failure handling | Record unresolved IDs, missing authorities, unsupported claims, and reviewer decision required. |
| Escalation rule | Escalate to Editorial, Review, Knowledge, or Financial Review when semantic correctness cannot be certified mechanically. |

SEMI-AUTO contracts: EC-004, EC-005, EC-006.

## 3.3 MANUAL

| Field | Rule |
| --- | --- |
| Execution method | Structured expert review using lower-level validation results as inputs. |
| Validation method | Human or reviewer-approved editorial, governance, architecture, and financial-domain judgment. |
| Expected output | Editorial readiness verdict with conditions, owners, and verification method. |
| Failure handling | Record blocker, unresolved condition, responsible capability, and required next plan. |
| Escalation rule | Escalate to Governance Capability for gate decisions; escalate to Architect Capability for architecture-impacting disputes. |

MANUAL contract: EC-010.

---

# 4. Capability Assignment

Capabilities are stable. Providers are replaceable.

| Capability | Responsibility in Editorial Automation |
| --- | --- |
| Engineering Capability | Runs deterministic repository validation, link checks, inventory checks, metadata checks, and patch-level correction candidates. |
| Knowledge Capability | Produces and validates candidate evidence, capability, and knowledge-object mappings before semantic review. |
| Editorial Capability | Reviews clarity, consistency, publication readiness, semantic appropriateness, and unresolved editorial conditions. |
| Review Capability | Challenges assumptions, verifies that contract outcomes satisfy quality gates, and records residual risk. |
| Governance Capability | Maintains lifecycle state, plan records, registry alignment, gate decisions, and escalation outcomes. |
| Publishing Capability | Maintains publication-facing metadata, indexes, navigation, and readiness handoff artifacts. |
| Architect Capability | Reviews architecture-impacting findings, platform implications, and scope boundary disputes. |
| Financial Review Capability | Reviews financial, regulatory, formula, and risk-domain claims when evidence or semantics affect financial interpretation. |

---

# 5. Provider Mapping

Provider mappings are informational examples only.

| Capability | Example Provider |
| --- | --- |
| Engineering Capability | Codex |
| Authoring Capability | OpenCode |
| Editorial Capability | GPT |
| Knowledge Capability | GPT; Codex |
| Review Capability | GPT; human reviewer |
| Governance Capability | GPT; Codex; governance owner |
| Publishing Capability | OpenCode; Codex |

Providers may be replaced without changing this profile. Conformance is based on capability responsibility, not on any specific product.

---

# 6. Automation Matrix

| Contract | Execution Rule | Validation Rule | Automation Level | Responsible Capability | Review Requirement |
| --- | --- | --- | --- | --- | --- |
| EC-001 Navigation | Inspect required navigation blocks and resolve local links. | Required fields present; links resolve or are explicitly None. | AUTO | Engineering Capability | None unless lifecycle target disputed. |
| EC-002 Related Documents | Compare related documents to known bundle scope and required peer relationships. | Mandatory relationships present; target IDs and links resolve. | AUTO | Engineering Capability | Semantic review only for new non-bundle relationships. |
| EC-003 Cross References | Inspect formal cross-reference sections and required target rows. | Required targets, locators, IDs, and links are valid. | AUTO | Engineering Capability | Semantic review only for new relationship types. |
| EC-004 Capability References | Generate or inspect CAP candidate mappings from registered capabilities. | CAP format and registry resolution pass; content fit reviewed. | SEMI-AUTO | Knowledge Capability | Semantic and governance review required. |
| EC-005 Knowledge Object References | Generate or inspect KO candidate mappings to canonical knowledge objects. | KO format and authority resolution pass; content fit reviewed. | SEMI-AUTO | Knowledge Capability | Semantic review required. |
| EC-006 Evidence References | Generate or inspect EVD candidate mappings to certified evidence. | EVD format and evidence authority resolution pass; evidence fit reviewed. | SEMI-AUTO | Knowledge Capability | Semantic and financial review required when claims are financial or regulatory. |
| EC-007 Bundle Integrity | Compare bundle review, deliverable inventory, and lifecycle state. | Listed files exist; present files are listed; status aligns with approved plan. | AUTO | Governance Capability | Architecture review if scope or lifecycle conflict exists. |
| EC-008 Master Index Synchronization | Compare master indexes to governed document and bundle state. | Index entries, status, deliverables, and links match current approved state. | AUTO | Engineering Capability | Governance review if state authority is unclear. |
| EC-009 Publication Metadata | Inspect Document Information blocks and publication metadata fields. | Required metadata exists and ID matches file identity. | AUTO | Publishing Capability | Governance review if owner/status is disputed. |
| EC-010 Editorial Readiness | Aggregate validation results and assess publication gate readiness. | Lower-level contracts pass or conditions are accepted with owners. | MANUAL | Editorial Capability | Review and governance approval required. |

---

# 7. Editorial Score Model

The editorial score is a weighted readiness score from 0 to 100.

| Dimension | Weight | Primary Contracts |
| --- | ---: | --- |
| Repository Integrity | 15 | EC-007; EC-008; EC-009 |
| Navigation | 10 | EC-001; EC-002 |
| Cross References | 10 | EC-002; EC-003 |
| Traceability | 15 | EC-003; EC-006 |
| Knowledge Integrity | 15 | EC-004; EC-005; EC-006 |
| Editorial Quality | 15 | EC-010 |
| Publication Readiness | 15 | EC-007; EC-009; EC-010 |
| Automation Coverage | 5 | EC-001 through EC-010 |
| Overall Score | 100 | All contracts |

PASS thresholds:

| Verdict | Threshold |
| --- | --- |
| GO | Overall score >= 90; no Blocking FAIL; all AUTO contracts PASS; MANUAL readiness PASS. |
| CONDITIONAL GO | Overall score >= 75; no unresolved Blocking FAIL; conditions have owner and verification method. |
| NO-GO | Overall score < 75, or any unresolved Blocking FAIL, or publication decision cannot be certified. |

---

# 8. Bundle-007 Validation Example

Bundle-007 would be processed as an illustration only:

```text
Repository Audit
-> Editorial Contracts
-> Automation Profile
-> Semantic Review
-> Freeze Candidate
```

| Step | Applied Profile | Expected Result |
| --- | --- | --- |
| Repository Audit | Level-0 and Level-1 AUTO checks. | Confirm branch, sync, deliverables, navigation, and known Bundle-007 inventory. |
| Editorial Contracts | EC-001 through EC-010 selected by Bundle-007 scope. | Contract execution queue with AUTO, SEMI-AUTO, and MANUAL items. |
| Automation Profile | AUTO first, SEMI-AUTO scaffold second, MANUAL last. | Deterministic findings separated from semantic review items. |
| Semantic Review | EC-004, EC-005, EC-006, EC-010 routed to review capabilities. | CAP, KO, EVD, and readiness decisions recorded without changing Bundle-007. |
| Freeze Candidate | Aggregate score and unresolved conditions. | GO, CONDITIONAL GO, or NO-GO recommendation. |

This example does not modify Bundle-007.

---

# 9. Future Automation

Future automation may be introduced after separate approval.

| Future Form | Candidate Steps |
| --- | --- |
| CLI | Contract selection, repository integrity check, link validation, score report. |
| GitHub Action | Branch/sync-independent validation on pull requests and release candidates. |
| CI Validation | AUTO contract checks, metadata checks, link checks, index consistency checks. |
| Repository Checker | Bundle inventory, document ID, navigation, related-document, and cross-reference validation. |
| AI Workflow | SEMI-AUTO CAP/KO/EVD scaffolding and MANUAL readiness review queue preparation. |

Implementation is out of scope for PLAN-027.

---

# 10. Recommended PLAN-028

| Field | Recommendation |
| --- | --- |
| Plan ID | PLAN-028 |
| Title | Bundle-007 Editorial Contract Execution Pilot |
| Objective | Execute the PLAN-027 profiles against Bundle-007 P2 findings without expanding beyond the approved worklist. |
| Scope | AUTO validation and correction candidates first; SEMI-AUTO CAP, KO, and EVD scaffolds second; MANUAL readiness review last. |
| Constraint | No publication release, no repository migration, no FAEP Foundation changes. |

---

# 11. Preservation Statement

This profile does not modify:

- FAEP Foundation.
- Existing Standards.
- Existing Contracts.
- Existing Editorial Contracts.
- Existing Candidate Registry.
- Existing Bundle-007 content.
- Existing Publications.

No implementation, editorial remediation, repository migration, release, or handbook writing was performed.

---

# 12. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Editorial Automation Profile created by PLAN-027 |
