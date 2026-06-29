# FP-VOL-001 — Platform Architecture

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FP-VOL-001 |
| Document Name | Financial Platform Handbook — Volume 1: Platform Architecture |
| Version | 1.0.0 |
| Status | Published |
| Category | Financial Platform Handbook |
| Owner | FRKP Publishing Office |
| Plan | PLAN-022 |
| Volume | Platform Architecture |
| Next Volume | FP-VOL-002 — Formula Engine |
| Related Documents | FAEP-000; FAEP-001; FAEP-002; FRKP-003; FRKP-004; FRKP-005; FRKP-PUB-000; FRKP-PUB-001; FRKP-PUB-002; FAEP-CAP-000; FAEP-CAP-001; FAEP-CONTRACT-000; FAEP-CONTRACT-001; FAEP-FOUNDATION-000; FAEP-FOUNDATION-001; FAEP-FOUNDATION-002; FAEP-STD-000; FAEP-STD-001; FAEP-STD-002; FAEP-STD-003; FAEP-STD-004; FAEP-STD-005; FAEP-STD-006; FAEP-ADR-000; FAEP-VALIDATION-000; FAEP-VALIDATION-001 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# Chapter 1 — Executive Summary

The Financial Platform is the unified technical foundation for building AI-augmented, evidence-driven, governance-controlled financial knowledge and engineering systems.

This volume — **Platform Architecture** — is the first of eight volumes in the Financial Platform Handbook. It introduces the entire platform ecosystem: its vision, architecture, components, governance model, and publication framework.

## Platform at a Glance

The Financial Platform is defined by three architectural layers containing nine core engines, extended to sixteen platform engines in the full specification, governed by fifteen Core Contracts, six platform standards, and thirty-five discovered candidate capabilities. All platform knowledge is managed through the FRKC Knowledge Operating System and published through the FRKP publishing pipeline.

## Audience

This volume serves as the entry point for:

- **Financial engineers** seeking to understand how knowledge, formulas, and risk analytics connect
- **Developers** building platform-conformant implementations
- **Solution architects** designing FAEP-conformant projects
- **IB Project members** adopting Financial Platform patterns for business delivery

## Reading Path

| Reader Type | Recommended Chapters |
| --- | --- |
| Executives and decision-makers | 1, 2, 11, 12 |
| Platform architects | 3, 4, 9, 10 |
| Financial engineers | 5, 6, 7, 8 |
| Developers and implementers | 4, 5, 6, 8, 9 |
| IB Project members | 2, 7, 8, 11, 15 |
| All readers | 12, 13, 14 |

## Volume Map

The eight volumes of the Financial Platform Handbook form a dependency graph:

```
FP-VOL-005 (Knowledge Platform) — provides knowledge model
    |
    v
FP-VOL-001 (Platform Architecture) — provides architectural context
    |
    +---> FP-VOL-002 (Formula Engine) — provides formulas
    |         |
    |         v
    +---> FP-VOL-003 (Risk Engine) — provides runtime
    |         |
    |         v
    +---> FP-VOL-004 (Risk Solution) — provides domain content
    |
    +---> FP-VOL-006 (Implementation Guide) — provides methodology
    |         |
    |         v
    +---> FP-VOL-007 (Operations Guide) — provides procedures
    |         |
    |         v
    +---> FP-VOL-008 (IB Integration Guide) — consumer-focused
```

Volume-1 (this document) is the recommended starting point for all readers.

---

# Chapter 2 — Financial Platform Vision

## 2.1 Vision

A unified Financial AI Platform ecosystem where knowledge, evidence, and computation converge to enable intelligent risk decision-making across all business domains.

## 2.2 Mission

Provide the governance, architecture, and standards that enable Financial AI Platform projects to operate coherently, reuse reliably, and evolve independently under a common program framework.

## 2.3 Platform Philosophy

The Financial Platform is built on six foundational philosophies:

| Pillar | Description |
| --- | --- |
| Knowledge First | Every artifact is grounded in structured, traceable knowledge. Knowledge precedes publication. |
| Evidence First | Every claim is supported by verifiable evidence. No publication without evidence mapping. |
| Architecture First | Platform architecture precedes implementation. Contracts are defined before engines. |
| Governance First | Governance is embedded in every artifact lifecycle. Every gate requires evidence. |
| AI Native | All artifacts are AI-agent processable by design. AI agents are first-class platform citizens. |
| Reusable by Design | Every pattern, template, contract, and standard is designed for reuse across the program. |

## 2.4 Strategic Objectives

| ID | Objective | Description |
| --- | --- | --- |
| SO-001 | Program Coherence | All FAEP projects operate under a unified governance framework |
| SO-002 | Reference Validation | FRKP validates Core Contracts as the first Reference Implementation |
| SO-003 | Knowledge Unification | FRKC provides a shared knowledge corpus consumed by all platform projects |
| SO-004 | Computational Integrity | Risk Platform delivers verified, evidence-backed risk analytics |
| SO-005 | AI Integration | AI Platform enables intelligent automation across the program |
| SO-006 | Business Enablement | Business Platforms deliver domain-specific value on FAEP infrastructure |

## 2.5 Program Architecture

The Financial Platform is organized into six program streams:

```
Program-000: Platform Core (FAEP)
    |
    v
Program-100: Knowledge Platform (FRKC)
    |
    v
Program-200: Publishing Platform (FRKP)
    |
    v
Program-300: Risk Platform
    |
    v
Program-400: AI Platform
    |
    v
Program-500: Business Platforms
```

Each program stream has a defined purpose, owner, dependencies, and maturity level. The full roadmap is documented in FAEP-001 (Program Roadmap).

## 2.6 Platform Principles

The Financial Platform is governed by eleven mandatory principles and seven recommended principles, as defined in the FAEP Core Platform Specification (FRKP-004). The mandatory principles include:

- Single Source of Truth — every artifact exists in exactly one authoritative location
- Everything Traceable — every claim, decision, and release is traceable to its origin
- Everything Versioned — every artifact uses semantic versioning
- Evidence Driven — no knowledge without supporting evidence
- Contract Before Implementation — every engine is defined by contract before building
- Reference Implementation Pattern — every contract is validated by at least one implementation
- Plugin Architecture — engines are plugins that conform to Core Contracts
- Domain Isolation — each domain is isolated; communication through defined integration points
- Human + AI Collaboration — AI agents assist but do not replace human governance authority
- Immutable Freeze — frozen artifacts must not be modified
- AI Agent Ready — every artifact must be processable by AI agents

---

# Chapter 3 — Platform Architecture

## 3.1 FAEP Definition

FAEP (Financial AI Engineering Platform) is the umbrella architecture for building AI-augmented, evidence-driven, governance-controlled financial knowledge and engineering platforms. It is:

- An architectural framework defining engines, boundaries, integration points, and data flows
- A governance container providing reusable standards, templates, and processes
- An integration blueprint specifying how knowledge, computation, analytics, evidence, and AI agents connect
- A bootstrap mechanism enabling rapid creation of new FAEP-conformant projects

FAEP is not a product, a single repository, a vendor-specific platform, or a replacement for any project implementation.

## 3.2 Three-Layer Architecture

The FAEP Master Architecture defines nine engines organized in three layers:

