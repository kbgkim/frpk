# FAEP-ADR-000 - Architecture Decision Registry

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-ADR-000 |
| Document Name | Architecture Decision Registry |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-STD-005; FAEP-000; FAEP-001; FAEP-002; FRKP-003; FRKP-004; FRKP-005 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-015 |

---

# 1. Purpose

This registry centralizes reusable FAEP architecture decisions extracted from previous plans and governance specifications.

Historical `AD-NNN` identifiers are preserved in their source documents. This registry assigns FAEP-level registry IDs for cross-program governance.

---

# 2. Registry Summary

| Registry ID | Source | Source ID | Title | Status |
| --- | --- | --- | --- | --- |
| FAEP-ADR-001 | PLAN-011 | AD-001 | FAEP as Umbrella Architecture | Accepted |
| FAEP-ADR-002 | PLAN-011 | AD-002 | FRKP as First Reference Implementation | Accepted |
| FAEP-ADR-003 | PLAN-011 | AD-005 | KPGF as Reusable Governance Framework Extract | Accepted |
| FAEP-ADR-004 | PLAN-012 / FRKP-004 | AD-001 | FAEP Core as Platform Contract | Accepted |
| FAEP-ADR-005 | PLAN-012 / FRKP-004 | AD-002 | Sixteen-Engine Platform Decomposition | Accepted |
| FAEP-ADR-006 | PLAN-012 / FRKP-004 | AD-003 | Contracts Before Implementation | Accepted |
| FAEP-ADR-007 | PLAN-012 / FRKP-004 | AD-006 | Plugin Architecture for All Engines | Accepted |
| FAEP-ADR-008 | PLAN-012 / FRKP-004 | AD-007 | Hybrid Repository Strategy | Accepted |
| FAEP-ADR-009 | PLAN-012 / FRKP-004 | AD-009 | Text-Based Contracts Initially | Accepted |
| FAEP-ADR-010 | PLAN-012 / FRKP-004 | AD-010 | Progressive Formalization | Accepted |
| FAEP-ADR-011 | PLAN-012 / FRKP-004 | AD-011 | Evidence-Driven Traceability | Accepted |
| FAEP-ADR-012 | PLAN-012 / FRKP-004 | AD-012 | Human + AI Governance Model | Accepted |
| FAEP-ADR-013 | PLAN-012 / FRKP-004 | AD-013 | Bundle Lifecycle as Standard | Accepted |
| FAEP-ADR-014 | PLAN-012 / FRKP-004 | AD-014 | Minimum Viable Governance | Accepted |
| FAEP-ADR-015 | PLAN-012 / FRKP-004 | AD-015 | Domain Isolation Principle | Accepted |
| FAEP-ADR-016 | PLAN-012 / FRKP-004 | AD-016 | AI Agent Readiness | Accepted |
| FAEP-ADR-017 | PLAN-013 | AD-001 | FAEP Program as Governing Structure | Accepted |
| FAEP-ADR-018 | PLAN-013 | AD-002 | Program-Numbered Architecture | Accepted |
| FAEP-ADR-019 | PLAN-013 | AD-003 | FAEP-Namespaced Governance Documents | Accepted |
| FAEP-ADR-020 | PLAN-013 | AD-004 | Governance Before Expansion | Accepted |
| FAEP-ADR-021 | PLAN-013 | AD-005 | Preservation of Existing Identifiers | Accepted |
| FAEP-ADR-022 | FRKP-005 | AD-001 | FRKC as Knowledge Operating System | Accepted |
| FAEP-ADR-023 | FRKP-005 | AD-002 | Six-Layer Knowledge Architecture | Accepted |
| FAEP-ADR-024 | FRKP-005 | AD-003 | Canonical First - Single Source of Truth | Accepted |
| FAEP-ADR-025 | FRKP-005 | AD-004 | Evidence-Anchored Knowledge | Accepted |
| FAEP-ADR-026 | FRKP-005 | AD-006 | Knowledge Graph as Primary Navigation Model | Accepted |
| FAEP-ADR-027 | FRKP-005 | AD-007 | Separate Evidence Graph from Knowledge Graph | Accepted |
| FAEP-ADR-028 | FRKP-005 | AD-008 | AI-Native Knowledge Design | Accepted |
| FAEP-ADR-029 | FRKP-005 | AD-011 | Integration Through Contracts, Not Direct Access | Accepted |
| FAEP-ADR-030 | FRKP-005 | AD-012 | FRKC as Separate Repository | Accepted |
| FAEP-ADR-031 | FRKP-005 | AD-017 | Evidence Certification Precedes Knowledge Publication | Accepted |
| FAEP-ADR-032 | PLAN-015 | AD-001 | FAEP Standards as Core Governance Catalogue | Accepted |
| FAEP-ADR-033 | PLAN-015 | AD-002 | FRKP Standards as Reference Implementation Standards | Accepted |

