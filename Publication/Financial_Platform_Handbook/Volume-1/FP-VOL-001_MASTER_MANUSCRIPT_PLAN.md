# FP-VOL-001 — Master Manuscript Plan

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FP-VOL-001-MP-001 |
| Document Name | Financial Platform Handbook Volume-1 — Master Manuscript Plan |
| Volume Title | Platform Architecture |
| Version | 1.0.0 |
| Status | Active |
| Category | Master Manuscript Plan |
| Owner | FRKP Publishing Office |
| Plan | PLAN-023 |
| Related Documents | FP-VOL-001; FAEP-000; FAEP-001; FAEP-002; FRKP-003; FRKP-004; FRKP-005; FRKP-PUB-000; FRKP-PUB-001; FRKP-PUB-002; FRKP-PROGRAM-000; FRKP-PROGRAM-001; FRKP-PROGRAM-002; FRKP-PROGRAM-003; FRKP-PROGRAM-004; FAEP-CAP-000; FAEP-CAP-001; FAEP-CONTRACT-000; FAEP-CONTRACT-001; FAEP-FOUNDATION-000; FAEP-FOUNDATION-001; FAEP-FOUNDATION-002; FAEP-STD-000 through FAEP-STD-006; FAEP-ADR-000; FAEP-VALIDATION-000; FAEP-VALIDATION-001 |
| Created | 2026-06-29 |

---

## 1. Master Manuscript Summary

### 1.1 Volume Identity

| Attribute | Value |
| --- | --- |
| Volume ID | FP-VOL-001 |
| Volume Title | Platform Architecture |
| Series | Financial Platform Handbook |
| Edition | First Edition |
| Target Version | v1.0.0 (Published) |
| Status | Published (v1.0.0) |
| Next Revision | Planned (v1.1.0) |
| Next Volume | FP-VOL-002 — Formula Engine |

### 1.2 Scope Statement

Volume-1 defines the Financial AI Engineering Platform (FAEP) umbrella architecture. It introduces the platform vision, the three-layer nine-engine architecture model, the sixteen-engine extended model, the fifteen Core Contracts, all platform components, the integration model, the relationship between FAEP, FRKC, FRKP, Risk Platform, and IB Project, the traceability model, the capability discovery results, the publication architecture, and the governance framework. This volume serves as the entry point to the entire Financial Platform Handbook series.

### 1.3 Manuscript Architecture

The manuscript is organized into 15 chapters across four sections:

| Section | Chapters | Theme |
| --- | --- | --- |
| Introduction | 1-3 | Platform context, vision, and overview |
| Technical Architecture | 4-8 | Platform engines, contracts, and components |
| Cross-Cutting Concerns | 9-11 | Publication, traceability, governance |
| Reference | 12-15 | Reading guide, glossary, references, roadmap |

### 1.4 Total Estimated Length

15 chapters, approximately 1,400-1,600 equivalent lines (markdown), with 20+ diagrams, 40+ tables, and 5+ worked examples.

### 1.5 Completion Status

Volume-1 v1.0.0 is Published. This Manuscript Plan reflects the current published structure with recommended refinements for v1.1.0.

---

## 2. Chapter Planning Matrix

### Chapter 1 — Executive Summary

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-01 |
| **Chapter Purpose** | Provide a concise overview of the Financial Platform and Volume-1. Orient all reader types to the platform ecosystem and guide them to relevant chapters. |
| **Target Reader** | All readers, especially executives and decision-makers needing a high-level understanding before deep reading. |
| **Learning Objectives** | Understand what the Financial Platform is; identify the three architectural layers and nine core engines; understand the reading path options; know what subsequent volumes cover. |
| **Source Documents** | FRKP-003 (FAEP Master Architecture); FRKP-004 (FAEP Core Platform Specification); FAEP-000 (Program Charter); FAEP-001 (Program Roadmap) |
| **Source Risk Components** | Not applicable — this is an architectural overview chapter, not a risk-domain chapter |
| **Related Capabilities** | None directly — this chapter introduces the platform rather than detailing capabilities |
| **Related Knowledge Objects** | FRKC governance documents; FAEP-000, FAEP-001 |
| **Related Contracts** | None directly |
| **Related Standards** | FAEP-STD-001 (Document Identification); FAEP-STD-004 (Navigation) |
| **Required Diagrams** | 1 — Volume Map (volume dependency graph) |
| **Required Tables** | 1 — Reading Path by Reader Type; 1 — Chapter-to-Section mapping |
| **Required Examples** | None |
| **Cross References** | All subsequent chapters; FRKP-PUB-002 (Handbook Structure) |
| **Estimated Length** | 50-70 lines |
| **Completion Status** | Published |

---

### Chapter 2 — Platform Vision

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-02 |
| **Chapter Purpose** | Articulate the Financial Platform vision, mission, philosophy, strategic objectives, program architecture, and platform principles. Establish the strategic context for all technical content. |
| **Target Reader** | Executives, decision-makers, platform architects, IB Project members. |
| **Learning Objectives** | Understand the six platform philosophies (Knowledge First, Evidence First, Architecture First, Governance First, AI Native, Reusable by Design); learn the six strategic objectives; understand the six program streams (Program-000 through Program-500); know the eleven mandatory and seven recommended platform principles. |
| **Source Documents** | FAEP-000 (Program Charter); FAEP-001 (Program Roadmap); FAEP-002 (Program Governance); FRKP-004 (FAEP Core Platform Specification) |
| **Source Risk Components** | Not applicable — vision chapter |
| **Related Capabilities** | CAP-GOV-001 (PLAN Governance Model); CAP-GOV-002 (Architecture Decision Records) |
| **Related Knowledge Objects** | FAEP-000, FAEP-001, FAEP-002 |
| **Related Contracts** | CC-GOV-001 (Governance Contract) |
| **Related Standards** | FAEP-STD-000 (Standard Catalog); FAEP-STD-005 (Architecture Decision Standard) |
| **Required Diagrams** | 1 — Program Stream hierarchy diagram |
| **Required Tables** | 1 — Six Philosophies; 1 — Strategic Objectives; 1 — Platform Principles |
| **Required Examples** | None |
| **Cross References** | CH-03 (Platform Overview); CH-04 (Platform Architecture); CH-11 (Governance); FAEP-000, FAEP-001, FAEP-002 |
| **Estimated Length** | 70-90 lines |
| **Completion Status** | Published |