```
+-------------------------------------------------------------------+
|                      ORCHESTRATION LAYER                            |
|  +-------------+  +-------------+  +-------------------+          |
|  |  AI Agent   |  | Governance  |  | Project Bootstrap |          |
|  |   Engine    |  |   Engine    |  |      Engine       |          |
|  +-------------+  +-------------+  +-------------------+          |
+-------------------------------------------------------------------+
|                         DOMAIN LAYER                                |
|  +-------------+  +-------------+  +-------------+                 |
|  | Knowledge   |  |  Formula    |  | Risk        |                 |
|  |   Engine    |  |   Engine    |  |  Analytics  |                 |
|  +-------------+  +-------------+  +-------------+                 |
|  +-------------+  +-------------+                                  |
|  | Evidence    |  |  Runtime    |                                  |
|  |   Engine    |  |   Engine    |                                  |
|  +-------------+  +-------------+                                  |
+-------------------------------------------------------------------+
|                      PRESENTATION LAYER                              |
|  +--------------------------------------------------------+        |
|  |              Document Publishing Engine                  |        |
|  +--------------------------------------------------------+        |
+-------------------------------------------------------------------+
```

### 3.2.1 Orchestration Layer

The top layer manages platform-wide orchestration, governance, and project lifecycle.

| Engine | ID | Primary Responsibility |
| --- | --- | --- |
| AI Agent Engine | AAE-001 | Orchestrate and automate platform tasks through AI agents |
| Governance Engine | GE-001 | Define and enforce platform governance rules and standards |
| Project Bootstrap Engine | PBE-001 | Enable rapid creation of new FAEP-conformant projects |

### 3.2.2 Domain Layer

The middle layer contains the core knowledge and computation engines.

| Engine | ID | Primary Responsibility |
| --- | --- | --- |
| Knowledge Engine | KE-001 | Manage structured knowledge documents across all domains |
| Formula Engine | FE-001 | Define, derive, and manage mathematical formulas and computations |
| Risk Analytics Engine | RAE-001 | Execute risk calculations and produce analytics |
| Evidence Engine | EE-001 | Manage evidence identification, registration, mapping, and traceability |
| Runtime Engine | RE-001 | Provide execution environment for formulas and analytics |

### 3.2.3 Presentation Layer

The bottom layer handles document publication and navigation.

| Engine | ID | Primary Responsibility |
| --- | --- | --- |
| Document Publishing Engine | DPE-001 | Publish, navigate, and present platform documents |

## 3.3 Architecture Principles

All FAEP engines and projects follow ten architecture principles:

| # | Principle | Description |
| --- | --- | --- |
| 1 | Single Responsibility | Each engine has exactly one primary responsibility |
| 2 | Layered Architecture | Engines are organized in layers; dependencies flow downward |
| 3 | Separation of Concerns | Knowledge, computation, governance, and presentation are separate engines |
| 4 | Loose Coupling | Engines communicate through defined integration points, not direct dependencies |
| 5 | Evidence-Driven | Every publication is traceable to authoritative evidence |
| 6 | Deterministic Processing | Given the same inputs, engines produce the same outputs |
| 7 | Governance-Controlled | All engines operate within defined governance rules |
| 8 | AI-Augmented | AI agents assist but do not replace human governance authority |
| 9 | Bootstrappable | New projects can be created from reusable platform patterns |
| 10 | Extensible | New engines, domains, and integration points can be added without breaking existing ones |

## 3.4 Integration Model

Engines communicate through twelve defined integration points. Each is unidirectional or request-response, not bidirectional streaming. Integration interfaces are defined by contract (data schema, not implementation).

| Integration Point | Source Engine | Target Engine | Data |
| --- | --- | --- | --- |
| IP-001 | Knowledge Engine | Formula Engine | Domain knowledge, term definitions |
| IP-002 | Knowledge Engine | Evidence Engine | Document-to-evidence mappings |
| IP-003 | Knowledge Engine | Document Publishing | Finalized documents |
| IP-004 | Formula Engine | Risk Analytics Engine | Executable formulas, parameters |
| IP-005 | Formula Engine | Knowledge Engine | Formula definitions, symbols |
| IP-006 | Risk Analytics Engine | Runtime Engine | Calculation tasks, data |
| IP-007 | Runtime Engine | Risk Analytics Engine | Calculation outputs |
| IP-008 | Evidence Engine | Governance Engine | Evidence IDs, certification data |
| IP-009 | Evidence Engine | Knowledge Engine | Evidence IDs, mappings |
| IP-010 | Governance Engine | All Engines | Standards, policies, templates |
| IP-011 | AI Agent Engine | All Engines | Task assignments, status queries |
| IP-012 | Project Bootstrap Engine | Governance Engine | Template request, governance init |

## 3.5 Relationship Model

The FAEP ecosystem consists of five key entities:

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
    |     +-- Validated against FAEP Core
    |
    +-- IB Project (First Consumer — target audience)
          |
          +-- Consumes Financial Platform Handbook
          +-- Uses published volumes as IB Reference Materials
