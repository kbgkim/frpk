# FRKP-EDITORIAL-001 - Editorial Contract Catalog

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-EDITORIAL-001 |
| Document Name | Editorial Contract Catalog |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance |
| Owner | FRKP Publishing Office |
| Plan | PLAN-026 |
| Related Documents | FRKP-EDITORIAL-000; FRKP-EDITORIAL-002; EDITORIAL_WORKLIST_BUNDLE_007; REPOSITORY_AUDIT_BUNDLE_007; FAEP-STD-003; FAEP-STD-004; FRKP-PROGRAM-002; FRKP-PROGRAM-004; FRKP-PUB-001 |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |

---

# 1. Purpose

This catalog registers reusable Editorial Contracts extracted from Bundle-007 P2 findings.

The catalog does not resolve the findings. It defines the recurring rules so later plans can execute
them consistently and automate them where possible.

---

# 2. Editorial Contract Summary

| Contract | Name | Primary Classification | Severity | Automation | Validation Level |
| --- | --- | --- | --- | --- | --- |
| EC-001 | Navigation | Publication | Required | AUTO | Level-1 |
| EC-002 | Related Documents | Publication | Required | AUTO | Level-1 |
| EC-003 | Cross References | Deterministic | Required | AUTO | Level-2 |
| EC-004 | Capability References | Knowledge | Required | SEMI-AUTO | Level-3 |
| EC-005 | Knowledge Object References | Knowledge | Required | SEMI-AUTO | Level-3 |
| EC-006 | Evidence References | Knowledge | Blocking | SEMI-AUTO | Level-2 |
| EC-007 | Bundle Integrity | Architectural | Required | AUTO | Level-4 |
| EC-008 | Master Index Synchronization | Governance | Required | AUTO | Level-0 |
| EC-009 | Publication Metadata | Governance | Required | AUTO | Level-4 |
| EC-010 | Editorial Readiness | Publication | Required | MANUAL | Level-5 |

---

# 3. Contract Catalog

## 3.1 EC-001 - Navigation

| Field | Value |
| --- | --- |
| Purpose | Ensure each governed document has a complete FRKP navigation block that supports human and AI traversal. |
| Scope | FRKP documents, bundle reviews, publication artifacts |
| Applicability | Active for every governed markdown document in a publication or bundle scope |
| Classification | Publication; Deterministic |
| PASS Criteria | Navigation block exists; breadcrumb exists; Previous, Parent Bundle, Parent Layer, Next fields are present; local links resolve or are explicitly None. |
| FAIL Criteria | Missing navigation block; required navigation field absent; local navigation link is broken. |
| Severity | Required |
| Automatic Resolution | Yes |
| Requires GPT Review | No |
| Automation Class | AUTO |
| Source Standards | FAEP-STD-004; FRKP-PROGRAM-002 |

## 3.2 EC-002 - Related Documents

| Field | Value |
| --- | --- |
| Purpose | Ensure document-level Related Documents represent required upstream, downstream, peer, and bundle relationships. |
| Scope | FRKP source documents and bundle reviews |
| Applicability | Active when a document belongs to a bundle or references sibling layer documents |
| Classification | Publication; Knowledge; Deterministic |
| PASS Criteria | Related Documents list includes mandatory bundle peers based on the approved bundle deliverable set; links resolve; document IDs match targets. |
| FAIL Criteria | Mandatory peer, upstream, or downstream document is omitted; related document link is broken; linked ID does not match target. |
| Severity | Required |
| Automatic Resolution | Yes |
| Requires GPT Review | No for known bundle peers; Yes for new semantic relationships |
| Automation Class | AUTO |
| Source Standards | FAEP-STD-004; FRKP-PROGRAM-002 |

## 3.3 EC-003 - Cross References