---

### Chapter 3 — Financial Platform Overview

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-03 |
| **Chapter Purpose** | Present the complete sixteen-engine platform model, all fifteen Core Contracts, ten Candidate Contracts, and the three reference implementations. Provide the component-level map of the entire Financial Platform. |
| **Target Reader** | Platform architects, developers, financial engineers, IB Project implementers. |
| **Learning Objectives** | Identify all sixteen platform engines and their primary responsibilities; understand the Core Contract model and all fifteen contracts; recognize the ten Candidate Contracts; know the three reference implementations (FRKP, Risk Project, IB Project); understand the integration model between engines. |
| **Source Documents** | FRKP-003 (FAEP Master Architecture); FRKP-004 (FAEP Core Platform Specification); FAEP-CONTRACT-001 (Candidate Contract Registry); FAEP-CAP-001 (Candidate Capability Registry) |
| **Source Risk Components** | BUNDLE-001 through BUNDLE-007 (all bundles reference the platform engine model for their ARCH layer); FRKC evidence EVD-000340 through EVD-000349 (operational risk evidence references engine architecture) |
| **Related Capabilities** | CAP-KNW-001 (Canonical Knowledge Storage); CAP-PUB-002 (Bundle Lifecycle Management); CAP-EXE-007 (PLAN-based Execution); CAP-GOV-003 (Contract Lifecycle Governance) |
| **Related Knowledge Objects** | KO-KNW-001 through KO-KNW-008; KO-PUB-001 through KO-PUB-008; KO-EXE-001 through KO-EXE-015; KO-GOV-001 through KO-GOV-005 |
| **Related Contracts** | All fifteen Core Contracts (CC-PRJ-001 through CC-SES-001) |
| **Related Standards** | FAEP-STD-001 (Document Identification); FAEP-STD-002 (Bundle Standard) |
| **Required Diagrams** | 1 — Sixteen-Engine Model diagram; 1 — Engine-to-Contract mapping; 1 — Reference Implementation landscape |
| **Required Tables** | 1 — Engine Registry (16 engines); 1 — Core Contract Registry (15 contracts); 1 — Candidate Contract Registry (10 candidates); 1 — Reference Implementation Status |
| **Required Examples** | 1 — Example engine-contract instantiation (walkthrough for one engine) |
| **Cross References** | CH-02 (Platform Vision); CH-04 (Platform Architecture); CH-09 (Publication Architecture); CH-11 (Governance) |
| **Estimated Length** | 120-150 lines |
| **Completion Status** | Published (as Chapter 4 — Platform Components) |

---

### Chapter 4 — Platform Architecture

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-04 |
| **Chapter Purpose** | Define the FAEP umbrella architecture, the three-layer nine-engine model, architecture principles, integration model, relationship model, and repository strategy. This is the technical core of the volume. |
| **Target Reader** | Platform architects, developers, solution architects, financial engineers. |
| **Learning Objectives** | Understand the FAEP definition and its role as architecture framework, governance container, integration blueprint, and bootstrap mechanism; learn the three-layer architecture (Orchestration, Domain, Presentation) and nine engines; know the ten architecture principles; understand the twelve integration points; recognize the FAEP ecosystem entities (FAEP, FRKC, FRKP, Risk Platform, IB Project) and their relationships; understand the hybrid repository strategy. |
| **Source Documents** | FRKP-003 (FAEP Master Architecture); FRKP-004 (FAEP Core Platform Specification); FAEP-000 (Program Charter) |
| **Source Risk Components** | BUNDLE-007 ARCH-771 (Operational Risk Architecture) — reference architecture pattern; all bundle ARCH layers |
| **Related Capabilities** | CAP-EXE-008 (Architecture Enforcement); CAP-GOV-002 (Architecture Decision Records); CAP-EXE-006 (Policy-First Governance Guard) |
| **Related Knowledge Objects** | KO-KNW-005 (Knowledge Layering); KO-PUB-005 (AI Agent Orchestration); KO-EXE-008 (Architecture Enforcement) |
| **Related Contracts** | CC-PLG-001 (Plugin Contract); CC-GOV-001 (Governance Contract) |
| **Related Standards** | FAEP-STD-005 (Architecture Decision Standard); FAEP-STD-004 (Navigation and Cross-Reference) |
| **Required Diagrams** | 1 — Three-Layer Architecture; 1 — Integration Point Map; 1 — Relationship Model; 1 — Repository Strategy |
| **Required Tables** | 1 — Engine-by-Layer (9 engines); 1 — Architecture Principles (10); 1 — Integration Points (12); 1 — Entity Relationship Table |
| **Required Examples** | 1 — Integration flow walkthrough (Knowledge Engine to Formula Engine to Risk Analytics) |
| **Cross References** | CH-03 (Platform Overview); CH-05 (Formula Engine); CH-06 (Risk Engine); CH-08 (Knowledge Platform); CH-10 (Traceability); CH-11 (Governance) |
| **Estimated Length** | 150-180 lines |
| **Completion Status** | Published (as Chapter 3 — Platform Architecture) |

---