```

| Entity | Role | Current State |
| --- | --- | --- |
| FAEP | Platform umbrella architecture | Defined — 43 Foundation artifacts frozen at v1.0 |
| FRKC | Knowledge Operating System | Certified with observations — v0.1 operational |
| FRKP | First Reference Implementation | Active — v1.0 released, v1.1 in development |
| Risk Platform | Formula, Risk Analytics, Runtime Engine | Defined — not yet implemented as dedicated project |
| IB Project | First downstream business project | Not yet created — planned bootstrap target |

## 3.6 Repository Strategy

The Financial Platform recommends a Hybrid Repository Strategy:

- **FAEP Core Repository** (future) — Core Contracts, Platform Specification, shared governance
- **FRKP Repository** — First Reference Implementation (current active repository)
- **FRKC Repository** (future) — Authoritative Knowledge Corpus
- **Risk Project Repository** (future) — Computational Engine
- **IB Project Repository** (future) — Business Platform

Currently, all FAEP architecture definitions reside within the FRKP repository. A future migration will extract FAEP Core into a dedicated repository.

---

# Chapter 4 — Platform Components

## 4.1 Sixteen-Engine Model

The FAEP Core Platform Specification extends the nine-engine Master Architecture to sixteen engines. Each engine has a single primary responsibility and is governed by a Core Contract.

### 4.1.1 Knowledge Engine (KE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-KNW-001 |
| Responsibility | Manage structured knowledge documents across all domains |
| Reference Implementation | FRKP (RL, KB, AN layers) |
| Key Functions | Document creation, cross-referencing, versioning, knowledge retrieval |

### 4.1.2 Formula Engine (FE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-FRM-001 |
| Responsibility | Define, derive, and manage mathematical formulas and computations |
| Reference Implementation | FRKP (FC, MF layers); Risk Project (executable) |
| Key Functions | Formula definition, symbol standardization, mathematical derivation |

### 4.1.3 Risk Analytics Engine (RAE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-RSK-001 |
| Responsibility | Execute risk calculations and produce analytics |
| Reference Implementation | Risk Project (future) |
| Key Functions | Risk calculation, aggregation, scenario generation, stress testing |

### 4.1.4 Runtime Engine (RE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-RE-001 |
| Responsibility | Provide execution environment for formulas and analytics |
| Reference Implementation | Risk Project (future) |
| Key Functions | Batch processing, real-time calculation, data pipelining |

### 4.1.5 Evidence Engine (EE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-EVD-001 |
| Responsibility | Manage evidence identification, registration, mapping, and traceability |
| Reference Implementation | FRKC (knowledge corpus); FRKP (mappings) |
| Key Functions | Evidence identification, registration, mapping, certification |

### 4.1.6 Governance Engine (GE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-GOV-001 |
| Responsibility | Define and enforce platform-wide governance rules and standards |
| Reference Implementation | FRKP (Governance/); KPGF (future extract) |
| Key Functions | Standard definition, certification, compliance checking |

### 4.1.7 Document Engine (DE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-DOC-001 |
| Responsibility | Create, store, navigate, and publish platform documents |
| Reference Implementation | FRKP (all layers) |
| Key Functions | Document creation, navigation generation, cross-reference validation |

### 4.1.8 Publishing Engine (PE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-PE-001 |
| Responsibility | Manage publication lifecycle from review-ready to released |
| Reference Implementation | FRKP (bundle review, freeze, release) |
| Key Functions | Publication orchestration, release packaging, distribution |

### 4.1.9 AI Agent Engine (AAE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-AGT-001 |
| Responsibility | Orchestrate and automate platform tasks through AI agents |
| Reference Implementation | FRKP (AI Operating Model patterns) |
| Key Functions | Task orchestration, validation, cross-reference checking, state monitoring |

### 4.1.10 Bootstrap Engine (BE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-PRJ-001 |
| Responsibility | Enable rapid creation of new FAEP-conformant projects |
| Reference Implementation | FRKP (Templates/); FAEP Core (future) |
| Key Functions | Template application, repository scaffolding, governance initialization |

### 4.1.11 Plugin Engine (PLE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-PLG-001 |
| Responsibility | Manage plugin registration, isolation, lifecycle, and dependency resolution |
| Reference Implementation | FAEP Core (future) |
| Key Functions | Plugin registration, dependency resolution, lifecycle management |

### 4.1.12 Workflow Engine (WE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-WE-001 |
| Responsibility | Define and execute platform workflows |
| Reference Implementation | FRKP (evidence-driven publishing workflow) |
| Key Functions | Workflow definition, state machine management, task orchestration |

### 4.1.13 Search Engine (SE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-SE-001 |
| Responsibility | Provide search and retrieval across all platform artifacts |
| Reference Implementation | FRKP (navigation, cross-reference, master index) |
| Key Functions | Full-text search, metadata search, cross-reference search |

### 4.1.14 Metadata Engine (ME-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-MET-001 |
| Responsibility | Manage metadata for all platform artifacts |
| Reference Implementation | FRKP (document information, standards) |
| Key Functions | Metadata schema definition, extraction, validation |

### 4.1.15 Version Engine (VE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-VER-001 |
| Responsibility | Manage versioning of all platform artifacts |
| Reference Implementation | FRKP (VERSION, CHANGELOG, semantic versioning) |
| Key Functions | Version assignment, compatibility checking, history management |

### 4.1.16 Release Engine (RLE-001)

| Attribute | Value |
| --- | --- |
| Core Contract | CC-REL-001 |
| Responsibility | Manage platform releases from readiness assessment to distribution |
| Reference Implementation | FRKP (v1.0 release, v1.1 release process) |
| Key Functions | Release readiness assessment, packaging, validation, certification |

## 4.2 Core Contracts

The sixteen engines are governed by fifteen Core Contracts. Each contract defines input contract, output contract, boundary contract, integration contract, lifecycle contract, and governance contract.

| Contract ID | Name | Owner Engine |
| --- | --- | --- |
| CC-PRJ-001 | Project Contract | Bootstrap Engine |
| CC-BUN-001 | Bundle Contract | Governance Engine |
| CC-KNW-001 | Knowledge Contract | Knowledge Engine |
| CC-EVD-001 | Evidence Contract | Evidence Engine |
| CC-FRM-001 | Formula Contract | Formula Engine |
| CC-RSK-001 | Risk Engine Contract | Risk Analytics Engine |
| CC-DOC-001 | Document Contract | Document Engine |
| CC-NAV-001 | Navigation Contract | Document Engine |
| CC-MET-001 | Metadata Contract | Metadata Engine |
| CC-VER-001 | Version Contract | Version Engine |
| CC-REL-001 | Release Contract | Release Engine |
| CC-PLG-001 | Plugin Contract | Plugin Engine |
| CC-AGT-001 | Agent Contract | AI Agent Engine |
| CC-GOV-001 | Governance Contract | Governance Engine |
| CC-SES-001 | Session Contract | AI Agent Engine |

## 4.3 Candidate Contracts

Ten Candidate Contracts have been identified for future Core Contract promotion, registered in FAEP-CONTRACT-001:

| Candidate ID | Title | Source Domain |
| --- | --- | --- |
| FAEP-CAND-001 | Compiler Pipeline Contract | Formula Engine |
| FAEP-CAND-002 | Execution Plan Contract | Runtime Engine |
| FAEP-CAND-003 | Determinism Modes Contract | Runtime Engine |
| FAEP-CAND-004 | Shadow Mode Migration Contract | Runtime Engine |
| FAEP-CAND-005 | Bitemporal Data Contract | Data Management |
| FAEP-CAND-006 | Universal Variable Codec Contract | Variable Management |
| FAEP-CAND-007 | Execution Mode Contract | Runtime Engine |
| FAEP-CAND-008 | Governance Guardian Contract | Governance Engine |
| FAEP-CAND-009 | PLAN Execution Contract | Governance Engine |
| FAEP-CAND-010 | Architecture Enforcement Contract | Governance Engine |

## 4.4 Reference Implementations

| Implementation | Role | Status |
| --- | --- | --- |
| FRKP | Primary — Knowledge, Evidence, Document, Publishing, Governance | Active (v1.0 stable) |
| Risk Project | Formula, Risk Analytics, Runtime | Future |
| IB Project | First Business Platform | Future |

---

# Chapter 5 — Formula Engine Overview

## 5.1 Purpose

The Formula Engine is the platform component responsible for defining, deriving, and managing mathematical formulas and computations. It bridges the gap between knowledge (what a formula means) and execution (how a formula computes).

## 5.2 Core Responsibilities

| Responsibility | Description |
| --- | --- |
| Formula Definition | Define formulas with precise mathematical notation, symbols, and parameters |
| Symbol Standardization | Maintain a canonical symbol registry shared across all formulas |
| Mathematical Derivation | Document the derivation chain from regulatory text to computable formula |
| Formula Catalog | Organize formulas in a searchable, cross-referenced catalog |
| Formula Computation | Provide executable formula contracts for runtime engines |

## 5.3 Formula Lifecycle

```
Specified -> Derived -> Cataloged -> Implemented -> Validated -> Frozen -> Superseded
```

| Stage | Description |
| --- | --- |
| Specified | Formula defined with symbols and parameters per regulatory source |
| Derived | Full mathematical derivation documented in Mathematical Foundation |
| Cataloged | Formula added to Formula Catalog with cross-references |
| Implemented | Executable implementation created in the computation engine |
| Validated | Results verified against expected outputs and reference data |
| Frozen | Immutable formula baseline with freeze certificate |
| Superseded | Replaced by newer formula version with traceable supersession chain |

## 5.4 Compiler Pipeline

The Formula Engine includes a multi-stage compiler pipeline for domain-specific formula language:

```
Source Text -> Lexer -> Parser -> AST -> Semantic Validation -> Optimization -> Canonical Plan -> Runtime Binding
```

Each stage transforms the formula representation toward deterministic executable form.

## 5.5 Integration with Other Engines

| Integration | Direction | Data |
| --- | --- | --- |
| Knowledge Engine | Bidirectional | Domain knowledge, term definitions; formula documentation |
| Risk Analytics Engine | Outbound | Executable formulas, parameters |
| Runtime Engine | Outbound | Canonical execution plans |
| Evidence Engine | Bidirectional | Formula evidence mapping |

## 5.6 Key Capabilities

| Capability ID | Title | Description |
| --- | --- | --- |
| CAP-EXE-001 | DSL Compilation Pipeline | Compile domain-specific formula language through pipeline stages |
| CAP-EXE-003 | Formula Governance Workflow | Manage formula lifecycle through defined states |
| CAP-EXE-010 | Evidence-Gated Promotion | Gate formula promotion on evidence submission |
| CAP-EXE-011 | Dependency Impact Analysis | Analyze direct and transitive formula dependencies |
| CAP-EXE-012 | Variable Resolution | Resolve formula variables across multiple dimensions |
| CAP-EXE-013 | Variable Codec Serialization | Serialize variables using codec system |

---

# Chapter 6 — Risk Engine Overview

## 6.1 Purpose

The Risk Engine provides the deterministic runtime execution environment for formulas and analytics. It is the computational backbone of the Financial Platform, ensuring that every calculation is repeatable, verifiable, and auditable.

## 6.2 Core Responsibilities

| Responsibility | Description |
| --- | --- |
| Deterministic Execution | Execute formulas deterministically — same inputs always produce same outputs |
| Execution Plan Management | Manage content-addressed execution plans with SHA-256 identity |
| Execution Mode Enforcement | Support PRODUCTION, REPLAY, SIMULATION, and DEBUG modes |
| Numeric Precision Governance | Enforce Decimal128 standard with HALF_EVEN rounding |
| Variable Resolution | Resolve variable values across context, scenario, and time dimensions |

## 6.3 Determinism Model

The Risk Engine guarantees determinism through:

- **Content-Addressed Plans** — execution plans are identified by SHA-256 hash of their content
- **Deterministic Numeric Precision** — Decimal128 with HALF_EVEN rounding ensures cross-platform consistency
- **Sandboxed Execution** — each execution mode has a defined sandbox policy
- **Governance Guards** — policy chain intercepts runtime execution to enforce lifecycle, safety, and governance rules

## 6.4 Execution Modes

| Mode | Purpose | Determinism Required | Sandbox Policy |
| --- | --- | --- | --- |
| PRODUCTION | Live risk calculation | Strict | Full governance enforcement |
| REPLAY | Re-execute prior calculations | Exact | Read-only; cached results |
| SIMULATION | What-if scenario analysis | Parameter-driven | Restricted write access |
| DEBUG | Developer troubleshooting | Relaxed | Full access; audit logging |

## 6.5 Execution Plan Architecture

Compiled formulas are represented as content-addressed execution plans with opcode-based intermediate representation:

```
Plan: SHA-256(content)
    Opcodes: CONST_DECIMAL, READ_INPUT, ADD, MULTIPLY, DIVIDE, COMPARE, etc.
    Dependencies: direct and transitive formula dependencies
    Caching: plan results cached by SHA-256 identity
    Replay: plans support deterministic re-execution