---

# 3. Architecture Decisions

## FAEP-ADR-001 - FAEP as Umbrella Architecture

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | PLAN-011 established a platform architecture spanning FRKP, FRKC, Risk Platform, AI Platform, and future business platforms. |
| Decision | FAEP is the umbrella architecture for all Financial AI Platform projects. |
| Consequences | FRKP is no longer the final architectural boundary; it validates FAEP as a Reference Implementation. |
| Related Standards | FAEP-STD-000 |
| Related Specifications | FRKP-003; FRKP-004 |
| Related Programs | Program-000; Program-100; Program-200; Program-300; Program-400; Program-500 |

## FAEP-ADR-002 - FRKP as First Reference Implementation

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Existing FRKP governance and bundles validate platform concepts. |
| Decision | FRKP is the first Reference Implementation of FAEP Core. |
| Consequences | FRKP-specific rules are preserved but reusable rules are extracted into FAEP Standards. |
| Related Standards | FAEP-STD-000; FAEP-STD-002; FAEP-STD-006 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-200 |

## FAEP-ADR-003 - KPGF as Reusable Governance Framework Extract

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | FRKP governance standards contain reusable governance patterns. |
| Decision | Reusable governance patterns are extracted into FAEP Standards rather than remaining only in FRKP. |
| Consequences | FRKP becomes a Reference Implementation; FAEP Standards become the reusable governance catalogue. |
| Related Standards | FAEP-STD-000 through FAEP-STD-006 |
| Related Specifications | FAEP-002; FRKP-004 |
| Related Programs | Program-000; Program-200 |

## FAEP-ADR-004 - FAEP Core as Platform Contract

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Future Financial AI projects require common contracts. |
| Decision | FAEP Core is the platform contract, not an application and not FRKP. |
| Consequences | Projects conform to Core contracts while retaining local implementation freedom. |
| Related Standards | FAEP-STD-000 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-000 |

## FAEP-ADR-005 - Sixteen-Engine Platform Decomposition

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | The earlier nine-engine model needed clearer separation of concerns. |
| Decision | FAEP Core uses sixteen engines, including Knowledge, Evidence, Governance, Document, Publishing, Version, and Release engines. |
| Consequences | Standards can map cleanly to engine responsibilities. |
| Related Standards | FAEP-STD-002; FAEP-STD-003; FAEP-STD-004; FAEP-STD-006 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-000 |

## FAEP-ADR-006 - Contracts Before Implementation

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Platform components need stable boundaries before code or project execution. |
| Decision | Every engine and integration point is defined by contract before implementation. |
| Consequences | PLAN-015 creates standards only and does not perform implementation. |
| Related Standards | FAEP-STD-000; FAEP-STD-005 |
| Related Specifications | FRKP-004 |
| Related Programs | All FAEP programs |

## FAEP-ADR-007 - Plugin Architecture for All Engines

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Engines must be replaceable and independently governed. |
| Decision | Engines are plugins registered, isolated, versioned, and replaceable through Core contracts. |
| Consequences | Plugin metadata and dependency governance remain future formalization work. |
| Related Standards | FAEP-STD-001; FAEP-STD-006 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-000; Program-300; Program-400; Program-500 |