### Chapter 5 — Formula Engine

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-05 |
| **Chapter Purpose** | Introduce the Formula Engine — the platform component responsible for defining, deriving, and managing mathematical formulas and computations. Bridge the gap between knowledge (formula meaning) and execution (formula computation). |
| **Target Reader** | Financial engineers, formula developers, compiler engineers, risk platform implementers. |
| **Learning Objectives** | Understand the five core Formula Engine responsibilities; learn the seven-stage formula lifecycle (Specified through Superseded); know the compiler pipeline architecture (Lexer through Runtime Binding); understand integration with Knowledge Engine, Risk Analytics Engine, Runtime Engine, and Evidence Engine; recognize key capabilities (CAP-EXE-001, CAP-EXE-003, CAP-EXE-010, CAP-EXE-011). |
| **Source Documents** | FRKP-004 (FAEP Core Platform Specification) — CC-FRM-001; FRKP-003 (FAEP Master Architecture); FRKP-FC-* layers; FAEP-CAND-001 (Compiler Pipeline Contract); FAEP-CAND-002 (Execution Plan Contract) |
| **Source Risk Components** | BUNDLE-007 FC-471 (Operational Risk Capital Formula); BUNDLE-001 FC-401, FC-402; BUNDLE-002 FC-421 through FC-426; BUNDLE-003 FC-431 through FC-434; BUNDLE-004 FC-441 through FC-444; BUNDLE-005 FC-451 through FC-454; BUNDLE-006 FC-461 through FC-464 |
| **Related Capabilities** | CAP-EXE-001 (DSL Compilation Pipeline); CAP-EXE-003 (Formula Governance Workflow); CAP-EXE-010 (Evidence-Gated Promotion); CAP-EXE-011 (Dependency Impact Analysis); CAP-EXE-012 (Variable Resolution); CAP-EXE-013 (Variable Codec Serialization) |
| **Related Knowledge Objects** | KO-EXE-001 (DSL Compilation Pipeline); KO-EXE-003 (Formula Governance); KO-EXE-010 (Evidence-Gated Promotion); KO-EXE-011 (Dependency Impact) |
| **Related Contracts** | CC-FRM-001 (Formula Contract); FAEP-CAND-001 (Compiler Pipeline); FAEP-CAND-002 (Execution Plan); FAEP-CAND-006 (Variable Codec) |
| **Related Standards** | FAEP-STD-002 (Bundle Standard) |
| **Required Diagrams** | 1 — Formula Lifecycle state machine; 1 — Compiler Pipeline architecture |
| **Required Tables** | 1 — Formula Lifecycle Stages; 1 — Integration Points with other engines; 1 — Key Capabilities |
| **Required Examples** | 1 — Formula derivation walkthrough (regulatory text to computed formula) |
| **Cross References** | CH-03 (Platform Overview — CC-FRM-001); CH-04 (Platform Architecture — integration IP-004, IP-005); CH-06 (Risk Engine — execution); CH-08 (Knowledge Platform — knowledge source); FP-VOL-002 (full Formula Engine volume) |
| **Estimated Length** | 100-120 lines |
| **Completion Status** | Published |

---

### Chapter 6 — Risk Engine

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-06 |
| **Chapter Purpose** | Introduce the Risk Engine — the deterministic runtime execution environment for formulas and analytics. Describe how the platform ensures repeatable, verifiable, and auditable calculation. |
| **Target Reader** | Risk engineers, runtime developers, platform implementers, quantitative analysts. |
| **Learning Objectives** | Understand the five core Risk Engine responsibilities; learn the determinism model (content-addressed plans, Decimal128, sandboxed execution, governance guards); know the four execution modes (PRODUCTION, REPLAY, SIMULATION, DEBUG); understand the execution plan architecture with opcode-based IR; recognize key capabilities (CAP-EXE-002, CAP-EXE-004, CAP-EXE-005, CAP-EXE-006, CAP-EXE-014). |
| **Source Documents** | FRKP-004 (FAEP Core Platform Specification) — CC-RE-001, CC-RSK-001; FRKP-003 (FAEP Master Architecture); Risk Platform compiler and runtime architecture; FAEP-CAND-003 (Determinism Modes); FAEP-CAND-004 (Shadow Mode Migration); FAEP-CAND-007 (Execution Mode) |
| **Source Risk Components** | BUNDLE-007 ARCH-771 (Operational Risk Architecture — execution context); BUNDLE-001 ARCH-701; BUNDLE-002 ARCH-721; BUNDLE-003 ARCH-731; BUNDLE-004 ARCH-741; BUNDLE-005 ARCH-751; BUNDLE-006 ARCH-761 |
| **Related Capabilities** | CAP-EXE-002 (Deterministic Runtime Execution); CAP-EXE-004 (Content-Addressed Execution Plans); CAP-EXE-005 (Execution Mode Enforcement); CAP-EXE-006 (Policy-First Governance Guard); CAP-EXE-014 (Numeric Precision Governance) |
| **Related Knowledge Objects** | KO-EXE-002 (Deterministic Execution); KO-EXE-004 (Execution Plans); KO-EXE-005 (Execution Modes); KO-EXE-006 (Governance Guards); KO-EXE-014 (Numeric Precision) |
| **Related Contracts** | CC-RE-001 (Runtime Contract); CC-RSK-001 (Risk Engine Contract); FAEP-CAND-003 (Determinism Modes); FAEP-CAND-004 (Shadow Mode Migration); FAEP-CAND-007 (Execution Mode); FAEP-CAND-008 (Governance Guardian) |
| **Related Standards** | FAEP-STD-006 (Release and Freeze Standard) |
| **Required Diagrams** | 1 — Execution Plan Architecture; 1 — Governance Guard pipeline; 1 — Execution Mode decision tree |
| **Required Tables** | 1 — Execution Modes comparison; 1 — Key Capabilities; 1 — Integration Points |
| **Required Examples** | 1 — Deterministic execution walkthrough (same input produces same output across platforms) |
| **Cross References** | CH-03 (Platform Overview — CC-RE-001, CC-RSK-001); CH-04 (Platform Architecture — integration IP-006, IP-007); CH-05 (Formula Engine — formula input); CH-07 (Risk Solution — domain context); FP-VOL-003 (full Risk Engine volume) |
| **Estimated Length** | 100-120 lines |
| **Completion Status** | Published |