```

## 6.6 Integration with Other Engines

| Integration | Direction | Data |
| --- | --- | --- |
| Formula Engine | Inbound | Executable formulas and canonical plans |
| Risk Analytics Engine | Bidirectional | Calculation tasks and results |
| Governance Engine | Bidirectional | Compliance evidence and governance rules |

## 6.7 Key Capabilities

| Capability ID | Title | Description |
| --- | --- | --- |
| CAP-EXE-002 | Deterministic Runtime Execution | Execute formulas with deterministic guarantees |
| CAP-EXE-004 | Content-Addressed Execution Plans | Represent compiled formulas as SHA-256-addressed plans |
| CAP-EXE-005 | Execution Mode Enforcement | Execute in distinct modes with mode-specific policies |
| CAP-EXE-006 | Policy-First Governance Guard | Intercept runtime with policy chain guards |
| CAP-EXE-014 | Numeric Precision Governance | Enforce numeric precision policy across computations |

---

# Chapter 7 — Risk Solution Overview

## 7.1 Purpose

The Risk Solution component delivers domain-specific risk analytics on the Financial Platform. It is the primary business-facing capability, translating regulatory requirements into computable risk measures.

## 7.2 Risk Domains

The Financial Platform covers the following risk domains:

| Domain | Regulatory Framework | Key Risk Measures |
| --- | --- | --- |
| Market Risk | Basel III, FRTB | Value at Risk (VaR), Expected Shortfall, Standardized Approach charges |
| Credit Risk | IFRS 9, Basel III | Expected Credit Loss (ECL), Probability of Default (PD), Loss Given Default (LGD) |
| Operational Risk | Basel III | Operational Risk Capital, Standardized Measurement Approach (SMA), Loss Distribution |
| Liquidity Risk | Basel III | Liquidity Coverage Ratio (LCR), Net Stable Funding Ratio (NSFR) |
| Counterparty Credit Risk | SA-CCR, Basel III | Credit Valuation Adjustment (CVA), Debit Valuation Adjustment (DVA), Exposure at Default (EAD) |
| ICAAP | Internal | Capital adequacy assessment, stress testing integration |
| Stress Testing | Internal, Regulatory | Scenario analysis, capital adequacy, reverse stress testing |

## 7.3 Bundle Delivery Model

Risk content is delivered through the Bundle lifecycle — a structured process from planning through freeze certification.

| Bundle | Domain | Status |
| --- | --- | --- |
| BUNDLE-001 | Basel III Framework | Completed |
| BUNDLE-002 | FRTB | Completed |
| BUNDLE-003 | IFRS 9 | Completed |
| BUNDLE-004 | SA-CCR | Completed |
| BUNDLE-005 | Credit Valuation Adjustment (CVA) | Completed |
| BUNDLE-006 | Market Risk Standardized Approach | Completed |
| BUNDLE-007 | Operational Risk | Completed |
| BUNDLE-008 | Liquidity Risk | Planned |
| BUNDLE-009 | ICAAP | Planned |
| BUNDLE-010 | Stress Testing | Planned |

## 7.4 Knowledge Layering

Each risk bundle is published across seven knowledge layers:

```
RL (Reference Library) — regulatory evidence and source texts
KB (Knowledge Base) — explanatory content and framework description
AN (Analysis) — quantitative and qualitative analysis
FC (Formula Catalog) — computable formula definitions
MF (Mathematical Foundation) — derivations and proofs
IMP (Implementation Guide) — practical implementation guidance
ARCH (Architecture Guide) — architectural context and integration
```

## 7.5 Integration with Other Engines

| Integration | Direction | Data |
| --- | --- | --- |
| Formula Engine | Bidirectional | Domain-specific formula requirements |
| Knowledge Engine | Bidirectional | Risk knowledge documentation |
| Runtime Engine | Outbound | Risk calculation execution |
| Publishing Engine | Outbound | Risk content publication |

---

# Chapter 8 — Knowledge Platform Overview

## 8.1 Purpose

The Knowledge Platform — implemented as FRKC (Financial Risk Knowledge Corpus) — is the Knowledge Operating System of the Financial Platform. It is the canonical hub where all knowledge, evidence, ontology, and semantic structure reside.

FRKC is not a document repository. It is the active knowledge substrate upon which all platform engines depend.

## 8.2 Knowledge Philosophy

| Pillar | Description |
| --- | --- |
| Knowledge First | Knowledge is the primary asset. Every artifact exists to serve knowledge. |
| Canonical First | Every concept exists in exactly one authoritative location. No duplication. |
| Evidence First | Every knowledge artifact must be traceable to verifiable evidence. |
| Ontology First | Knowledge is a structured ontology of concepts, relations, and semantics. |
| AI Native | All artifacts are AI-agent processable by design. |
| Versioned Knowledge | Every artifact has a version history. Every change is traceable. |
| Semantic Navigation | Knowledge is navigable through semantic relationships, not just directories. |

## 8.3 Six-Layer Knowledge Architecture

```
+----------------------------------------------------------+
|                   AI LAYER                                  |
|  Chunks · Embeddings · Retrieval Context · Annotations     |
+----------------------------------------------------------+
|                 EXECUTION LAYER                             |
|  Executable Formulas · Runtime Parameters · Computation    |
+----------------------------------------------------------+
|                PUBLICATION LAYER                            |
|  Published Documents · Navigation · Indexes · Cross-Refs   |
+----------------------------------------------------------+
|                 SEMANTIC LAYER                              |
|  Ontology · Knowledge Graph · Semantic Relations           |
+----------------------------------------------------------+
|                 EVIDENCE LAYER                              |
|  Evidence IDs · Registers · Mappings · Certifications      |
+----------------------------------------------------------+
|                 CANONICAL LAYER                             |
|  Concepts · Definitions · Glossary · Formulas · Regulations |
+----------------------------------------------------------+
```

## 8.4 Knowledge Objects

FRKC defines eleven knowledge object types:

| Object Type | Purpose | Example ID |
| --- | --- | --- |
| Knowledge Item | Discrete unit of canonical knowledge | KB-271 |
| Evidence Item | Verifiable source supporting knowledge claims | EVD-000340 |
| Formula Knowledge | Mathematical formula with derivation context | FC-471 |
| Regulation | Regulatory text with FRKC mappings | REG-BASEL-003 |
| Definition | Canonical concept or term definition | DEF-PD-001 |
| Glossary | Collection of term-definition pairs | GLOSSARY-001 |
| Concept | Atomic unit of meaning in ontology | CONCEPT-LGD |
| Semantic Relation | Typed relationship between knowledge objects | REL-0001 |
| Ontology Node | Node in the FRKC ontology graph | ONT-RISK-001 |
| Knowledge Collection | Named group of knowledge objects | COLLECTION-BUNDLE-007 |
| Knowledge Version | Versioned snapshot of the FRKC corpus | FRKC-v0.1 |

## 8.5 Ontology Model

The FRKC ontology defines six concept types and ten relation types:

**Concept Types:** Event, Entity, Measure, Process, Relation, Rule

**Relation Types:** is_a, part_of, defined_by, supported_by, derived_from, computed_by, measured_by, governed_by, triggers, mitigates

## 8.6 Knowledge Graph

The canonical knowledge graph traversal path:

```
Concept -> Evidence -> Formula -> Risk Analytics -> Runtime -> Publication -> AI Agent
```

Each traversal follows typed, bidirectional relationships with defined cardinality and governance rules.

## 8.7 Semantic Retrieval

FRKC provides structured retrieval for AI agents:

| Operation | Description |
| --- | --- |
| search(query, filters, limit) | Semantic search with ranking |
| retrieve(object_id, version) | Full object retrieval |
| traverse(start_id, relation_types, depth) | Graph traversal |
| evidence_chain(object_id) | Complete evidence chain |
| context_assembly(query, max_tokens) | AI context with citations |

## 8.8 Integration with Platform Engines

FRKC integrates with every FAEP Platform through defined contracts:

| Platform | Contract | Key Integration |
| --- | --- | --- |
| FAEP Core | CC-KNW-001, CC-EVD-001, CC-MET-001 | Knowledge and evidence contracts |
| FRKP | Knowledge Source | Canonical knowledge for publication |
| Risk Platform | Formula Source | Formula specifications for computation |
| AI Platform | RAG Corpus | Authoritative corpus for AI context |
| Business Platforms | Domain Knowledge | Canonical terminology and regulatory mappings |

---

# Chapter 9 — Publishing Architecture

## 9.1 Purpose

The Publishing Architecture defines how Financial Platform knowledge is transformed from source material into published handbook volumes. FRKP (Financial Risk Knowledge Platform) serves as the official technical publishing platform.

## 9.2 Publishing Hierarchy

```
Financial Platform
    +-- Volume (thematic domain)
          +-- Chapter (functional area)
                +-- Section (knowledge unit)
                      +-- Knowledge Object (canonical knowledge)
                            +-- Reference (source code, formula, regulation)
