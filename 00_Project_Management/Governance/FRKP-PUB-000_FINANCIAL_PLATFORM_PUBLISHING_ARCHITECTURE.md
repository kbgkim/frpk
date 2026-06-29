# FRKP-PUB-000 — Financial Platform Publishing Architecture

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PUB-000 |
| Document Name | Financial Platform Publishing Architecture |
| Version | 1.0.0 |
| Status | Active |
| Category | Publishing Architecture |
| Owner | FRKP Publishing Office |
| Plan | PLAN-021 |
| Related Documents | FRKP-003; FRKP-004; FRKP-005; FAEP-CAP-000; FAEP-CAP-001; FAEP-FOUNDATION-000; FRKP-FRKC-001; FRKP-DOC-100 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# 1. Purpose

This document defines the **Financial Platform Publishing Architecture** — the official framework for transforming Risk Platform knowledge into publishable Financial Platform documentation.

FRKP is the designated technical publishing platform for the Financial Platform (FP). This architecture governs how source knowledge is identified, extracted, structured, reviewed, frozen, and published as the **Financial Platform Handbook** — the definitive reference for the IB Project and all downstream consumers.

---

# 2. Publishing Philosophy

## 2.1 FRKP as the Official Technical Publishing Platform

FRKP exists to publish financial risk knowledge. With the FAEP Foundation v1.0 frozen and the Risk Platform established as the primary Reference Implementation, FRKP's mission expands from internal knowledge management to **external technical publication**.

The Financial Platform Handbook is not a FRKP-internal artifact. It is the authoritative technical reference for the IB Project, regulators, implementers, and platform consumers.

## 2.2 Relationship Model

```
FAEP (Financial AI Engineering Platform)
  |
  +-- FRKC (Knowledge Operating System — canonical knowledge)
  |     |
  |     +-- Provides knowledge objects, evidence, ontology
  |
  +-- FRKP (Publishing Platform — official publisher)
  |     |
  |     +-- Produces Financial Platform Handbook
  |     +-- Owns publishing workflow, volumes, chapters, sections
  |
  +-- Risk Platform (Reference Implementation — source)
  |     |
  |     +-- Provides source code, formulas, architecture, capabilities
  |     +-- Validated against FAEP Core (PLAN-016)
  |
  +-- IB Project (First Consumer — target audience)
        |
        +-- Consumes Financial Platform Handbook
        +-- Uses published volumes as IB Reference Materials
```

**FAEP** is the architectural umbrella. **FRKC** is the knowledge source. **FRKP** is the publishing engine. **Risk Platform** is the demonstrated implementation. **IB Project** is the first downstream consumer.

Each relationship is unidirectional at the publishing level: source material flows from Risk Platform through FRKC knowledge objects into FRKP publications consumed by the IB Project.

## 2.3 Publishing Principles

| Principle | Description |
| --- | --- |
| PP-001 — Knowledge First | Every publication is grounded in FRKC canonical knowledge |
| PP-002 — Evidence First | Every publication claim is traceable to certified evidence |
| PP-003 — Architecture First | Publication structure is designed before content is written |
| PP-004 — Source Traceable | Every handbook section traces to Risk Platform source code |
| PP-005 — Capability Mapped | Every capability is assigned to exactly one volume/chapter/section |
| PP-006 — Consumer Ready | Publications target IB Project implementers and technical reviewers |
| PP-007 — Version Controlled | Every volume, chapter, and section is versioned independently |
| PP-008 — Freeze Governed | Publications follow FRKP freeze and release lifecycle |

---

# 3. Publishing Architecture

## 3.1 Publication Hierarchy

```
Financial Platform
  |
  +-- Volume (thematic domain — e.g., Platform Architecture)
  |     |
  |     +-- Chapter (functional area — e.g., FAEP Master Architecture)
  |     |     |
  |     |     +-- Section (knowledge unit — e.g., Platform Engine Model)
  |     |     |     |
  |     |     |     +-- Knowledge Object (canonical knowledge item)
  |     |     |     |     |
  |     |     |     |     +-- Reference (source code, formula, regulation)
  |     |     |     |
  |     |     |     +-- Knowledge Object (...)
  |     |     |
  |     |     +-- Section (...)
  |     |
  |     +-- Chapter (...)
  |
  +-- Volume (...)
```