---

### Chapter 7 — Risk Solution

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-07 |
| **Chapter Purpose** | Present the domain-specific risk analytics delivered by the Financial Platform. Map regulatory frameworks to computable risk measures across all covered risk domains. Describe the bundle delivery model and knowledge layering. |
| **Target Reader** | Risk managers, financial engineers, domain experts, IB Project members, regulatory compliance teams. |
| **Learning Objectives** | Identify the seven risk domains covered (Market Risk, Credit Risk, Operational Risk, Liquidity Risk, Counterparty Credit Risk, ICAAP, Stress Testing); understand the regulatory framework binding for each domain; know the bundle delivery model and the seven knowledge layers (RL through ARCH); recognize the ten planned bundles (BUNDLE-001 through BUNDLE-010); understand how risk content flows from regulatory source to published handbook. |
| **Source Documents** | FRKP-004 (FAEP Core Platform Specification) — CC-RSK-001; FRKP-005 (FRKC Knowledge Operating System); BUNDLE-001 through BUNDLE-007 bundle reviews; FRKP-PUB-001 (Knowledge Mapping Model) |
| **Source Risk Components** | BUNDLE-001 (Basel III Framework); BUNDLE-002 (FRTB); BUNDLE-003 (IFRS 9); BUNDLE-004 (SA-CCR); BUNDLE-005 (CVA); BUNDLE-006 (Market Risk Standardized); BUNDLE-007 (Operational Risk SMA) — all seven completed bundles; FRKC evidence EVD-000330 through EVD-000349 (operational risk evidence) |
| **Related Capabilities** | CAP-KNW-002 (Evidence Registration & Mapping); CAP-KNW-005 (Knowledge Layering); CAP-PUB-002 (Bundle Lifecycle Management); CAP-PUB-001 (Evidence-Driven Publishing Workflow) |
| **Related Knowledge Objects** | KO-KNW-002 (Evidence Mapping); KO-KNW-005 (Knowledge Layering); KO-PUB-002 (Bundle Lifecycle); KO-PUB-001 (Evidence-Driven Publishing) |
| **Related Contracts** | CC-RSK-001 (Risk Engine Contract); CC-EVD-001 (Evidence Contract); CC-BUN-001 (Bundle Contract) |
| **Related Standards** | FAEP-STD-002 (Bundle Standard); FAEP-STD-003 (Evidence Standard) |
| **Required Diagrams** | 1 — Bundle Delivery Model; 1 — Knowledge Layering stack (RL through ARCH) |
| **Required Tables** | 1 — Risk Domains and Regulatory Frameworks; 1 — Bundle Registry (10 bundles); 1 — Bundle Status by Layer |
| **Required Examples** | 1 — Bundle traceability example (Operational Risk SMA — regulatory text to published section) |
| **Cross References** | CH-05 (Formula Engine — formula definitions per bundle); CH-06 (Risk Engine — execution); CH-08 (Knowledge Platform — FRKC knowledge source); CH-09 (Publication Architecture — bundle lifecycle); CH-10 (Traceability — evidence chain); FP-VOL-004 (full Risk Solution volume) |
| **Estimated Length** | 120-140 lines |
| **Completion Status** | Published |

---

### Chapter 8 — Knowledge Platform

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-08 |
| **Chapter Purpose** | Introduce the FRKC Knowledge Operating System — the canonical knowledge hub of the Financial Platform. Describe the knowledge philosophy, six-layer knowledge architecture, eleven knowledge object types, ontology model, knowledge graph, and semantic retrieval operations. |
| **Target Reader** | Knowledge engineers, platform architects, AI/ML engineers, document authors, IB Project members. |
| **Learning Objectives** | Understand FRKC as a Knowledge Operating System (not a document repository); learn the seven knowledge philosophy pillars; understand the six-layer architecture (Canonical through AI); identify all eleven knowledge object types; know the ontology model (six concept types, ten relation types); understand the knowledge graph traversal path; understand the five semantic retrieval operations for AI agents. |
| **Source Documents** | FRKP-005 (FRKC Knowledge Operating System); FRKP-PUB-001 (Knowledge Mapping Model); FAEP-CAP-001 (Candidate Capability Registry); FAEP-CAP-000 (Capability Discovery Guide) |
| **Source Risk Components** | All bundles contribute knowledge objects to FRKC; BUNDLE-007 KB-271, KB-272, AN-271 (knowledge layer examples); FRKC evidence EVD-000340 through EVD-000349 |
| **Related Capabilities** | CAP-KNW-001 (Canonical Knowledge Storage); CAP-KNW-002 (Evidence Registration & Mapping); CAP-KNW-003 (Terminology Management); CAP-KNW-004 (Domain Classification); CAP-KNW-005 (Knowledge Layering); CAP-KNW-006 (Cross-Reference Linking); CAP-KNW-007 (Metadata Enforcement); CAP-KNW-008 (Knowledge Versioning) |
| **Related Knowledge Objects** | All eleven KO types (Knowledge Item, Evidence Item, Formula Knowledge, Regulation, Definition, Glossary, Concept, Semantic Relation, Ontology Node, Knowledge Collection, Knowledge Version) |
| **Related Contracts** | CC-KNW-001 (Knowledge Contract); CC-EVD-001 (Evidence Contract); CC-MET-001 (Metadata Contract) |
| **Related Standards** | FAEP-STD-003 (Evidence Standard); FAEP-STD-004 (Navigation and Cross-Reference Standard) |
| **Required Diagrams** | 1 — Six-Layer Knowledge Architecture; 1 — Knowledge Graph traversal path; 1 — Ontology model (concept and relation types) |
| **Required Tables** | 1 — Eleven Knowledge Object Types; 1 — Ontology Concept Types and Relation Types; 1 — Integration with Platform Engines |
| **Required Examples** | 1 — Knowledge object instantiation example (Operational Risk concept through all six layers) |
| **Cross References** | CH-03 (Platform Overview — CC-KNW-001); CH-04 (Platform Architecture — integration IP-001, IP-002, IP-003); CH-07 (Risk Solution — knowledge layering); CH-09 (Publication Architecture — publication from knowledge); CH-10 (Traceability — knowledge-to-publication chain); FP-VOL-005 (full Knowledge Platform volume) |
| **Estimated Length** | 120-140 lines |
| **Completion Status** | Published |