```

| Level | Identifier Pattern | Example |
| --- | --- | --- |
| Financial Platform | `FP` | Financial Platform Handbook |
| Volume | `FP-VOL-{NNN}` | FP-VOL-001 — Platform Architecture |
| Chapter | `FP-VOL-{NNN}-CH-{NNN}` | FP-VOL-001-CH-002 — Platform Engine Model |
| Section | `FP-VOL-{NNN}-CH-{NNN}-SEC-{NNN}` | FP-VOL-001-CH-002-SEC-001 — Engine Taxonomy |
| Knowledge Object | `KO-{DOMAIN}-{NNN}` | KO-KNW-001 — Canonical Knowledge Storage |
| Reference | `REF-{TYPE}-{NNN}` | REF-SRC-001 — Risk Platform Compiler Pipeline |

## 9.3 Volume Architecture

The Financial Platform Handbook comprises eight volumes:

| Volume ID | Volume Name | Purpose |
| --- | --- | --- |
| FP-VOL-001 | Platform Architecture | Define the FAEP umbrella architecture, engine model, core contracts, and platform governance |
| FP-VOL-002 | Formula Engine | Document the formula language, compiler pipeline, optimization, and formula governance |
| FP-VOL-003 | Risk Engine | Describe deterministic runtime execution, execution plans, modes, precision |
| FP-VOL-004 | Risk Solution | Present domain-specific risk solutions across all risk domains |
| FP-VOL-005 | Knowledge Platform | Define the FRKC Knowledge Operating System, ontology, evidence management |
| FP-VOL-006 | Implementation Guide | Provide reference implementation methodology, bundle lifecycle, authoring |
| FP-VOL-007 | Operations Guide | Cover platform governance, release management, freeze certification |
| FP-VOL-008 | IB Integration Guide | Guide the integration of IB Project as first downstream consumer |

## 9.4 Publication Workflow

```
Knowledge Extraction -> Technical Review -> Publication Review -> Version Freeze -> Official Publication -> Continuous Update
```

| Stage | Duration | Exit Criteria |
| --- | --- | --- |
| Knowledge Extraction | 2-4 weeks | All source knowledge extracted and cataloged |
| Technical Review | 1-2 weeks | Technical accuracy confirmed; corrections applied |
| Publication Review | 1 week | Style compliance; navigation valid; cross-refs resolved |
| Version Freeze | 1 week | Freeze certificate issued; change log recorded |
| Official Publication | Continuous | Volume released; IB Project notified |

## 9.5 Publishing Principles

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

## 9.6 Recommended Publication Order

| Priority | Volume | Rationale |
| --- | --- | --- |
| 1 | FP-VOL-005 — Knowledge Platform | Knowledge model is foundation for all volumes |
| 2 | FP-VOL-001 — Platform Architecture | Architectural context required by all subsequent volumes |
| 3 | FP-VOL-002 — Formula Engine | Core technical capability; highest IB Project dependency |
| 4 | FP-VOL-003 — Risk Engine | Runtime engine documentation; dependency for Risk Solution |
| 5 | FP-VOL-004 — Risk Solution | Business-facing content; primary value for domain experts |
| 6 | FP-VOL-006 — Implementation Guide | Methodology for new implementations |
| 7 | FP-VOL-007 — Operations Guide | Operational procedures for platform operation |
| 8 | FP-VOL-008 — IB Integration Guide | Consumer-focused; requires all prior volumes |

---

# Chapter 10 — Traceability Model

## 10.1 Purpose

The Traceability Model ensures that every platform artifact — from evidence source to published volume — is connected through a documented, auditable chain. No claim exists without provenance. No release exists without evidence.

## 10.2 End-to-End Traceability Chain

```
Risk Source (code repository, formula definition, regulation PDF)
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