| Field | Value |
| --- | --- |
| Purpose | Ensure formal cross-reference tables provide machine-readable semantic links between related artifacts. |
| Scope | Governed source documents and publication sections |
| Applicability | Active when source documents have known bundle peers or standards dependencies |
| Classification | Deterministic; Publication; Knowledge |
| PASS Criteria | Cross References section exists when required; table includes target ID, target description or title, locator, relationship type where needed, and valid links. |
| FAIL Criteria | Required Cross References section is missing; required target is omitted; target link is broken; target ID is unstable or mismatched. |
| Severity | Required |
| Automatic Resolution | Yes |
| Requires GPT Review | No for mandatory bundle peers; Yes for relationship-type semantics beyond known patterns |
| Automation Class | AUTO |
| Source Standards | FAEP-STD-004; FRKP-PROGRAM-002 |

## 3.4 EC-004 - Capability References

| Field | Value |
| --- | --- |
| Purpose | Ensure publication content maps to registered FAEP Candidate Capabilities where capability claims or implementation patterns are discussed. |
| Scope | FRKP source documents, Handbook sections, bundle review documents |
| Applicability | Active for every technical, architectural, implementation, knowledge, or publishing section that describes platform capability. |
| Classification | Knowledge; Semantic; Governance |
| PASS Criteria | Capability Mapping block exists where required; every CAP ID follows CAP-{DOMAIN}-{NNN}; every CAP ID resolves in FAEP-CAP-001; selected capability is appropriate to the section content. |
| FAIL Criteria | Required Capability Mapping block is missing; CAP ID does not resolve; mapped capability contradicts section content or source registry. |
| Severity | Required |
| Automatic Resolution | No |
| Requires GPT Review | Yes |
| Automation Class | SEMI-AUTO |
| Source Standards | FRKP-PROGRAM-002; FRKP-PUB-001; FAEP-CAP-001 |

## 3.5 EC-005 - Knowledge Object References

| Field | Value |
| --- | --- |
| Purpose | Ensure publication content traces to canonical FRKC knowledge objects rather than becoming an unsupported standalone document. |
| Scope | FRKP source documents, Handbook sections, bundle review documents |
| Applicability | Active for every section carrying canonical knowledge, formula, implementation, architecture, or domain explanation. |
| Classification | Knowledge; Semantic |
| PASS Criteria | Knowledge Object Reference block exists where required; each KO ID follows the registered KO pattern; each KO is resolvable to an FRKC knowledge object or approved mapping; KO is appropriate to section content. |
| FAIL Criteria | Required KO block is missing; KO ID is malformed or unresolved; KO does not support the section content. |
| Severity | Required |
| Automatic Resolution | No |
| Requires GPT Review | Yes |
| Automation Class | SEMI-AUTO |
| Source Standards | FRKP-005; FRKP-PROGRAM-002; FRKP-PUB-001 |

## 3.6 EC-006 - Evidence References

| Field | Value |
| --- | --- |
| Purpose | Ensure every publication claim can trace through FRKC evidence records to an authoritative source. |
| Scope | FRKP source documents, Handbook sections, bundle review documents, release or freeze baselines |
| Applicability | Active for every governed document or section containing factual, regulatory, formula, or architecture claims. |
| Classification | Knowledge; Governance; Semantic |
| PASS Criteria | Evidence block or traceability block exists where required; every EVD ID follows EVD-NNNNNN; each EVD ID resolves to the evidence authority; evidence is mapped to the artifact; certification status is acceptable. |
| FAIL Criteria | Required evidence block is missing; EVD ID is malformed or unresolved; evidence is not certified where certification is required; claims have no evidence mapping. |
| Severity | Blocking |
| Automatic Resolution | No |
| Requires GPT Review | Yes |
| Automation Class | SEMI-AUTO |
| Source Standards | FAEP-STD-003; FRKP-FRKC-001; FRKP-PROGRAM-002; FRKP-PROGRAM-004 |

## 3.7 EC-007 - Bundle Integrity