---

### Chapter 9 — Publication Architecture

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-09 |
| **Chapter Purpose** | Define how Financial Platform knowledge is transformed from source material into published handbook volumes. Describe FRKP as the official technical publishing platform, the publishing hierarchy, volume architecture, publication workflow, publishing principles, and recommended publication order. |
| **Target Reader** | Publishing engineers, technical writers, editorial reviewers, FRKP Publishing Office, IB Project members. |
| **Learning Objectives** | Understand the publishing hierarchy (Platform through Reference); learn the eight-volume architecture and identifier patterns; know the seven-stage publication workflow (Knowledge Extraction through Official Publication); understand the eight publishing principles; learn the recommended publication priority order with rationale for each volume. |
| **Source Documents** | FRKP-PUB-000 (Financial Platform Publishing Architecture); FRKP-PUB-001 (Knowledge Mapping Model); FRKP-PUB-002 (Handbook Structure); FRKP-PROGRAM-000 (Publication Program); FRKP-PROGRAM-001 (Publication Workflow); FRKP-PROGRAM-002 (Editorial Standard); FRKP-PROGRAM-003 (Publication Backlog); FRKP-PROGRAM-004 (Publication Quality Gate) |
| **Source Risk Components** | Not directly — this is the publishing architecture that packages risk content; the ARCH layer of every bundle feeds into this architecture |
| **Related Capabilities** | CAP-PUB-001 (Evidence-Driven Publishing Workflow); CAP-PUB-002 (Bundle Lifecycle Management); CAP-PUB-003 (Document Authoring & Publication); CAP-PUB-004 (Navigation Index Management); CAP-PUB-005 (AI Agent Orchestration); CAP-PUB-006 (Session Handoff & Restoration); CAP-PUB-007 (Freeze Certification); CAP-PUB-008 (Archive Management) |
| **Related Knowledge Objects** | KO-PUB-001 through KO-PUB-008 (all publishing knowledge objects) |
| **Related Contracts** | CC-DOC-001 (Document Contract); CC-NAV-001 (Navigation Contract); CC-PE-001 (Publishing Contract); CC-REL-001 (Release Contract) |
| **Related Standards** | FAEP-STD-001 (Document Identification); FAEP-STD-004 (Navigation); FAEP-STD-006 (Release and Freeze) |
| **Required Diagrams** | 1 — Publishing Hierarchy tree; 1 — Publication Workflow (7 stages); 1 — Volume Dependency Graph |
| **Required Tables** | 1 — Publishing Hierarchy levels; 1 — Volume Architecture (8 volumes); 1 — Publication Workflow Stages; 1 — Recommended Publication Order; 1 — Publishing Principles |
| **Required Examples** | 1 — Section publication walkthrough (knowledge object through all seven workflow stages) |
| **Cross References** | CH-03 (Platform Overview — CC-DOC-001, CC-PE-001, CC-REL-001); CH-07 (Risk Solution — bundle delivery); CH-08 (Knowledge Platform — knowledge source); CH-10 (Traceability — publication traceability); CH-12 (Reading Guide — how to use the handbook); FP-VOL-006 (Implementation Guide); FP-VOL-007 (Operations Guide) |
| **Estimated Length** | 120-140 lines |
| **Completion Status** | Published |

---

### Chapter 10 — Traceability

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-10 |
| **Chapter Purpose** | Define the end-to-end traceability model that connects every platform artifact from evidence source to published volume. Ensure that no claim exists without provenance and no release exists without evidence. |
| **Target Reader** | Platform architects, governance reviewers, evidence engineers, quality assurance, IB Project members. |
| **Learning Objectives** | Understand the seven-step end-to-end traceability chain (Risk Source through IB Requirement); learn the six traceability rules (TR-001 through TR-006); understand the platform-level cross-contract traceability; know the evidence-to-governance traceability path; understand the formula-to-knowledge traceability through seven knowledge layers. |
| **Source Documents** | FRKP-004 (FAEP Core Platform Specification) — traceability sections; FAEP-STD-003 (Evidence Standard); FRKP-PUB-001 (Knowledge Mapping Model); FRKP-FRKC-001 (Evidence-Driven Publishing Workflow); FAEP-CONTRACT-000 (Contract Lifecycle Standard) |
| **Source Risk Components** | All bundle evidence chains; BUNDLE-007 evidence EVD-000340 through EVD-000349; CAN-CON-000032 operational risk evidence range |
| **Related Capabilities** | CAP-KNW-002 (Evidence Registration & Mapping); CAP-KNW-006 (Cross-Reference Linking); CAP-PUB-001 (Evidence-Driven Publishing Workflow); CAP-EXE-010 (Evidence-Gated Promotion) |
| **Related Knowledge Objects** | KO-KNW-002 (Evidence Mapping); KO-KNW-006 (Cross-Reference Linking); KO-PUB-001 (Evidence-Driven Publishing) |
| **Related Contracts** | CC-EVD-001 (Evidence Contract); CC-NAV-001 (Navigation Contract); CC-REL-001 (Release Contract) |
| **Related Standards** | FAEP-STD-003 (Evidence Standard); FAEP-STD-004 (Navigation and Cross-Reference) |
| **Required Diagrams** | 1 — End-to-End Traceability Chain; 1 — Platform-Level Cross-Contract Traceability; 1 — Evidence-to-Governance Traceability |
| **Required Tables** | 1 — Traceability Rules (6); 1 — Platform-Level Traceability (7 contract links); 1 — Formula-to-Knowledge Layer Mapping |
| **Required Examples** | 1 — Full traceability chain example (Operational Risk SMA — regulation to publication) |
| **Cross References** | CH-03 (Platform Overview — CC-EVD-001); CH-04 (Platform Architecture — integration IP-002, IP-008, IP-009); CH-07 (Risk Solution — evidence chain); CH-08 (Knowledge Platform — evidence management); CH-09 (Publication Architecture — publication traceability); CH-11 (Governance — governance evidence) |
| **Estimated Length** | 100-120 lines |
| **Completion Status** | Published |