## FAEP-ADR-008 - Hybrid Repository Strategy

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Core, knowledge, and projects need independent evolution. |
| Decision | FAEP uses one Core repository, multiple project repositories, and a knowledge corpus repository as the target model. |
| Consequences | Cross-repository references and evidence chains require future refinement. |
| Related Standards | FAEP-STD-001; FAEP-STD-003; FAEP-STD-004 |
| Related Specifications | FRKP-004; FRKP-005 |
| Related Programs | Program-000; Program-100; Program-200 |

## FAEP-ADR-009 - Text-Based Contracts Initially

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Early FAEP phases need speed and readability. |
| Decision | Core contracts and standards remain text-based initially. |
| Consequences | Markdown tables remain valid machine-readable navigation until schemas are introduced. |
| Related Standards | FAEP-STD-004 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-000 |

## FAEP-ADR-010 - Progressive Formalization

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Multiple implementations will eventually need formal schemas. |
| Decision | Contracts and standards formalize progressively as reuse demands increase. |
| Consequences | PLAN-016 can use text standards; PLAN-017 should formalize mature contracts. |
| Related Standards | FAEP-STD-000 through FAEP-STD-006 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-000 |

## FAEP-ADR-011 - Evidence-Driven Traceability

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Trustworthy financial AI requires provenance for claims, formulas, releases, and decisions. |
| Decision | Every platform artifact must be traceable to evidence. |
| Consequences | Evidence Standard and Navigation Standard are required Core governance standards. |
| Related Standards | FAEP-STD-003; FAEP-STD-004; FAEP-STD-006 |
| Related Specifications | FRKP-004; FRKP-005 |
| Related Programs | All FAEP programs |

## FAEP-ADR-012 - Human + AI Governance Model

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | AI agents assist with review, validation, and orchestration. |
| Decision | AI agents do not replace human governance authority. |
| Consequences | Human approval remains required for acceptance, freeze, release, and strategic decisions. |
| Related Standards | FAEP-STD-006 |
| Related Specifications | FAEP-002; FRKP-004 |
| Related Programs | Program-400; all programs |

## FAEP-ADR-013 - Bundle Lifecycle as Standard

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Bundle-007 validated a governed bundle lifecycle. |
| Decision | Bundle lifecycle is elevated into a FAEP Standard. |
| Consequences | FRKP layer deliverables remain reference-specific; lifecycle gates are reusable. |
| Related Standards | FAEP-STD-002; FAEP-STD-006 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-200; future business platforms |

## FAEP-ADR-014 - Minimum Viable Governance

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Governance overhead must be proportional to artifact criticality. |
| Decision | Governance rigor scales with criticality and risk. |
| Consequences | Minor corrections do not require release-level governance, but freezes and releases do. |
| Related Standards | FAEP-STD-000; FAEP-STD-006 |
| Related Specifications | FAEP-002; FRKP-004 |
| Related Programs | All FAEP programs |

## FAEP-ADR-015 - Domain Isolation Principle

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Platform domains need independent evolution. |
| Decision | Domains communicate through defined integration points only. |
| Consequences | FRKC, FRKP, Risk Platform, AI Platform, and Business Platforms retain separate responsibilities. |
| Related Standards | FAEP-STD-000; FAEP-STD-004 |
| Related Specifications | FRKP-004; FRKP-005 |
| Related Programs | All FAEP programs |

## FAEP-ADR-016 - AI Agent Readiness

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | AI agents must parse, validate, and navigate platform artifacts. |
| Decision | Every platform artifact must be AI-agent processable. |
| Consequences | Metadata, navigation, IDs, and cross-references become Core standard concerns. |
| Related Standards | FAEP-STD-001; FAEP-STD-004 |
| Related Specifications | FRKP-004; FRKP-005 |
| Related Programs | Program-400; all programs |