## 3.2 Hierarchy Definitions

| Level | Definition | Identifier Pattern | Example |
| --- | --- | --- | --- |
| **Financial Platform** | The published body of knowledge | `FP` | Financial Platform Handbook |
| **Volume** | Thematic domain covering a major platform area | `FP-VOL-{NNN}` | FP-VOL-001 — Platform Architecture |
| **Chapter** | Functional area within a volume | `FP-VOL-{NNN}-CH-{NNN}` | FP-VOL-001-CH-002 — Platform Engine Model |
| **Section** | Self-contained knowledge unit within a chapter | `FP-VOL-{NNN}-CH-{NNN}-SEC-{NNN}` | FP-VOL-001-CH-002-SEC-001 — Engine Taxonomy |
| **Knowledge Object** | Canonical knowledge artifact from FRKC | `KO-{DOMAIN}-{NNN}` | KO-KNW-001 — Canonical Knowledge Storage |
| **Reference** | Source code, formula, regulation, or standard | `REF-{TYPE}-{NNN}` | REF-SRC-001 — Risk Platform Compiler Pipeline |

## 3.3 Traceability Chain

```
Risk Source (code, formula, regulation)
  |  identified by REF-{TYPE}-{NNN}
  v
Knowledge Object (FRKC canonical item)
  |  mapped by KO-{DOMAIN}-{NNN}
  v
Capability (Candidate Capability)
  |  assigned by CAP-{DOMAIN}-{NNN}
  v
Formula (canonical formula definition)
  |  referenced by FC-{NNN}
  v
Runtime (execution semantics and behavior)
  |  described by runtime specifications
  v
Document (published section content)
  |  published as section in FP-VOL-{NNN}-CH-{NNN}-SEC-{NNN}
  v
Publication (Financial Platform Handbook volume)
  |  released as FP-VOL-{NNN}
  v
IB Requirement (downstream consumer need)
  |  validated by IB Project traceability
```

---

# 4. Financial Platform Handbook Architecture

## 4.1 Volume Architecture

| Volume ID | Volume Name | Purpose |
| --- | --- | --- |
| FP-VOL-001 | Platform Architecture | Define the FAEP umbrella architecture, engine model, core contracts, and platform governance structure |
| FP-VOL-002 | Formula Engine | Document the formula language, compiler pipeline, optimization, and formula governance |
| FP-VOL-003 | Risk Engine | Describe deterministic runtime execution, execution plans, modes, precision, and variable resolution |
| FP-VOL-004 | Risk Solution | Present domain-specific risk solutions: market risk, credit risk, operational risk, liquidity, ICAAP, stress testing |
| FP-VOL-005 | Knowledge Platform | Define the FRKC Knowledge Operating System, knowledge objects, ontology, evidence management, and semantic retrieval |
| FP-VOL-006 | Implementation Guide | Provide reference implementation methodology, bundle lifecycle, document authoring, and evidence-driven publishing |
| FP-VOL-007 | Operations Guide | Cover platform governance, release management, freeze certification, AI agent operations, and session management |
| FP-VOL-008 | IB Integration Guide | Guide the integration of IB Project as the first downstream consumer of the Financial Platform |

## 4.2 Volume Justification

**Volume-1 — Platform Architecture**: Every platform decision depends on architectural foundations. This volume defines the structural framework that all other volumes reference. Without it, readers cannot understand how engines, contracts, and governance relate.

**Volume-2 — Formula Engine**: The Risk Platform's most sophisticated capability is its formula engine — a multi-stage compilation pipeline from domain-specific language to deterministic execution. This volume documents the complete formula lifecycle.

**Volume-3 — Risk Engine**: The runtime execution layer that makes formulas computable. Determinism, execution plans, modes, and numeric precision are engineering concerns that every platform implementer must understand.

**Volume-4 — Risk Solution**: The primary business-facing volume. Domain experts and risk practitioners need comprehensive treatments of each risk domain — market risk, credit risk, operational risk, and emerging domains.