---

### Chapter 11 — Governance

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-11 |
| **Chapter Purpose** | Define the platform governance model covering standards, contracts, foundations, capabilities, and validation. Explain how the Financial Platform enforces architectural compliance through governance rules embedded in every artifact lifecycle. |
| **Target Reader** | Governance reviewers, platform architects, FAEP Architecture Board, FRKP Publishing Office, project leads. |
| **Learning Objectives** | Understand the FAEP governance hierarchy (FAEP Core -> FAEP Foundation -> Reference Implementations); learn the six FAEP Standards (FAEP-STD-000 through FAEP-STD-006); understand the Contract Lifecycle (Idea through Retired) and the ten Candidate Contracts; know the Foundation freeze and evolution model; understand the Capability Discovery and Validation framework; recognize the Reference Implementation validation methodology. |
| **Source Documents** | FAEP-002 (Program Governance); FAEP-STD-000 through FAEP-STD-006; FAEP-CONTRACT-000 (Contract Lifecycle Standard); FAEP-CONTRACT-001 (Candidate Contract Registry); FAEP-FOUNDATION-000 (Foundation Freeze Policy); FAEP-FOUNDATION-001 (Foundation Evolution Policy); FAEP-FOUNDATION-002 (Foundation Versioning Policy); FAEP-CAP-000 (Capability Discovery Guide); FAEP-CAP-001 (Candidate Capability Registry); FAEP-VALIDATION-000 (Validation Framework); FAEP-VALIDATION-001 (Score Model); FAEP-ADR-000 (Architecture Decision Registry) |
| **Source Risk Components** | All bundles validate against governance standards; BUNDLE-007 freeze certificate FRKP-FREEZE-001; FRKP-FRKC-001 (Evidence-Driven Publishing Workflow) |
| **Related Capabilities** | CAP-GOV-001 (PLAN Governance Model); CAP-GOV-002 (Architecture Decision Records); CAP-GOV-003 (Contract Lifecycle Governance); CAP-GOV-004 (Foundation Freeze & Evolution); CAP-GOV-005 (Reference Implementation Validation) |
| **Related Knowledge Objects** | KO-GOV-001 (PLAN Governance); KO-GOV-002 (ADR); KO-GOV-003 (Contract Lifecycle); KO-GOV-004 (Foundation); KO-GOV-005 (Validation) |
| **Related Contracts** | CC-GOV-001 (Governance Contract); CC-PRJ-001 (Project Contract); CC-BUN-001 (Bundle Contract); CC-VER-001 (Version Contract); CC-REL-001 (Release Contract); all ten FAEP-CAND-XXX contracts |
| **Related Standards** | All six FAEP Standards (FAEP-STD-000 through FAEP-STD-006) |
| **Required Diagrams** | 1 — Governance Hierarchy; 1 — Contract Lifecycle state machine; 1 — Foundation Layer Architecture (Stable Foundation, Candidate Layer, Reference Implementations) |
| **Required Tables** | 1 — Standards Registry; 1 — Contract Lifecycle Stages; 1 — Candidate Contract Registry; 1 — Validation Levels; 1 — Foundation Artifact Categories |
| **Required Examples** | 1 — Contract lifecycle walkthrough (candidate to core promotion) |
| **Cross References** | CH-02 (Platform Vision — governance principles); CH-03 (Platform Overview — contracts); CH-04 (Platform Architecture — governance layer); CH-09 (Publication Architecture — publication governance); CH-10 (Traceability — governance traceability); FAEP-002, FAEP-STD-000 through FAEP-STD-006, FAEP-FOUNDATION-000/001/002, FAEP-CONTRACT-000/001, FAEP-VALIDATION-000/001 |
| **Estimated Length** | 130-160 lines |
| **Completion Status** | To be refined (content partially distributed in other chapters) |

---

### Chapter 12 — Reading Guide

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-12 |
| **Chapter Purpose** | Provide navigation guidance for all reader types. Define how to use the handbook, the volume dependency graph, recommended reading paths, section structure conventions, and document identifier conventions. |
| **Target Reader** | All readers — serves as the navigation reference for the entire handbook series. |
| **Learning Objectives** | Understand the handbook design philosophy (sequential and targeted reference); learn the volume dependency graph; identify the recommended reading path for each objective; understand the section structure template; recognize all document identifier conventions. |
| **Source Documents** | FRKP-PUB-002 (Financial Platform Handbook Structure); FRKP-PROGRAM-002 (Editorial Standard); FRKP-PROGRAM-003 (Publication Backlog) |
| **Source Risk Components** | Not applicable — reading guide only |
| **Related Capabilities** | CAP-PUB-004 (Navigation Index Management) |
| **Related Knowledge Objects** | KO-PUB-004 (Navigation) |
| **Related Contracts** | CC-NAV-001 (Navigation Contract); CC-DOC-001 (Document Contract) |
| **Related Standards** | FAEP-STD-004 (Navigation and Cross-Reference) |
| **Required Diagrams** | 1 — Volume Dependency Graph |
| **Required Tables** | 1 — Recommended Reading Paths; 1 — Section Structure Template; 1 — Document Conventions |
| **Required Examples** | None |
| **Cross References** | All chapters; CH-09 (Publication Architecture — volume architecture); FRKP-PUB-002 |
| **Estimated Length** | 40-60 lines |
| **Completion Status** | Published |