| Field | Value |
| --- | --- |
| Purpose | Ensure bundle review documents, deliverables, layer inventory, and lifecycle status remain consistent. |
| Scope | Bundle review files, bundle directories, bundle audit artifacts, freeze or release records |
| Applicability | Active for every bundle at Quality Review, Freeze Gate, release candidate, or maintenance stage |
| Classification | Architectural; Governance; Publication |
| PASS Criteria | Bundle review lists all included deliverables; listed files exist; layer count matches approved scope; status and lifecycle stage align with bundle evidence and plan records. |
| FAIL Criteria | Listed deliverable missing; present deliverable omitted from bundle review; lifecycle status contradicts approved plan or freeze state. |
| Severity | Required |
| Automatic Resolution | Yes |
| Requires GPT Review | No for inventory; Yes for lifecycle risk acceptance |
| Automation Class | AUTO |
| Source Standards | FAEP-STD-002; FRKP-PROGRAM-004 |

## 3.8 EC-008 - Master Index Synchronization

| Field | Value |
| --- | --- |
| Purpose | Ensure repository master indexes reflect current bundle, document, and layer state. |
| Scope | FRKP-DOC-100, layer README files, bundle README files, publication indexes |
| Applicability | Active when a governed document, bundle, layer, prefix, or status changes |
| Classification | Governance; Deterministic; Publication |
| PASS Criteria | New governed documents are registered; bundle status matches latest approved plan; deliverable matrix includes active bundle scope; index links resolve. |
| FAIL Criteria | Active bundle missing from index; status is stale; deliverable matrix omits known documents; index link is broken. |
| Severity | Required |
| Automatic Resolution | Yes |
| Requires GPT Review | No |
| Automation Class | AUTO |
| Source Standards | FAEP-STD-001; FAEP-STD-004; FRKP-DOC-100 maintenance rules |

## 3.9 EC-009 - Publication Metadata

| Field | Value |
| --- | --- |
| Purpose | Ensure governed artifacts carry consistent metadata required for publication, indexing, AI retrieval, and quality gates. |
| Scope | FRKP documents, publication volumes, bundle reviews, governance documents |
| Applicability | Active for every governed markdown artifact |
| Classification | Governance; Deterministic; Publication |
| PASS Criteria | Document Information table exists; required fields are present; Document ID matches file ID; version, status, owner/category where applicable, created date, and related documents are present. |
| FAIL Criteria | Missing Document Information; ID mismatch; required metadata field absent; frozen/released artifact lacks version or status. |
| Severity | Required |
| Automatic Resolution | Yes |
| Requires GPT Review | No for field presence; Yes for ownership or status disputes |
| Automation Class | AUTO |
| Source Standards | FAEP-STD-001; FRKP-PROGRAM-002; FRKP-PROGRAM-004 |

## 3.10 EC-010 - Editorial Readiness

| Field | Value |
| --- | --- |
| Purpose | Ensure a document or bundle is ready for publication quality gate review after deterministic and traceability checks are satisfied. |
| Scope | Handbook volumes, bundle publication packages, release candidates |
| Applicability | Active before Publication Freeze or release readiness assessment |
| Classification | Publication; Semantic; Governance |
| PASS Criteria | Required lower-level contracts pass or have accepted conditions; quality gate dimensions can be assessed; open conditions are recorded with owner, target date, and verification method. |
| FAIL Criteria | Critical traceability or publishing contracts fail; quality gate cannot be assessed; conditions lack owner, target date, or verification method. |
| Severity | Required |
| Automatic Resolution | No |
| Requires GPT Review | Yes |
| Automation Class | MANUAL |
| Source Standards | FRKP-PROGRAM-004; FRKP-PROGRAM-001; FRKP-FRKC-001 |

---

# 4. Automation Matrix

| Contract | Codex/OpenCode Auto-Resolve | Deterministic Validation | GPT Review Required | Automation Class |
| --- | --- | --- | --- | --- |
| EC-001 Navigation | Yes | Yes | No | AUTO |
| EC-002 Related Documents | Yes for known peers | Yes | Conditional | AUTO |
| EC-003 Cross References | Yes for known peers | Yes | Conditional | AUTO |
| EC-004 Capability References | Scaffold only | Partial | Yes | SEMI-AUTO |
| EC-005 Knowledge Object References | Scaffold only | Partial | Yes | SEMI-AUTO |
| EC-006 Evidence References | Scaffold only | Partial | Yes | SEMI-AUTO |
| EC-007 Bundle Integrity | Yes for inventory/status deltas | Yes | Conditional | AUTO |
| EC-008 Master Index Synchronization | Yes | Yes | No | AUTO |
| EC-009 Publication Metadata | Yes | Yes | Conditional | AUTO |
| EC-010 Editorial Readiness | No | Partial | Yes | MANUAL |