## 10.3 Traceability Rules

| Rule | Description |
| --- | --- |
| TR-001 | Every section must reference at least one Knowledge Object |
| TR-002 | Every Knowledge Object must trace to a Risk Source |
| TR-003 | Every Capability must be assigned to exactly one Section |
| TR-004 | Every Formula must trace to a Knowledge Object and a Section |
| TR-005 | Every IB Requirement must be traceable to a Section |
| TR-006 | Traceability chains must be bidirectional and resolvable |

## 10.4 Platform-Level Traceability

The FAEP Core Platform Specification defines cross-platform traceability contracts:

| From | To | Contract | Rule |
| --- | --- | --- | --- |
| Knowledge | Evidence | CC-EVD-001 | Every knowledge document references at least one evidence source |
| Evidence | Formula | CC-FRM-001 | Every formula references evidence sources for each input |
| Formula | Risk Analytics | CC-RSK-001 | Every risk calculation references the formula definition |
| Risk Analytics | Document | CC-DOC-001 | Every document containing risk analytics references the calculation source |
| Document | Release | CC-REL-001 | Every release references all included documents and their freeze certificates |
| Release | AI Agent | CC-AGT-001 | Every AI agent task references the release context |
| AI Agent | Governance | CC-GOV-001 | Every AI agent action must be governable and auditable |

## 10.5 Evidence-to-Governance Traceability

Every governance decision (review, freeze, release) is traceable to supporting evidence:

```
Evidence Source -> Evidence ID -> Publication Mapping -> Bundle Review -> Freeze Certification -> Release
```

## 10.6 Formula-to-Knowledge Traceability

Every formula is traceable to its knowledge source:

```
Regulatory Text -> RL -> KB -> AN -> FC -> MF -> IMP -> ARCH -> Executable Formula
```

---

# Chapter 11 — Capability Overview

## 11.1 Purpose

The Financial Platform has discovered thirty-five Candidate Capabilities across four domains. These capabilities represent implementation patterns demonstrated by FRKC, FRKP, and Risk Platform reference implementations.

## 11.2 Capability Discovery Summary

| Domain | Count | Provider | Consumer |
| --- | --- | --- | --- |
| Knowledge (CAP-KNW) | 8 | FRKC | FRKP, Risk Platform, AI Platform |
| Publishing (CAP-PUB) | 8 | FRKP | Bundle consumers, release consumers |
| Execution (CAP-EXE) | 14 | Risk Platform | Runtime, governance, developers |
| Governance (CAP-GOV) | 5 | FAEP, FRKP, Risk Platform | All programs |
| **Total** | **35** | | |

## 11.3 Capability Domains

### 11.3.1 Knowledge Capabilities

| ID | Title | Priority |
| --- | --- | --- |
| CAP-KNW-001 | Canonical Knowledge Storage | P2 |
| CAP-KNW-002 | Evidence Registration & Mapping | P1 |
| CAP-KNW-003 | Terminology Management | P3 |
| CAP-KNW-004 | Domain Classification | P3 |
| CAP-KNW-005 | Knowledge Layering | P2 |
| CAP-KNW-006 | Cross-Reference Linking | P1 |
| CAP-KNW-007 | Metadata Enforcement | P3 |
| CAP-KNW-008 | Knowledge Versioning | P3 |

### 11.3.2 Publishing Capabilities

| ID | Title | Priority |
| --- | --- | --- |
| CAP-PUB-001 | Evidence-Driven Publishing Workflow | P2 |
| CAP-PUB-002 | Bundle Lifecycle Management | P2 |
| CAP-PUB-003 | Document Authoring & Publication | P2 |
| CAP-PUB-004 | Navigation Index Management | P3 |
| CAP-PUB-005 | AI Agent Orchestration | P2 |
| CAP-PUB-006 | Session Handoff & Restoration | P2 |
| CAP-PUB-007 | Freeze Certification | P2 |
| CAP-PUB-008 | Archive Management | P4 |

### 11.3.3 Execution Capabilities

| ID | Title | Priority |
| --- | --- | --- |
| CAP-EXE-001 | DSL Compilation Pipeline | P1 |
| CAP-EXE-002 | Deterministic Runtime Execution | P1 |
| CAP-EXE-003 | Formula Governance Workflow | P2 |
| CAP-EXE-004 | Content-Addressed Execution Plans | P1 |
| CAP-EXE-005 | Execution Mode Enforcement | P1 |
| CAP-EXE-006 | Policy-First Governance Guard | P2 |
| CAP-EXE-007 | PLAN-based Execution | P1 |
| CAP-EXE-008 | Architecture Enforcement | P2 |
| CAP-EXE-009 | Release Snapshot Management | P2 |
| CAP-EXE-010 | Evidence-Gated Promotion | P2 |
| CAP-EXE-011 | Dependency Impact Analysis | P3 |
| CAP-EXE-012 | Variable Resolution | P3 |
| CAP-EXE-013 | Variable Codec Serialization | P3 |
| CAP-EXE-014 | Numeric Precision Governance | P3 |
| CAP-EXE-015 | Operator Review & Governance Metrics | P4 |