**Volume-5 — Knowledge Platform**: The knowledge foundation that underpins every publication. FRKC is the authoritative knowledge source; this volume documents how knowledge is structured, versioned, and retrieved.

**Volume-6 — Implementation Guide**: Practical methodology for building FAEP-conformant implementations. Every project needs a repeatable process for knowledge engineering, bundle management, and evidence-driven publishing.

**Volume-7 — Operations Guide**: Governance and operational procedures for running the platform. Freeze certification, release management, AI agent operations, and continuous improvement are essential for platform sustainability.

**Volume-8 — IB Integration Guide**: The final volume bridges the Financial Platform Handbook to its primary consumer. The IB Project represents the first real-world validation of the publishing architecture.

---

# 5. Publishing Workflow

```
Knowledge Extraction
  |
  |-- Source code analysis
  |-- Formula extraction
  |-- Architecture documentation
  |-- Capability identification
  v
Technical Review
  |
  |-- Peer review by platform engineers
  |-- Accuracy verification against source
  |-- Completeness check
  v
Publication Review
  |
  |-- Style and formatting compliance
  |-- Cross-reference validation
  |-- Navigation structure verification
  |-- FAEP standard compliance
  v
Version Freeze
  |
  |-- Scope freeze
  |-- Change control activation
  |-- Correction-only mode
  v
Official Publication
  |
  |-- Volume release
  |-- Archive to 13_Output/
  |-- Notification to IB Project
  v
Continuous Update
  |
  |-- Errata process
  |-- Minor revision cycle
  |-- Major revision cycle
```

## 5.1 Stage Definitions

| Stage | Entry Criteria | Exit Criteria | Duration Target |
| --- | --- | --- | --- |
| Knowledge Extraction | Source identified; evidence mapped | All source knowledge extracted and cataloged | 2-4 weeks per volume |
| Technical Review | Extraction complete; KO drafted | Technical accuracy confirmed; corrections applied | 1-2 weeks per volume |
| Publication Review | Technical review passed | Style compliance; navigation valid; cross-refs resolved | 1 week per volume |
| Version Freeze | Publication review passed | Freeze certificate issued; change log recorded | 1 week per volume |
| Official Publication | Freeze certified | Volume released to 13_Output/; IB Project notified | Continuous |

---

# 6. Traceability Model

## 6.1 End-to-End Traceability

```
Risk Source (code repository, formula definition, regulation PDF)
  |  REF-001: Risk Platform Core Compiler
  |  REF-002: Basel III Regulatory Text
  |  REF-003: IFRS 9 Accounting Standard
  v
Knowledge Object (FRKC canonical item with ID, version, evidence)
  |  KO-EXE-001: DSL Compilation Knowledge
  |  KO-KNW-002: Evidence Registration Standard
  v
Formula (canonical formula with catalog ID, mathematical definition)
  |  FC-471: Operational Risk Loss Distribution
  |  FC-461: Covariance Matrix Computation
  v
Capability (Candidate Capability with provider/consumer mapping)
  |  CAP-EXE-001: DSL Compilation Pipeline
  |  CAP-PUB-001: Evidence-Driven Publishing
  v
Publication (Volume, Chapter, Section with document ID)
  |  FP-VOL-002-CH-003-SEC-001: Compiler Pipeline Stages
  |  FP-VOL-006-CH-005-SEC-001: Evidence-Driven Workflow
  v
IB Requirement (downstream consumer traceability)
  |  IB-REQ-042: Formula compilation must be deterministic
  |  IB-REQ-057: All publications must cite evidence
```

## 6.2 Traceability Rules

| Rule | Description |
| --- | --- |
| TR-001 | Every section must reference at least one Knowledge Object |
| TR-002 | Every Knowledge Object must trace to a Risk Source |
| TR-003 | Every Capability must be assigned to exactly one Section |
| TR-004 | Every Formula must trace to a Knowledge Object and a Section |
| TR-005 | Every IB Requirement must be traceable to a Section |
| TR-006 | Traceability chains must be bidirectional and resolvable |

---

# 7. Governance Integration

## 7.1 Relationship to Existing Governance