---

# 5. Bundle-007 P2 Mapping

| P2 Finding | Why It Happened | Missing Rule | Mapped Contract(s) | Deterministic Validation | Automatic Resolution | GPT Review |
| --- | --- | --- | --- | --- | --- | --- |
| P2-001: Add ARCH-771 to MF-471 Related Documents | Related document completeness was handled as document editing rather than a reusable bundle-peer rule. | Each document must include mandatory related bundle peers based on layer relationship. | EC-002; EC-007 | Yes | Yes | No |
| P2-002: Add MF-471 to IMP-471 Related Documents | Upstream mathematical dependency was not enforced by a bundle relationship contract. | Implementation documents must reference mathematical foundations they implement when present in scope. | EC-002; EC-003; EC-007 | Yes | Yes | No |
| P2-003: Add FRKC Evidence Traceability | Bundle-007 predates the evidence-driven publishing workflow and evidence block requirement. | Every governed section or artifact must map claims to EVD references from the evidence authority. | EC-006; EC-010 | Partial | Scaffold only | Yes |
| P2-004: Add FAEP Capability References | Capability mapping existed in FAEP-CAP-001 and FRKP-PUB-001 but was not applied as an editorial contract. | Capability-bearing sections must include resolvable CAP references appropriate to content. | EC-004; EC-010 | Partial | Scaffold only | Yes |
| P2-005: Add Knowledge Object References | KO traceability existed in FRKP-005 and FRKP-PROGRAM-002 but was not enforced during Bundle-007 authoring. | Knowledge-bearing sections must include resolvable KO references to canonical FRKC objects. | EC-005; EC-010 | Partial | Scaffold only | Yes |
| P2-006: Synchronize FRKP-DOC-100 Master Index | Master index maintenance was not tied to bundle completion or document creation events. | Indexes must be synchronized whenever governed bundle/document state changes. | EC-008; EC-007; EC-009 | Yes | Yes | No |

---

# 6. Execution Demonstration for Bundle-007 P2

Bundle-007 P2 can be resolved by executing contracts rather than by open-ended manual review:

| Execution Step | Contract | Expected Output |
| --- | --- | --- |
| 1 | EC-007 | Confirm Bundle-007 deliverable inventory and lifecycle state. |
| 2 | EC-002 and EC-003 | Generate missing known related-document and cross-reference updates. |
| 3 | EC-006 | Generate evidence traceability scaffolds from EVD-000340 through EVD-000349 and request GPT/human appropriateness review. |
| 4 | EC-004 | Generate CAP candidate mappings from FAEP-CAP-001 and request GPT/human appropriateness review. |
| 5 | EC-005 | Generate KO candidate mappings from FRKP-005/FRKP-PUB-001 and request GPT/human appropriateness review. |
| 6 | EC-008 | Synchronize FRKP-DOC-100 bundle status and deliverable matrix. |
| 7 | EC-010 | Run editorial readiness assessment using FRKP-PROGRAM-004 dimensions. |

---

# 7. Recommended PLAN-027

| Field | Recommendation |
| --- | --- |
| Plan ID | PLAN-027 |
| Title | Bundle-007 Editorial Contract Execution |
| Objective | Execute the registered Editorial Contracts against Bundle-007 P2 findings without expanding scope beyond the known P2 worklist. |
| Primary Contracts | EC-002; EC-004; EC-005; EC-006; EC-007; EC-008; EC-010 |
| Expected Outputs | Bundle-007 P2 remediation edits, traceability mappings, FRKP-DOC-100 synchronization, validation report |
| Automation Strategy | Run AUTO contracts first, scaffold SEMI-AUTO traceability, then send semantic mappings for GPT/human review. |
| Constraints | No FAEP Foundation changes, no Core Contract changes, no new standards, no release. |

---

# 8. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Editorial Contract Catalog created by PLAN-026 |