### 11.3.4 Governance Capabilities

| ID | Title | Priority |
| --- | --- | --- |
| CAP-GOV-001 | PLAN Governance Model | P1 |
| CAP-GOV-002 | Architecture Decision Records | P2 |
| CAP-GOV-003 | Contract Lifecycle Governance | P2 |
| CAP-GOV-004 | Foundation Freeze & Evolution | P3 |
| CAP-GOV-005 | Reference Implementation Validation | P3 |

## 11.4 Provider/Consumer Mapping

| Provider | Capabilities Provided | Capabilities Consumed |
| --- | --- | --- |
| FAEP | CAP-GOV-002, CAP-GOV-003, CAP-GOV-004, CAP-GOV-005 | All implementation feedback |
| FRKC | CAP-KNW-001 through CAP-KNW-008 | CAP-PUB-001, CAP-GOV-003, CAP-GOV-004 |
| FRKP | CAP-PUB-001 through CAP-PUB-008, CAP-GOV-001 | CAP-KNW-001 through CAP-KNW-008, CAP-GOV-002 |
| Risk Platform | CAP-EXE-001 through CAP-EXE-015, CAP-GOV-001, CAP-GOV-002 | CAP-KNW-002, CAP-KNW-006, CAP-PUB-006 |

## 11.5 Validation Priorities

| Priority | Capabilities | Rationale |
| --- | --- | --- |
| P1 — Critical | CAP-EXE-001, CAP-EXE-002, CAP-EXE-004, CAP-EXE-005, CAP-EXE-007, CAP-GOV-001, CAP-KNW-002, CAP-KNW-006 | Highest multi-program evidence; already registered as Candidate Contracts |
| P2 — High | CAP-KNW-001, CAP-KNW-005, CAP-PUB-001 through CAP-PUB-003, CAP-PUB-005 through CAP-PUB-007, CAP-EXE-003, CAP-EXE-006, CAP-EXE-008, CAP-EXE-009, CAP-EXE-010, CAP-GOV-002, CAP-GOV-003 | Implemented but need cross-program validation |
| P3 — Medium | CAP-KNW-003, CAP-KNW-004, CAP-KNW-007, CAP-KNW-008, CAP-PUB-004, CAP-EXE-011 through CAP-EXE-014, CAP-GOV-004, CAP-GOV-005 | Lower cross-program urgency |
| P4 — Low | CAP-PUB-008, CAP-EXE-015 | Narrow scope; low cross-program relevance |

---

# Chapter 12 — Reading Guide

## 12.1 How to Use This Handbook

The Financial Platform Handbook is designed for both sequential reading and targeted reference. Each volume is self-contained but references others for deeper context.

## 12.2 Volume Dependency Graph

```
FP-VOL-005 (Knowledge Platform)
    |  provides knowledge model
    v
FP-VOL-001 (Platform Architecture)
    |  provides architectural context
    v
FP-VOL-002 (Formula Engine) --> FP-VOL-003 (Risk Engine)
    |                               |
    v                               v
FP-VOL-004 (Risk Solution)
    |
    v
FP-VOL-006 (Implementation Guide) --> FP-VOL-007 (Operations Guide)
    |                                     |
    v                                     v
FP-VOL-008 (IB Integration Guide)
```

## 12.3 Recommended Reading Paths

| Objective | Path |
| --- | --- |
| Understand the platform vision | VOL-001 -> VOL-005 -> VOL-001 |
| Implement a formula engine | VOL-001 -> VOL-005 -> VOL-002 |
| Build a risk solution | VOL-001 -> VOL-005 -> VOL-002 -> VOL-003 -> VOL-004 |
| Bootstrap a new project | VOL-001 -> VOL-005 -> VOL-006 -> VOL-007 |
| Integrate IB Project | VOL-001 -> VOL-005 -> VOL-006 -> VOL-007 -> VOL-008 |
| Quick reference | VOL-001 (Chapter 11, 13, 14) |

## 12.4 Section Structure

Every section in the Handbook follows a consistent structure:

- **Knowledge Object Reference** — canonical knowledge source
- **Capability Mapping** — related capabilities
- **Evidence** — supporting evidence citations
- **Content** — section content
- **Cross-References** — related sections, objects, capabilities
- **IB Relevance** — relevance to IB Project implementers

## 12.5 Document Conventions

| Convention | Meaning |
| --- | --- |
| `FAEP-###` | Program governance document |
| `FRKP-###` | Reference implementation document |
| `CC-XXX-###` | Core Contract |
| `CAP-XXX-###` | Candidate Capability |
| `EVD-######` | Evidence record |
| `FP-VOL-###` | Financial Platform Handbook volume |
| `BUNDLE-###` | Knowledge bundle |

---

# Chapter 13 — Glossary

| Term | Definition |
| --- | --- |
| **Core Contract** | A formal specification defining inputs, outputs, boundaries, and governance for a platform engine |
| **Candidate Capability** | An implementation pattern discovered from a Reference Implementation, not yet formalized as a standard |
| **FAEP** | Financial AI Engineering Platform — the umbrella architecture for the Financial Platform |
| **FRKC** | Financial Risk Knowledge Corpus — the Knowledge Operating System of the Financial Platform |
| **FRKP** | Financial Risk Knowledge Platform — the first Reference Implementation and official publishing platform |
| **Foundation** | The frozen baseline of FAEP Core artifacts (43 artifacts at v1.0) |
| **Freeze Certificate** | A governance document certifying that a set of artifacts is frozen and immutable |
| **Knowledge Object** | A discrete unit of canonical knowledge in FRKC, with defined schema and lifecycle |
| **Knowledge OS** | The Knowledge Operating System model — FRKC as the active knowledge substrate for all platforms |
| **KPGF** | Knowledge Platform Governance Framework — the reusable governance framework extracted from FRKP |
| **Plugin** | A self-contained, contract-conformant component implementing one or more engine contracts |
| **Reference Implementation** | A FAEP Core-conformant project that validates Core Contracts through implementation |
| **Bundle** | A themed collection of knowledge artifacts delivered through the bundle lifecycle |
| **Evidence Chain** | The traceability path from a knowledge claim through evidence sources to original regulatory text |
| **Deterministic Execution** | Execution that produces identical outputs for identical inputs, guaranteed by the platform |
| **Execution Plan** | A content-addressed, opcode-based representation of a compiled formula |
| **Content Addressing** | Identifying artifacts by SHA-256 hash of their content for caching, identity, and replay |
| **Candidate Contract** | A proposed Core Contract in the process of validation before promotion to Core status |
| **Governance Guard** | A policy-chain component that intercepts runtime execution to enforce governance rules |
| **AI Agent Engine** | The platform engine responsible for AI agent orchestration, validation, and automation |

---

# Chapter 14 — References

## 14.1 Program Governance Documents

| Document ID | Title | Version |
| --- | --- | --- |
| FAEP-000 | FAEP Program Charter | 1.0.0 |
| FAEP-001 | FAEP Program Roadmap | 1.0.0 |
| FAEP-002 | FAEP Program Governance | 1.0.0 |
| FRKP-003 | FAEP Master Architecture | 1.0.0 |
| FRKP-004 | FAEP Core Platform Specification | 1.0.0 |
| FRKP-005 | FRKC Knowledge Operating System | 1.0.0 |