| Governance Artifact | Relationship |
| --- | --- |
| FAEP Foundation v1.0 | Publishing architecture operates within frozen Foundation boundaries |
| FAEP-CAP-000/CAP-001 | Capability registry provides the capability-to-publication mapping |
| FAEP-CONTRACT-000/CONTRACT-001 | Publications may reference Candidate Contracts but not promote them |
| FRKP-FRKC-001 (Evidence-Driven Workflow) | Publishing workflow extends the evidence-driven model |
| FRKP-DOC-100 (Master Document Index) | PUB documents registered in the master index |
| FAEP-STD-004 (Navigation Standard) | Volumes, chapters, and sections follow navigation standards |

## 7.2 Publishing Authority

| Role | Responsibility |
| --- | --- |
| FRKP Publishing Office | Owns the publishing architecture and workflow |
| Technical Reviewer | Validates technical accuracy against source code |
| Publication Reviewer | Validates compliance with publishing standards |
| Freeze Authority | Certifies volume freeze and release |
| IB Project Liaison | Represents consumer requirements in publication planning |

---

# 8. Deliverables

| Deliverable | Description |
| --- | --- |
| FRKP-PUB-000 | Financial Platform Publishing Architecture (this document) |
| FRKP-PUB-001 | Knowledge Mapping Model — source-to-publication mapping methodology |
| FRKP-PUB-002 | Financial Platform Handbook Structure — complete volume/chapter/section design |
| Publishing Architecture Summary | Executive summary of the publishing architecture |
| Handbook Structure | Complete volume/chapter/section tree |
| Knowledge Mapping Summary | Source code to publication mapping overview |
| Capability Mapping Summary | 35 Candidate Capabilities mapped to volumes/chapters/sections |
| Traceability Summary | End-to-end traceability model |

---

# 9. Recommended Publication Order

| Priority | Volume | Rationale |
| --- | --- | --- |
| 1 | FP-VOL-005 — Knowledge Platform | Foundation for all other volumes; FRKC knowledge model must be published first |
| 2 | FP-VOL-001 — Platform Architecture | Architectural context required by all subsequent volumes |
| 3 | FP-VOL-002 — Formula Engine | Core technical capability; highest IB Project dependency |
| 4 | FP-VOL-003 — Risk Engine | Runtime engine documentation; direct dependency for Risk Solution |
| 5 | FP-VOL-004 — Risk Solution | Business-facing content; primary value for domain experts |
| 6 | FP-VOL-006 — Implementation Guide | Methodology documentation; required for new implementations |
| 7 | FP-VOL-007 — Operations Guide | Operational procedures; required for platform operation |
| 8 | FP-VOL-008 — IB Integration Guide | Consumer-focused; requires all prior volumes as prerequisites |

---

# 10. Recommended PLAN-022

PLAN-022 should focus on **Financial Platform Handbook Volume Pilot — Knowledge Platform.**

| Aspect | Description |
| --- | --- |
| Title | Financial Platform Handbook Volume Pilot |
| Objective | Write the first volume (FP-VOL-005 — Knowledge Platform) as a pilot to validate the publishing architecture end-to-end |
| Scope | Full volume: 6 chapters, 18+ sections, complete traceability from FRKC knowledge objects to published content |
| Outputs | FP-VOL-005 draft; validation report on publishing architecture; lessons learned for remaining volumes |
| Priority | High — validates the entire publishing workflow before committing to 8 volumes |

---

# 11. Summary

FRKP-PUB-000 establishes the Financial Platform Publishing Architecture. FRKP is the official technical publishing platform for the Financial Platform. The architecture defines the complete publication hierarchy (Financial Platform → Volume → Chapter → Section → Knowledge Object → Reference), the publishing workflow (Knowledge Extraction → Technical Review → Publication Review → Version Freeze → Official Publication), and the end-to-end traceability model (Risk Source → Knowledge → Formula → Capability → Publication → IB Requirement). Eight volumes are defined with clear justification and recommended publication order. PLAN-022 is recommended as a pilot volume to validate the architecture.

---

# Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Financial Platform Publishing Architecture (PLAN-021) |