## FAEP-ADR-017 - FAEP Program as Governing Structure

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Multiple platforms require one program governance model. |
| Decision | FAEP Program governs all present and future Financial AI Platform projects. |
| Consequences | FAEP-000, FAEP-001, and FAEP-002 become source governance documents. |
| Related Standards | FAEP-STD-000 |
| Related Specifications | FAEP-000; FAEP-001; FAEP-002 |
| Related Programs | All FAEP programs |

## FAEP-ADR-018 - Program-Numbered Architecture

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Program responsibilities need stable identifiers. |
| Decision | FAEP uses Program-000 through Program-500 architecture numbering. |
| Consequences | Program identifiers are now covered by FAEP-STD-001. |
| Related Standards | FAEP-STD-001 |
| Related Specifications | FAEP-001 |
| Related Programs | All FAEP programs |

## FAEP-ADR-019 - FAEP-Namespaced Governance Documents

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Program documents need an identity distinct from FRKP. |
| Decision | FAEP program governance uses FAEP-prefixed documents. |
| Consequences | FAEP standards use FAEP-STD and FAEP-ADR namespaces. |
| Related Standards | FAEP-STD-001 |
| Related Specifications | FAEP-002 |
| Related Programs | Program-000 |

## FAEP-ADR-020 - Governance Before Expansion

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Business and risk platform expansion would otherwise duplicate governance. |
| Decision | Governance standards are established before new projects are bootstrapped. |
| Consequences | PLAN-015 precedes recommended PLAN-016 business platform bootstrap. |
| Related Standards | FAEP-STD-000 through FAEP-STD-006 |
| Related Specifications | FAEP-002; FRKP-004 |
| Related Programs | Program-000; Program-500 |

## FAEP-ADR-021 - Preservation of Existing Identifiers

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | FRKP has frozen artifacts and established document IDs. |
| Decision | Existing FRKP identifiers, Bundle IDs, and frozen artifacts are preserved. |
| Consequences | FAEP extraction uses mapping and elevation, not repository migration or renumbering. |
| Related Standards | FAEP-STD-001; FAEP-STD-006 |
| Related Specifications | FAEP-002 |
| Related Programs | Program-200 |

## FAEP-ADR-022 - FRKC as Knowledge Operating System

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | FAEP platforms require canonical financial risk knowledge. |
| Decision | FRKC is the Knowledge OS of FAEP. |
| Consequences | FRKC is canonical for knowledge and evidence, while platforms consume it through contracts. |
| Related Standards | FAEP-STD-003; FAEP-STD-004 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100 |

## FAEP-ADR-023 - Six-Layer Knowledge Architecture

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Knowledge, evidence, semantic structure, publication, execution, and AI retrieval have distinct responsibilities. |
| Decision | FRKC uses Canonical, Evidence, Semantic, Publication, Execution, and AI layers. |
| Consequences | Layer-specific FRKC rules remain FRKC-specific; evidence and navigation principles are generalized. |
| Related Standards | FAEP-STD-003; FAEP-STD-004 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100 |

## FAEP-ADR-024 - Canonical First - Single Source of Truth

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Duplicate knowledge creates inconsistency. |
| Decision | Canonical concepts, terms, definitions, formulas, and regulations exist in one authoritative location. |
| Consequences | Derived artifacts reference canonical sources. |
| Related Standards | FAEP-STD-003; FAEP-STD-004 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100; consuming programs |

## FAEP-ADR-025 - Evidence-Anchored Knowledge

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Knowledge must be verifiable. |
| Decision | Every FRKC knowledge artifact is traceable to certified evidence. |
| Consequences | Evidence Standard governs certification and mapping. |
| Related Standards | FAEP-STD-003 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100 |

## FAEP-ADR-026 - Knowledge Graph as Primary Navigation Model

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Directory navigation cannot express semantic relationships. |
| Decision | FRKC knowledge graph is the primary navigation model for knowledge consumers. |
| Consequences | FAEP semantic links and machine-readable navigation support graph evolution. |
| Related Standards | FAEP-STD-004 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100; Program-400 |