---

### Chapter 13 — Glossary

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-13 |
| **Chapter Purpose** | Define all technical terms used in Volume-1 with self-contained definitions. Serve as the authoritative terminology reference for the Financial Platform Handbook series. |
| **Target Reader** | All readers — primary reference for terminology. |
| **Learning Objectives** | Understand all platform-specific terms (Core Contract, Candidate Capability, FAEP, FRKC, FRKP, Foundation, Freeze Certificate, Knowledge Object, Knowledge OS, Plugin, Reference Implementation, Bundle, Evidence Chain, Deterministic Execution, Execution Plan, Content Addressing, Candidate Contract, Governance Guard, AI Agent Engine). |
| **Source Documents** | FAEP-000 (Program Charter); FRKP-003 (FAEP Master Architecture); FRKP-004 (FAEP Core Platform Specification); FRKP-005 (FRKC Knowledge Operating System); FRKP-PROGRAM-002 (Editorial Standard) |
| **Source Risk Components** | Not applicable — glossary only |
| **Related Capabilities** | CAP-KNW-003 (Terminology Management) |
| **Related Knowledge Objects** | KO-KNW-003 (Terminology Management); Glossary object type |
| **Related Contracts** | CC-KNW-001 (Knowledge Contract) |
| **Related Standards** | FAEP-STD-001 (Document Identification) |
| **Required Diagrams** | None |
| **Required Tables** | 1 — Glossary (20+ terms with definitions) |
| **Required Examples** | None |
| **Cross References** | All chapters; CH-12 (Reading Guide — document conventions) |
| **Estimated Length** | 30-50 lines |
| **Completion Status** | Published |

---

### Chapter 14 — References

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-14 |
| **Chapter Purpose** | Catalog all source documents referenced in Volume-1. Provide a complete bibliography organized by category (Program Governance, Foundation, Standards, Publishing Architecture, Capability and Contract Registries, Architecture Decisions, Validation, Freeze Certificates, Evidence-Driven Publishing). |
| **Target Reader** | All readers — primary reference for document identification and retrieval. |
| **Learning Objectives** | Locate any referenced document by ID; understand the document categorization; know the version of each referenced artifact. |
| **Source Documents** | All FAEP, FRKP, FAEP-FOUNDATION, FAEP-STD, FAEP-CAP, FAEP-CONTRACT, FAEP-ADR, FAEP-VALIDATION, FRKP-PUB, FRKP-PROGRAM, FRKP-FRKC, FRKP-FREEZE documents |
| **Source Risk Components** | Not applicable — references only |
| **Related Capabilities** | None directly |
| **Related Knowledge Objects** | All FAEP and FRKP governance documents |
| **Related Contracts** | All Core Contracts and Candidate Contracts |
| **Related Standards** | FAEP-STD-001 (Document Identification); FAEP-STD-004 (Navigation) |
| **Required Diagrams** | None |
| **Required Tables** | 8 — One per reference category |
| **Required Examples** | None |
| **Cross References** | All chapters; FAEP-STD-001 |
| **Estimated Length** | 50-70 lines |
| **Completion Status** | Published |

---

### Chapter 15 — Next Volumes

| Attribute | Value |
| --- | --- |
| **Chapter ID** | CH-15 |
| **Chapter Purpose** | Provide the roadmap for subsequent Financial Platform Handbook volumes. Describe the volume sequence, the next volume (FP-VOL-002 — Formula Engine) in detail, and the publication target for all future volumes. |
| **Target Reader** | All readers, especially IB Project members planning their adoption roadmap. |
| **Learning Objectives** | Understand the eight-volume sequence; know the scope, audience, chapter structure, and prerequisites for FP-VOL-002 (Formula Engine); understand the publication sequence and estimated timelines for all remaining volumes. |
| **Source Documents** | FRKP-PROGRAM-003 (Publication Backlog); FRKP-PUB-002 (Handbook Structure); PLAN-022 (Publication Program Bootstrap) |
| **Source Risk Components** | Not applicable — roadmap only |
| **Related Capabilities** | All capabilities across all domains (this chapter references the full capability landscape) |
| **Related Knowledge Objects** | FRKP-PROGRAM-003 |
| **Related Contracts** | All contracts (this chapter introduces the contract landscape for future volumes) |
| **Related Standards** | FAEP-STD-001 (Document Identification) |
| **Required Diagrams** | 1 — Volume Sequence (8 volumes) |
| **Required Tables** | 1 — Volume Sequence and Status; 1 — FP-VOL-002 Chapter Outline |
| **Required Examples** | None |
| **Cross References** | CH-01 (Executive Summary — reading path); CH-09 (Publication Architecture — recommended publication order); CH-12 (Reading Guide — volume dependency); FRKP-PROGRAM-003 |
| **Estimated Length** | 40-60 lines |
| **Completion Status** | Published |

---

## 3. Publication Readiness Matrix