## 14.2 Foundation Documents

| Document ID | Title | Version |
| --- | --- | --- |
| FAEP-FOUNDATION-000 | Foundation Freeze Policy | 1.0.0 |
| FAEP-FOUNDATION-001 | Foundation Evolution Policy | 1.0.0 |
| FAEP-FOUNDATION-002 | Foundation Versioning Policy | 1.0.0 |

## 14.3 Standards

| Document ID | Title | Version |
| --- | --- | --- |
| FAEP-STD-000 | Standard Catalog | 1.0.0 |
| FAEP-STD-001 | Document Identification Standard | 1.0.0 |
| FAEP-STD-002 | Bundle Standard | 1.0.0 |
| FAEP-STD-003 | Evidence Standard | 1.0.0 |
| FAEP-STD-004 | Navigation and Cross-Reference Standard | 1.0.0 |
| FAEP-STD-005 | Architecture Decision Standard | 1.0.0 |
| FAEP-STD-006 | Release and Freeze Standard | 1.0.0 |

## 14.4 Publishing Architecture

| Document ID | Title | Version |
| --- | --- | --- |
| FRKP-PUB-000 | Financial Platform Publishing Architecture | 1.0.0 |
| FRKP-PUB-001 | Knowledge Mapping Model | 1.0.0 |
| FRKP-PUB-002 | Financial Platform Handbook Structure | 1.0.0 |

## 14.5 Capability and Contract Registries

| Document ID | Title | Version |
| --- | --- | --- |
| FAEP-CAP-000 | Capability Discovery Guide | 1.0.0 |
| FAEP-CAP-001 | Candidate Capability Registry | 1.0.0 |
| FAEP-CONTRACT-000 | Contract Lifecycle Standard | 1.0.0 |
| FAEP-CONTRACT-001 | Candidate Contract Registry | 1.0.0 |

## 14.6 Architecture Decisions

| Document ID | Title | Version |
| --- | --- | --- |
| FAEP-ADR-000 | Architecture Decision Registry | 1.0.0 |

## 14.7 Validation

| Document ID | Title | Version |
| --- | --- | --- |
| FAEP-VALIDATION-000 | Reference Implementation Validation Framework | 1.0.0 |
| FAEP-VALIDATION-001 | Reference Implementation Score Model | 1.0.0 |

## 14.8 Freeze Certificate

| Document ID | Title | Version |
| --- | --- | --- |
| FRKP-FREEZE-001 | FRKP Version 1 Freeze Certificate | 1.0.0 |

## 14.9 Evidence-Driven Publishing

| Document ID | Title | Version |
| --- | --- | --- |
| FRKP-FRKC-001 | Evidence-Driven Publishing Workflow | 1.0.0 |

---

# Chapter 15 — Next Volume

## 15.1 Volume Sequence

This volume (FP-VOL-001 — Platform Architecture) is the entry point to the Financial Platform Handbook. The next volume in the recommended publication sequence is:

## 15.2 FP-VOL-002 — Formula Engine

**Purpose:** Document the formula language, compiler pipeline, optimization, and formula governance.

**Target Audience:** Formula developers, compiler engineers, financial engineers, risk platform implementers.

**Key Content Areas:**

| Chapter | Title | Key Topics |
| --- | --- | --- |
| CH-01 | Formula Language | Language syntax, type system, expression model, domain-specific constructs |
| CH-02 | Lexical and Syntactic Analysis | Lexer architecture, parser design, AST structure, error handling |
| CH-03 | Compiler Pipeline | Pipeline architecture, semantic validation, intermediate representation |
| CH-04 | Compiler Optimization | Optimization passes, constant folding, dead code elimination |
| CH-05 | Canonical Plan Generation | Plan structure, opcode IR, dependency analysis |
| CH-06 | Formula Governance | Lifecycle states, maker-checker workflow, promotion workflow |

**Prerequisites:** FP-VOL-001 (this volume), FP-VOL-005 (Knowledge Platform)

**Estimated Publication Target:** Next PLAN cycle.

## 15.3 Future Volumes

| Sequence | Volume | Status |
| --- | --- | --- |
| After FP-VOL-002 | FP-VOL-003 — Risk Engine | Planned |
| After FP-VOL-003 | FP-VOL-004 — Risk Solution | Planned |
| Alongside FP-VOL-001 | FP-VOL-005 — Knowledge Platform | Reference in progress |
| After FP-VOL-004 | FP-VOL-006 — Implementation Guide | Planned |
| After FP-VOL-006 | FP-VOL-007 — Operations Guide | Planned |
| After all prior | FP-VOL-008 — IB Integration Guide | Planned |

## 15.4 Recommended PLAN-023

PLAN-023 should focus on **Financial Platform Handbook Volume-2 — Formula Engine**.

| Aspect | Description |
| --- | --- |
| Title | Financial Platform Handbook Volume-2 — Formula Engine |
| Objective | Write the second official handbook volume documenting the Formula Engine |
| Scope | Full volume: 6 chapters covering formula language, compiler pipeline, optimization, canonical plan generation, and formula governance |
| Source Evidence | Risk Platform compiler; FRKP FC and MF layers; FAEP-CAND-001, FAEP-CAND-002 |
| Capabilities Mapped | CAP-EXE-001, CAP-EXE-003, CAP-EXE-010, CAP-EXE-011 |
| Priority | High — highest IB Project dependency after Platform Architecture |

---

# Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Financial Platform Handbook Volume-1: Platform Architecture (PLAN-022) |

---

# Cross-Reference Index

| Reference ID | Target Document | Relationship | Version |
| --- | --- | --- | --- |
| REF-001 | FAEP-000 — Program Charter | derives-from | 1.0.0 |
| REF-002 | FAEP-001 — Program Roadmap | derives-from | 1.0.0 |
| REF-003 | FAEP-002 — Program Governance | derives-from | 1.0.0 |
| REF-004 | FRKP-003 — FAEP Master Architecture | derives-from | 1.0.0 |
| REF-005 | FRKP-004 — FAEP Core Platform Specification | derives-from | 1.0.0 |
| REF-006 | FRKP-005 — FRKC Knowledge OS | derives-from | 1.0.0 |
| REF-007 | FRKP-PUB-000 — Publishing Architecture | derives-from | 1.0.0 |
| REF-008 | FRKP-PUB-001 — Knowledge Mapping Model | derives-from | 1.0.0 |
| REF-009 | FRKP-PUB-002 — Handbook Structure | derives-from | 1.0.0 |
| REF-010 | FAEP-CAP-001 — Candidate Capability Registry | cites | 1.0.0 |
| REF-011 | FAEP-CONTRACT-001 — Candidate Contract Registry | cites | 1.0.0 |
| REF-012 | FAEP-FOUNDATION-000 — Foundation Freeze Policy | governs | 1.0.0 |
| REF-013 | FAEP-STD-001 — Document Identification Standard | governs | 1.0.0 |
| REF-014 | FAEP-STD-004 — Navigation and Cross-Reference Standard | governs | 1.0.0 |
| REF-015 | FAEP-ADR-000 — Architecture Decision Registry | cites | 1.0.0 |