## FAEP-ADR-027 - Separate Evidence Graph from Knowledge Graph

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Evidence has a lifecycle distinct from knowledge. |
| Decision | Evidence objects are maintained in a separate evidence graph. |
| Consequences | FAEP Evidence Standard treats evidence as independently governed. |
| Related Standards | FAEP-STD-003 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100 |

## FAEP-ADR-028 - AI-Native Knowledge Design

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | AI agents are first-class platform citizens. |
| Decision | FRKC artifacts are designed for AI consumption by default. |
| Consequences | Navigation, citations, metadata, and cross-references must be machine-readable. |
| Related Standards | FAEP-STD-001; FAEP-STD-004 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100; Program-400 |

## FAEP-ADR-029 - Integration Through Contracts, Not Direct Access

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | FRKC internals must evolve independently. |
| Decision | Platforms integrate with FRKC through defined contracts and integration points. |
| Consequences | Direct access to platform internals is disallowed by architecture. |
| Related Standards | FAEP-STD-004 |
| Related Specifications | FRKP-004; FRKP-005 |
| Related Programs | All consuming programs |

## FAEP-ADR-030 - FRKC as Separate Repository

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Knowledge should not be owned by a single publishing platform. |
| Decision | FRKC is maintained as a separate repository from FRKP and other platforms. |
| Consequences | Cross-repository evidence and knowledge references require stable authority context. |
| Related Standards | FAEP-STD-001; FAEP-STD-003; FAEP-STD-004 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100; Program-200 |

## FAEP-ADR-031 - Evidence Certification Precedes Knowledge Publication

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Uncertified evidence cannot ground trustworthy published knowledge. |
| Decision | Evidence must be certified before supported knowledge is published from draft status. |
| Consequences | Evidence certification is a mandatory gate in bundle and release readiness. |
| Related Standards | FAEP-STD-002; FAEP-STD-003; FAEP-STD-006 |
| Related Specifications | FRKP-005 |
| Related Programs | Program-100; Program-200 |

## FAEP-ADR-032 - FAEP Standards as Core Governance Catalogue

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | Reusable governance rules were embedded in FRKP documents. |
| Decision | Reusable governance rules are elevated into FAEP-STD-000 through FAEP-STD-006. |
| Consequences | FAEP has an official platform-level standard catalogue for future programs. |
| Related Standards | FAEP-STD-000 through FAEP-STD-006 |
| Related Specifications | FAEP-002; FRKP-004 |
| Related Programs | Program-000; all future programs |

## FAEP-ADR-033 - FRKP Standards as Reference Implementation Standards

| Field | Value |
| --- | --- |
| Status | Accepted |
| Context | FRKP standards include both universal rules and project-specific publishing conventions. |
| Decision | FRKP standards remain valid for FRKP and become reference inputs to FAEP Standards, not program-wide authority by themselves. |
| Consequences | FRKP-specific layer, numbering, and publication conventions are preserved without forcing them on future platforms. |
| Related Standards | FAEP-STD-000; FAEP-STD-001; FAEP-STD-002; FAEP-STD-004 |
| Related Specifications | FRKP-004 |
| Related Programs | Program-200; future business platforms |

---

# 4. Deferred ADR Refinement

The following source decisions are not fully expanded in this registry because they are platform-specific or implementation-specific:

| Source | Decision | Classification | Reason |
| --- | --- | --- | --- |
| PLAN-011 AD-003 | Risk Project as external engine | Risk Platform-specific | Requires Risk Platform architecture plan |
| PLAN-011 AD-004 | IB Project as future downstream consumer | Business Platform-specific | Requires business bootstrap plan |
| FRKP-005 AD-018 | Multi-strategy retrieval | FRKC-specific / AI Platform-specific | Retrieval implementation deferred |
| FRKP-005 AD-020 | Context assembly with ranking | FRKC-specific / AI Platform-specific | Ranking implementation deferred |

---

# 5. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial centralized FAEP ADR registry created by PLAN-015 |