| Dimension | CH-01 | CH-02 | CH-03 | CH-04 | CH-05 | CH-06 | CH-07 | CH-08 | CH-09 | CH-10 | CH-11 | CH-12 | CH-13 | CH-14 | CH-15 |
| --- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **Knowledge Readiness** | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% |
| **Diagram Readiness** | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 50% | 100% | N/A | N/A | 100% |
| **Reference Readiness** | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% |
| **Traceability Readiness** | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% |
| **Editorial Readiness** | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 80% | 100% | 100% | 100% | 100% |
| **Architecture Readiness** | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% |
| **Overall Chapter** | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 100% | 88% | 100% | 100% | 100% | 100% |

**Notes:**
- CH-11 (Governance) has lower readiness: content is distributed across CH-02, CH-03, CH-04, and CH-09 rather than consolidated. A dedicated governance chapter requires knowledge extraction from FAEP-002, FAEP-STD-000 through FAEP-STD-006, FAEP-FOUNDATION-000/001/002, FAEP-CONTRACT-000/001, FAEP-CAP-000/001, FAEP-VALIDATION-000/001. Diagrams for governance hierarchy and contract lifecycle need creation. Editorial consolidation needed to extract governance content from other chapters.
- All other chapters are published at v1.0.0 and ready for minor refinement.

**Volume Overall Readiness: 99%**

---

## 4. Writing Order Recommendation

| Priority | Chapter | Rationale |
| --- | --- | --- |
| 1 | CH-01 — Executive Summary | Provides the roadmap for all writing; must be written first to establish scope and audience mapping |
| 2 | CH-02 — Platform Vision | Establishes strategic context; foundational for all technical chapters |
| 3 | CH-04 — Platform Architecture | Technical core; defines architecture that CH-05 through CH-10 reference |
| 4 | CH-03 — Financial Platform Overview | Component catalog; depends on CH-04 architecture context for coherence |
| 5 | CH-05 — Formula Engine | First engine chapter; high IB Project dependency |
| 6 | CH-06 — Risk Engine | Second engine chapter; depends on CH-05 formula concepts |
| 7 | CH-07 — Risk Solution | Domain content; depends on CH-05 and CH-06 engine context |
| 8 | CH-08 — Knowledge Platform | Knowledge foundation; can proceed independently in parallel with CH-05/06/07 |
| 9 | CH-09 — Publication Architecture | Publishing model; depends on CH-04 architecture context |
| 10 | CH-10 — Traceability | Cross-cutting; depends on CH-07, CH-08, CH-09 understanding |
| 11 | CH-11 — Governance | Governance consolidation; depends on all technical chapters |
| 12 | CH-12 — Reading Guide | Navigation; should be reviewed last for cross-reference accuracy |
| 13 | CH-13 — Glossary | Terminology; iteratively refined as chapters are written |
| 14 | CH-14 — References | Bibliography; final compilation after all chapters reference their sources |
| 15 | CH-15 — Next Volumes | Roadmap; written last to reflect actual publication state |

**Recommendation for v1.1.0 revision order:**
1. CH-11 — Governance (new content consolidation; highest delta from current)
2. CH-04 — Platform Architecture (minor refinements)
3. CH-03 — Financial Platform Overview (minor refinements, rename from Platform Components to align with Manuscript Plan)
4. All other chapters (editorial alignment, cross-reference updates)

---

## 5. Risk Mapping Summary

| Risk ID | Risk Description | Impact | Likelihood | Mitigation |
| --- | --- | --- | --- | --- |
| RSK-MP-001 | CH-11 (Governance) content distributed across multiple chapters leads to duplication or inconsistency | Medium | High | Consolidate all governance content into CH-11; add cross-references from other chapters |
| RSK-MP-002 | Chapter sequence differs from published order (CH-03 and CH-04 swapped) causing reader confusion | Low | Medium | Add clear mapping note in v1.1.0 revision; maintain backward navigation compatibility |
| RSK-MP-003 | Source documents (FAEP Foundation, Standards) may evolve independently, creating reference drift | Medium | Medium | Each chapter must reference specific frozen versions; add version tracking in references |
| RSK-MP-004 | IB Project requirements may change scope before Volume-1 v1.1.0 | Low | Low | Volume-1 is foundational; scope changes addressed in later volumes |
| RSK-MP-005 | Governance chapter duplication with FRKP-PROGRAM-000/001/002/003/004 | Medium | Medium | CH-11 should be governance overview; detailed workflow content stays in program documents |
| RSK-MP-006 | Total volume length may exceed editorial standard limits for a single volume | Low | Low | Split risk: if >2,000 lines, consider demoting detailed engine content to dedicated volumes |

---

## 6. Recommended PLAN-024

| Aspect | Description |
| --- | --- |
| **Plan ID** | PLAN-024 |
| **Title** | Financial Platform Handbook Volume-1 — Editorial Revision and Governance Chapter |
| **Objective** | Execute the v1.1.0 editorial revision of FP-VOL-001. Consolidate the Governance chapter (CH-11), align chapter sequence to the Master Manuscript Plan, update cross-references, and publish Volume-1 v1.1.0. |
| **Scope** | Editorial revision of 15 chapters. New Governance chapter consolidation. Cross-reference audit. Diagram creation for governance hierarchy, contract lifecycle, and foundation architecture. Published volume update. |
| **Source Documents** | FP-VOL-001_MASTER_MANUSCRIPT_PLAN.md (this document); FP-VOL-001 v1.0.0; FAEP-002; FAEP-STD-000 through FAEP-STD-006; FAEP-FOUNDATION-000/001/002; FAEP-CONTRACT-000/001; FAEP-CAP-000/001; FAEP-VALIDATION-000/001 |
| **Priority** | Medium — Volume-1 is published and stable; revision is quality improvement, not defect fix |
| **Dependencies** | None — Volume-1 is self-contained |
| **Risk** | Low — editorial revision only; no new technical content |

---

## 7. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Master Manuscript Plan for Financial Platform Handbook Volume-1 (PLAN-023) |
