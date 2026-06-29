# FRKP-003 — FAEP Master Architecture

---

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-003 |
| Document Name | FAEP Master Architecture |
| Version | 1.0.0 |
| Status | Active |
| Plan | PLAN-011 |
| Owner | FAEP Governance |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Purpose | Define the FAEP umbrella architecture connecting FRKP, Risk Project, IB Project, KPGF, and AI Agent capability |

**Note on Document ID:** FRKP-002 is assigned to the AI Operating Model. This document uses FRKP-003 as the next available Governance document ID. A future repository split may renumber this document to a dedicated FAEP namespace.

---

# 1. Purpose

This document defines the **Financial AI Engineering Platform (FAEP)** umbrella architecture. FAEP is the architectural container that connects knowledge management, formula computation, risk analytics, runtime execution, evidence traceability, governance, AI agent orchestration, project bootstrapping, and document publishing into a cohesive platform.

FRKP (Financial Risk Knowledge Platform) serves as the first reference implementation of FAEP. The FAEP architecture is designed to be applicable beyond FRKP to additional domains, business projects, and risk engines.

---

# 2. Background

FRKP was initiated as a Financial Risk Knowledge Platform to systematize financial risk management knowledge. During its development across Version 1.0 (Bundles 1-6) and Version 1.1 (Bundle-7 Operational Risk), several patterns emerged:

- **Knowledge Engine patterns** — document layering (RL → KB → AN → FC → MF → IMP → ARCH), evidence-driven publishing, cross-referencing.
- **Governance patterns** — document ID standards, bundle lifecycle, freeze certification, plan-based execution.
- **Evidence patterns** — evidence-to-publication mapping, FRKC knowledge corpus integration.
- **Formula patterns** — formula catalog with mathematical foundations, implementation guides, and architecture alignment.
- **Project patterns** — AI-native operating model, session resilience, bootstrap handoff.

These patterns are reusable beyond FRKP. The FAEP architecture formalizes them into a platform model that can bootstrap new projects (e.g., IB Project), integrate external risk engines (e.g., Risk Project), and extract a reusable governance framework (KPGF).

---

# 3. FAEP Definition

**FAEP (Financial AI Engineering Platform)** is the umbrella architecture for building AI-augmented, evidence-driven, governance-controlled financial knowledge and engineering platforms.

FAEP is:

- **An architectural framework** — defining engines, boundaries, integration points, and data flows.
- **A governance container** — providing reusable standards, templates, and processes.
- **An integration blueprint** — specifying how knowledge, computation, analytics, evidence, and AI agents connect.
- **A bootstrap mechanism** — enabling rapid creation of new FAEP-conformant projects.

FAEP is NOT:

- A product or software application.
- A single repository or codebase.
- A vendor-specific platform.
- A replacement for FRKP, Risk Project, or IB Project.

---

# 4. Platform Vision

FAEP envisions a future where:

1. **Knowledge is platform-native** — all financial knowledge lives in structured, evidence-driven, cross-referenced repositories.
2. **Formulas are computable** — formula catalogs are directly executable by runtime engines.
3. **Risk analytics are traceable** — every risk number is traceable to its formula, knowledge, and regulatory evidence.
4. **Governance is automated** — standards, reviews, certifications, and freezes are AI-assisted or AI-executed.
5. **Projects are bootstrappable** — new FAEP-conformant projects can be created from reusable templates and patterns.
6. **AI agents orchestrate** — AI agents handle routine orchestration, validation, and publishing tasks under human governance.

---

# 5. Scope and Non-Scope

## In Scope

- FAEP engine definitions and boundaries.
- Integration model among engines.
- Data and knowledge flow architecture.
- Formula-to-knowledge traceability.
- Evidence-to-governance traceability.
- AI Agent usage model.
- Plugin/bootstrap model.
- Repository strategy and migration roadmap.
- Relationship definitions: FAEP / FRKP / Risk Project / IB Project / KPGF.

## Non-Scope

- Implementation of any engine.
- FRKP bundle content.
- Risk Project software architecture.
- IB Project business requirements.
- Specific technology choices (programming languages, frameworks, tools).
- Deployment architecture (cloud, on-premise, container).
- Security architecture.
- Performance requirements.

---

# 6. Architecture Principles

All FAEP engines and projects follow these principles:

| # | Principle | Description |
| --- | --- | --- |
| 1 | **Single Responsibility** | Each engine has exactly one primary responsibility. |
| 2 | **Layered Architecture** | Engines are organized in layers; dependencies flow downward. |
| 3 | **Separation of Concerns** | Knowledge, computation, governance, and presentation are separate engines. |
| 4 | **Loose Coupling** | Engines communicate through defined integration points, not direct dependencies. |
| 5 | **Evidence-Driven** | Every publication is traceable to authoritative evidence. |
| 6 | **Deterministic Processing** | Given the same inputs, engines produce the same outputs. |
| 7 | **Governance-Controlled** | All engines operate within defined governance rules. |
| 8 | **AI-Augmented** | AI agents assist but do not replace human governance authority. |
| 9 | **Bootstrappable** | New projects can be created from reusable platform patterns. |
| 10 | **Extensible** | New engines, domains, and integration points can be added without breaking existing ones. |

---

# 7. Platform Layers

FAEP defines nine engines organized in three layers:

```
┌──────────────────────────────────────────────────────────────┐
│                    ORCHESTRATION LAYER                        │
│  ┌─────────────┐  ┌─────────────┐  ┌───────────────────┐    │
│  │  AI Agent   │  │ Governance  │  │ Project Bootstrap │    │
│  │   Engine    │  │   Engine    │  │      Engine       │    │
│  └─────────────┘  └─────────────┘  └───────────────────┘    │
├──────────────────────────────────────────────────────────────┤
│                     DOMAIN LAYER                              │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐          │
│  │ Knowledge   │  │  Formula    │  │ Risk        │          │
│  │   Engine    │  │   Engine    │  │  Analytics  │          │
│  │             │  │             │  │   Engine    │          │
│  └─────────────┘  └─────────────┘  └─────────────┘          │
│  ┌─────────────┐  ┌─────────────┐                            │
│  │ Evidence    │  │  Runtime    │                            │
│  │   Engine    │  │   Engine    │                            │
│  └─────────────┘  └─────────────┘                            │
├──────────────────────────────────────────────────────────────┤
│                   PRESENTATION LAYER                          │
│  ┌───────────────────────────────────────────────────┐       │
│  │              Document Publishing Engine            │       │
│  └───────────────────────────────────────────────────┘       │
└──────────────────────────────────────────────────────────────┘
```

## 7.1 Knowledge Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | KE-001 |
| **Primary Responsibility** | Manage structured knowledge documents |
| **Owner** | FRKP (reference implementation) |
| **Inputs** | Evidence sources, regulatory texts, domain expertise |
| **Outputs** | Reference Library, Knowledge Base, Analysis documents |
| **Key Functions** | Document creation, cross-referencing, versioning, knowledge retrieval |
| **Integration Points** | Formula Engine (feeds formula knowledge), Evidence Engine (receives evidence), Document Publishing Engine (sends for publication) |
| **Repository** | FRKP (layers: RL, KB, AN) |
| **Standards** | FRKP-DOC-001, FRKP-ID-001, FRKP-TERM-001 |

## 7.2 Formula Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | FE-001 |
| **Primary Responsibility** | Manage mathematical formulas and computations |
| **Owner** | Risk Project (reference implementation) |
| **Inputs** | Knowledge from Knowledge Engine, regulatory formula definitions |
| **Outputs** | Formula Catalog, Mathematical Foundation documents, executable formulas |
| **Key Functions** | Formula definition, symbol standardization, mathematical derivation, formula computation |
| **Integration Points** | Knowledge Engine (receives domain knowledge), Risk Analytics Engine (provides formulas for computation), Runtime Engine (provides executable formulas) |
| **Repository** | FRKP (FC, MF layers); Risk Project (executable formulas) |
| **Standards** | FRKP-FORM-001, FRKP-SYM-001 |

## 7.3 Risk Analytics Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | RAE-001 |
| **Primary Responsibility** | Execute risk calculations and produce analytics |
| **Owner** | Risk Project (reference implementation) |
| **Inputs** | Formulas from Formula Engine, market data, portfolio data, scenario parameters |
| **Outputs** | Risk measures, analytics reports, scenario results |
| **Key Functions** | Risk calculation, aggregation, scenario generation, stress testing, reporting |
| **Integration Points** | Formula Engine (receives formulas), Runtime Engine (executes on runtime), Knowledge Engine (documents analytics methodology) |
| **Repository** | Risk Project (future) |
| **Standards** | FAEP integration standards |

## 7.4 Runtime Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | RE-001 |
| **Primary Responsibility** | Provide execution environment for formulas and analytics |
| **Owner** | Risk Project (reference implementation) |
| **Inputs** | Executable formulas, calculation requests, data inputs |
| **Outputs** | Calculation results, execution logs |
| **Key Functions** | Batch processing, real-time calculation, data pipelining, execution management |
| **Integration Points** | Formula Engine (receives executable formulas), Risk Analytics Engine (provides execution) |
| **Repository** | Risk Project (future) |
| **Standards** | FAEP integration standards |

## 7.5 Evidence Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | EE-001 |
| **Primary Responsibility** | Manage evidence traceability from source to publication |
| **Owner** | FRKP (reference implementation) |
| **Inputs** | Evidence sources (regulatory texts, research papers, project documents) |
| **Outputs** | Evidence IDs, evidence-to-publication mappings, evidence registers |
| **Key Functions** | Evidence identification, evidence mapping, traceability tracking, evidence certification |
| **Integration Points** | Knowledge Engine (provides evidence for documents), Governance Engine (provides evidence for compliance) |
| **Repository** | FRKC (knowledge corpus); FRKP (mappings) |
| **Standards** | FRKP-FRKC-001 |

## 7.6 Governance Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | GE-001 |
| **Primary Responsibility** | Define and enforce platform governance rules |
| **Owner** | KPGF (reference implementation); FRKP (initial instantiation) |
| **Inputs** | Platform policies, standards, templates, review results |
| **Outputs** | Governance documents, certificates, standards, templates |
| **Key Functions** | Standard definition, document lifecycle management, certification, compliance checking, review management |
| **Integration Points** | All engines (provides governance rules); Evidence Engine (receives compliance evidence); AI Agent Engine (delegates routine governance tasks) |
| **Repository** | FRKP (Governance/); KPGF (future extract) |
| **Standards** | FRKP-ARCH-001, FRKP-BUNDLE-001, FRKP-DOC-001, FRKP-ID-001 |

## 7.7 AI Agent Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | AAE-001 |
| **Primary Responsibility** | Orchestrate and automate platform tasks through AI |
| **Owner** | FAEP (future) |
| **Inputs** | Task requests, platform state, engine outputs |
| **Outputs** | Task execution, validation results, status reports |
| **Key Functions** | Task orchestration, document validation, cross-reference checking, state monitoring, session handoff, engine coordination |
| **Integration Points** | All engines (orchestration and automation layer) |
| **Repository** | FAEP (future) |
| **Standards** | FRKP-002 AI Operating Model patterns |

## 7.8 Project Bootstrap Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | PBE-001 |
| **Primary Responsibility** | Enable rapid creation of new FAEP-conformant projects |
| **Owner** | FAEP (future) |
| **Inputs** | Project requirements, domain scope, engine selections |
| **Outputs** | Bootstrapped project repository, initial documents, governance setup |
| **Key Functions** | Template application, repository scaffolding, governance initialization, engine wiring |
| **Integration Points** | Governance Engine (provides templates/standards); Knowledge Engine (provides seed knowledge); AI Agent Engine (automates bootstrap) |
| **Repository** | FAEP (future); FRKP (Templates/) |
| **Standards** | FRKP-TPL-001, FRKP-000 bootstrap patterns |

## 7.9 Document Publishing Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | DPE-001 |
| **Primary Responsibility** | Publish, navigate, and present platform documents |
| **Owner** | FRKP (reference implementation) |
| **Inputs** | Knowledge documents, evidence mappings, governance metadata |
| **Outputs** | Published documents, navigation structures, indexes, cross-references |
| **Key Functions** | Document formatting, navigation generation, index creation, cross-reference validation, link integrity |
| **Integration Points** | Knowledge Engine (receives documents for publishing); Evidence Engine (embeds evidence traceability); Governance Engine (applies publishing standards) |
| **Repository** | FRKP (all layers) |
| **Standards** | FRKP-DOC-001, FRKP-NAV conventions |

---

# 8. Relationship Between FAEP, FRKP, Risk Project, IB Project, and KPGF

## Relationship Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                         FAEP (Platform)                              │
│                                                                     │
│  ┌──────────────────────────────────────────────────────────┐      │
│  │              FAEP Core Architecture                        │      │
│  │  - Engine definitions         - Integration model          │      │
│  │  - Platform principles        - Data flow model            │      │
│  │  - Plugin/bootstrap specs     - AI Agent model             │      │
│  └──────────────────────────────────────────────────────────┘      │
│                                                                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐              │
│  │    FRKP      │  │ Risk Project │  │  IB Project  │              │
│  │ (Reference)  │  │   (Future)   │  │   (Future)   │              │
│  │              │  │              │  │              │              │
│  │ Knowledge    │  │ Formula      │  │ Business     │              │
│  │ Engine       │  │ Engine       │  │ Knowledge    │              │
│  │ Evidence     │  │ Risk         │  │ Workflow     │              │
│  │ Engine       │  │ Analytics    │  │ Integration  │              │
│  │ Document     │  │ Engine       │  │              │              │
│  │ Publishing   │  │ Runtime      │  │              │              │
│  │ Engine       │  │ Engine       │  │              │              │
│  └──────────────┘  └──────────────┘  └──────────────┘              │
│                                                                     │
│  ┌──────────────────────────────────────────────────────────┐      │
│  │  KPGF (Reusable Governance Framework)                     │      │
│  │  - Standards (document ID, architecture, bundle, etc.)    │      │
│  │  - Templates (documents, reviews, certificates)           │      │
│  │  - Processes (evidence-driven publishing, AI operating)   │      │
│  └──────────────────────────────────────────────────────────┘      │
└─────────────────────────────────────────────────────────────────────┘
```

## Relationship Summary

| Entity | Role in FAEP | Current State | Future State |
| --- | --- | --- | --- |
| **FAEP** | Platform umbrella architecture | Defined (this document) | Platform governing all engines |
| **FRKP** | First reference implementation | Active repository | Continues as Knowledge/Document reference |
| **Risk Project** | Formula, Risk Analytics, Runtime Engine | Not yet created | Integrated via defined interfaces |
| **IB Project** | First downstream business project | Not yet created | Bootstrapped from FAEP patterns |
| **KPGF** | Reusable governance framework | Extract from FRKP governance | Independent framework repository |

---

# 9. Component Responsibility Matrix

| Engine | FRKP | Risk Project | IB Project | KPGF | FAEP Core |
| --- | :---: | :---: | :---: | :---: | :---: |
| Knowledge Engine | **Primary** | Consumes | Consumes | Standards | Defines |
| Formula Engine | Defines/Stores | **Computes** | Consumes | Standards | Defines |
| Risk Analytics Engine | Documents (ARCH) | **Executes** | Consumes | Standards | Defines |
| Runtime Engine | Documents (IMP) | **Operates** | Consumes | Standards | Defines |
| Evidence Engine | **Primary** | Contributes | Consumes | Standards | Defines |
| Governance Engine | Instantiates | Conforms | Conforms | **Framework** | Defines |
| AI Agent Engine | Uses patterns | Uses patterns | Uses patterns | Patterns | **Defines** |
| Project Bootstrap | Templates | Uses | Uses | Templates | **Specifies** |
| Document Publishing | **Primary** | Publishes | Publishes | Standards | Defines |

**Legend:** **Bold** = primary responsibility; *Italic* = secondary responsibility.

---

# 10. Integration Model

## Integration Point Summary

| Integration Point | Source Engine | Target Engine | Interface Type | Data |
| --- | --- | --- | --- | --- |
| IP-001 | Knowledge Engine | Formula Engine | Knowledge Query | Domain knowledge, term definitions |
| IP-002 | Knowledge Engine | Evidence Engine | Evidence Reference | Document-to-evidence mappings |
| IP-003 | Knowledge Engine | Document Publishing | Publication Request | Finalized documents |
| IP-004 | Formula Engine | Risk Analytics Engine | Formula Contract | Executable formulas, parameters |
| IP-005 | Formula Engine | Knowledge Engine | Formula Documentation | Formula definitions, symbols |
| IP-006 | Risk Analytics Engine | Runtime Engine | Execution Request | Calculation tasks, data |
| IP-007 | Runtime Engine | Risk Analytics Engine | Execution Result | Calculation outputs |
| IP-008 | Evidence Engine | Governance Engine | Compliance Evidence | Evidence IDs, certification data |
| IP-009 | Evidence Engine | Knowledge Engine | Evidence Feed | Evidence IDs, mappings |
| IP-010 | Governance Engine | All Engines | Governance Rules | Standards, policies, templates |
| IP-011 | AI Agent Engine | All Engines | Orchestration Commands | Task assignments, status queries |
| IP-012 | Project Bootstrap Engine | Governance Engine | Template Request | Project scaffold, governance init |

## Integration Rules

1. All integration points are unidirectional or request-response, not bidirectional streaming.
2. Integration interfaces are defined by contract (data schema, not implementation).
3. An engine may implement multiple interfaces but must not expose internal state directly.
4. Governance Engine integration (IP-010) is read-only from the consumer perspective — engines do not modify governance rules.
5. AI Agent Engine integration (IP-011) is the only cross-cutting orchestration interface.

---

# 11. Data and Knowledge Flow

## End-to-End Knowledge Flow

```
Regulatory Text / Research / Domain Expertise
        │
        ▼
┌────────────────┐
│ Evidence Engine │──→ Evidence IDs, Evidence Register
└────────────────┘
        │
        ▼
┌──────────────────┐
│ Knowledge Engine  │──→ RL → KB → AN documents
└──────────────────┘
        │                          │
        ▼                          ▼
┌──────────────┐         ┌────────────────┐
│Formula Engine │         │Document        │
│(documentation)│         │Publishing Engine│
└──────────────┘         └────────────────┘
        │                          │
        ▼                          ▼
┌──────────────┐         ┌────────────────┐
│Formula Engine │         │ Published      │
│(executable)   │         │ Documents      │
└──────────────┘
        │
        ▼
┌──────────────────┐
│ Runtime Engine    │──→ Calculation Results
└──────────────────┘
        │
        ▼
┌──────────────────┐
│Risk Analytics    │──→ Risk Measures, Reports
│Engine            │
└──────────────────┘
```

## Governance Flow

```
Governance Engine
        │
        ├── Standards → Knowledge Engine (document structure)
        ├── Standards → Formula Engine (formula format)
        ├── Templates → Document Publishing Engine (output format)
        ├── Policies  → AI Agent Engine (automation rules)
        └── Rules     → All Engines (compliance)
                │
                ▼
        Evidence Engine (compliance proof)
                │
                ▼
        Governance Engine (certification)
```

## AI Agent Flow

```
Human Task Request
        │
        ▼
┌──────────────┐
│ AI Agent     │──→ Task decomposition
│ Engine       │──→ Engine coordination
│              │──→ Validation
│              │──→ Status reporting
└──────────────┘
        │
        ├── Knowledge Engine → "Check cross-references"
        ├── Evidence Engine → "Verify evidence mapping"
        ├── Governance Engine → "Validate compliance"
        ├── Document Publishing → "Rebuild navigation"
        └── Human → "Review and approve"
```

---

# 12. Formula-to-Knowledge Traceability Model

Every formula in the Formula Engine must be traceable to its knowledge source in the Knowledge Engine.

## Traceability Chain

```
Regulatory Text (Evidence)
    │
    ▼
RL (Reference Library) — cites evidence
    │
    ▼
KB (Knowledge Base) — explains concept
    │
    ▼
AN (Analysis) — analyzes application
    │
    ▼
FC (Formula Catalog) — defines formula
    │
    ▼
MF (Mathematical Foundation) — proves derivation
    │
    ▼
IMP (Implementation Guide) — implements formula
    │
    ▼
ARCH (Architecture Guide) — places in system
    │
    ▼
Executable Formula (Runtime Engine) — computes
```

## Traceability Rules

| Rule | Description |
| --- | --- |
| TR-001 | Every FC document must reference at least one KB document. |
| TR-002 | Every FC document must reference the regulatory evidence (RL or external). |
| TR-003 | Every executable formula must reference its FC document. |
| TR-004 | Formula parameters must reference symbols defined in FRKP-SYM standards. |
| TR-005 | Formula computation results must be traceable to the formula definition. |

---

# 13. Evidence-to-Governance Traceability Model

Every governance decision (review, freeze, release) must be traceable to supporting evidence.

## Traceability Chain

```
Evidence Source (regulatory text, research)
    │
    ▼
Evidence ID assignment (Evidence Engine)
    │
    ▼
Publication mapping (Evidence Engine → Knowledge Engine)
    │
    ▼
Bundle Review (Governance Engine)
    │
    ▼
Freeze Certification (Governance Engine)
    │
    ▼
Release (Governance Engine)
```

## Traceability Rules

| Rule | Description |
| --- | --- |
| GR-001 | Every bundle review must reference evidence IDs for each claim. |
| GR-002 | Every freeze certificate must reference the evidence baseline. |
| GR-003 | Every human review item must reference evidence or deferred item. |
| GR-004 | Every release must reference freeze certificates of all included bundles. |
| GR-005 | Governance engine must not certify without evidence engine verification. |

---

# 14. AI Agent Usage Model

## Agent Capabilities

| Capability | Description | Automation Level |
| --- | --- | --- |
| Document Validation | Check document IDs, cross-references, navigation links | Full automation |
| Cross-Reference Checking | Verify all cross-references resolve to existing documents | Full automation |
| Evidence Mapping | Map evidence IDs to publication documents | Full automation |
| Navigation Generation | Generate and update navigation structures | Full automation |
| State Monitoring | Track repository state, working tree changes | Full automation |
| Plan Execution | Execute defined plans within scope boundaries | Supervised |
| Template Application | Apply document templates to new content | Supervised |
| Quality Review | Check standards compliance, consistency | Supervised |
| Editorial Review | Review for logical consistency, educational clarity | Human required |
| Domain Reasoning | Interpret regulatory text, make domain judgments | Human required |
| Governance Decisions | Approve plans, freeze, release | Human required |

## Agent Integration Model

```
Human Governance Authority
        │
        ▼
┌──────────────────────────────┐
│     AI Agent Engine          │
│                              │
│  ┌────────────────────┐      │
│  │ Orchestrator       │      │
│  │ - Task decomposition│      │
│  │ - Engine routing   │      │
│  │ - State tracking   │      │
│  │ - Result reporting │      │
│  └────────────────────┘      │
│                              │
│  ┌────────────────────┐      │
│  │ Validator          │      │
│  │ - Document checks  │      │
│  │ - Link integrity   │      │
│  │ - Standards check  │      │
│  └────────────────────┘      │
│                              │
│  ┌────────────────────┐      │
│  │ Knowledge Worker   │      │
│  │ - Content creation │      │
│  │ - Cross-referencing│      │
│  │ - Template fill    │      │
│  └────────────────────┘      │
│                              │
│  ┌────────────────────┐      │
│  │ Reporter           │      │
│  │ - State summary    │      │
│  │ - Change log       │      │
│  │ - Status dashboard │      │
│  └────────────────────┘      │
└──────────────────────────────┘
        │
        ├── Knowledge Engine
        ├── Formula Engine
        ├── Evidence Engine
        ├── Governance Engine
        ├── Document Publishing Engine
        └── Human Reviewer
```

---

# 15. Plugin/Bootstrap Model

## Plugin Types

| Plugin Type | Description | Source |
| --- | --- | --- |
| Domain Plugin | Pre-built knowledge structure for a domain (e.g., Operational Risk) | FRKP bundle patterns |
| Engine Plugin | Pre-configured engine wiring for a specific runtime | FAEP templates |
| Governance Plugin | Pre-defined governance rules and standards for a project type | KPGF |
| Template Plugin | Document templates, review templates, certificate templates | FRKP templates |
| Integration Plugin | Pre-defined integration contracts between engines | FAEP core |

## Bootstrap Process

```
1. Define project scope and domain
        │
        ▼
2. Select relevant plugins (domain, governance, templates)
        │
        ▼
3. Project Bootstrap Engine creates repository scaffold
        │
        ▼
4. Governance Engine initializes standards and templates
        │
        ▼
5. Knowledge Engine seeds domain knowledge from reference
        │
        ▼
6. Integration points configured between selected engines
        │
        ▼
7. AI Agent Engine initialized with project context
        │
        ▼
8. Human review and project launch
```

## Bootstrap Artefacts

| Artefact | Description | Plugin Source |
| --- | --- | --- |
| Repository structure | Folder layout, README, .gitignore | Project Bootstrap Engine |
| Governance documents | FRKP-000 style bootstrap, project charter | KPGF Governance Plugin |
| Standards | Document ID, architecture, bundle standards | KPGF Governance Plugin |
| Templates | Document templates, review templates | KPGF Template Plugin |
| Seed knowledge | RL, KB, AN documents for the domain | Domain Plugin |
| Integration config | Engine wiring, interface definitions | Integration Plugin |
| AI Agent config | Session restoration order, handoff templates | AI Agent Plugin |

---

# 16. Repository Strategy Options

## Option A: Keep Within FRKP Temporarily (Current)

**Description:** All FAEP architecture definitions remain in the FRKP repository under `00_Project_Management/Governance/` and `00_Project_Management/Plans/`.

**Advantages:**
- Zero disruption to current workflow.
- Leverages existing FRKP governance and conventions.
- No repository management overhead.
- FAEP architecture evolves alongside FRKP reference implementation.

**Disadvantages:**
- FAEP scope diluted within FRKP repository.
- FRKP-003 naming is under FRKP namespace.
- Potential confusion between FRKP project and FAEP platform.

**Timeline:** Phase 1 (immediate).

## Option B: Later Split Into FAEP Repository

**Description:** Create a dedicated FAEP GitHub repository (`github.com/kbgkim/faep` or similar) that houses platform architecture, engine specifications, KPGF, and plugin templates.

**Advantages:**
- Clear separation between platform and reference implementation.
- FAEP has its own namespace, conventions, and governance.
- Non-FRKP projects (IB Project, Risk Project) reference FAEP, not FRKP.
- Easier for external contributors to adopt platform patterns.

**Disadvantages:**
- Repository management overhead.
- Must maintain synchronization between FAEP and FRKP.
- Breaking change from current structure.
- Requires migration plan and cross-repository tooling.

**Timeline:** Phase 4 (after KPGF extraction).

## Option C: FRKP as Permanent Reference Implementation

**Description:** FRKP remains the sole repository. FAEP architecture is defined in FRKP governance documents. All new projects (IB, Risk) create their own repositories but reference FRKP's governance documents as authoritative.

**Advantages:**
- Single source of truth.
- No split overhead.
- FRKP governance naturally evolves into platform governance.

**Disadvantages:**
- FRKP identity as a risk knowledge platform conflicts with FAEP platform scope.
- Non-risk projects may not want to reference FRKP.
- FRKP naming and conventions may not fit non-risk domains.

**Timeline:** Ongoing — decision deferred to Phase 4.

---

# 17. Migration Roadmap

## Phase 1: Define Inside FRKP (Current)

| Step | Description | Status |
| --- | --- | --- |
| 1.1 | Define FAEP Master Architecture (this document) | ✅ Complete (PLAN-011) |
| 1.2 | Document FAEP architecture decisions | ✅ Complete |
| 1.3 | Define engine boundaries and integration points | ✅ Complete |
| 1.4 | Align with existing FRKP governance | ✅ Complete |

**Duration:** Immediate.

## Phase 2: Apply to IB Project (Next)

| Step | Description | Target |
| --- | --- | --- |
| 2.1 | Define IB Project bootstrap using FAEP patterns | Next PLAN |
| 2.2 | Create IB Project repository scaffold | Next PLAN |
| 2.3 | Apply KPGF governance templates to IB Project | Next PLAN |
| 2.4 | Validate bootstrap process | After Phase 2 execution |

**Trigger:** PLAN-011 completion.

## Phase 3: Integrate Risk Project

| Step | Description | Target |
| --- | --- | --- |
| 3.1 | Define Risk Project architecture in FAEP terms | Future |
| 3.2 | Define integration contracts between FRKP and Risk Project | Future |
| 3.3 | Implement Runtime Engine integration | Future |
| 3.4 | Implement Formula Engine integration | Future |

**Trigger:** Risk Project initiation.

## Phase 4: Extract KPGF/FAEP Core

| Step | Description | Target |
| --- | --- | --- |
| 4.1 | Extract KPGF governance framework from FRKP | Future |
| 4.2 | Create FAEP core repository | Future |
| 4.3 | Renumber FAEP documents to FAEP namespace | Future |
| 4.4 | Migrate FRKP to pure reference implementation | Future |
| 4.5 | Establish cross-repository governance synchronization | Future |

**Trigger:** 2+ FAEP-conformant projects exist.

---

# 18. Risks and Constraints

## Risks

| Risk ID | Description | Probability | Impact | Mitigation |
| --- | --- | --- | --- | --- |
| RISK-001 | Architecture becomes too abstract for practical use | Medium | Medium | Grounded in FRKP reference implementation |
| RISK-002 | Nine-engine model over-engineers simple projects | Medium | Low | Engines are logical; can merge in implementation |
| RISK-003 | Repository split creates synchronization burden | Low | Medium | Deferred until Phase 4 when need is clear |
| RISK-004 | IB Project may not fit FAEP bootstrap model | Medium | Medium | Bootstrap model designed for customization |
| RISK-005 | AI Agent model may not match available AI tools | Low | Medium | Defined abstractly; technology-agnostic |
| RISK-006 | Document ID conflicts between FAEP and FRKP | Low | Low | FRKP-003 used; renumbering deferred |

## Constraints

| Constraint ID | Description |
| --- | --- |
| CON-001 | FRKP freeze certificates must not be modified. |
| CON-002 | FRKP document IDs must not be renamed. |
| CON-003 | Bundle-007 content is frozen and must not be modified. |
| CON-004 | Version 1.0.0 frozen artifacts must not be modified. |
| CON-005 | FAEP architecture must not create Git tags, releases, or commits. |
| CON-006 | FAEP architecture must not resolve Version 1.1 release blockers. |

---

# 19. Open Decisions

| Decision ID | Question | Options | Recommendation | Decision Date |
| --- | --- | --- | --- | --- |
| OPD-001 | Should FAEP have a dedicated repository? | Yes / No / Deferred | Deferred to Phase 4 | TBD |
| OPD-002 | Should FAEP define formal interface contracts (OpenAPI, gRPC)? | Yes / No / Text-based | Text-based initially; formal in Phase 3 | TBD |
| OPD-003 | Should AI Agent Engine use specific AI tools or remain abstract? | Abstract / Specific | Abstract until Phase 4 | TBD |
| OPD-004 | Should KPGF be extracted before or after IB Project bootstrap? | Before / After | After — validate with IB Project first | TBD |
| OPD-005 | Should FRKP governance documents be renumbered to FAEP namespace? | Yes / No / Deferred | Deferred to Phase 4 | TBD |
| OPD-006 | What is the relationship between FRKP bundles and FAEP domain plugins? | Bundles = Plugins / Separate | Bundles are the reference; plugins are generalized patterns | TBD |

---

# 20. Recommended Next PLANs

## Immediate (Phase 2: IB Project Bootstrap)

| Priority | Plan ID | Title | Description |
| --- | --- | --- | --- |
| P1 | PLAN-012 | IB Project Bootstrap Definition | Define the first downstream business project bootstrapped from FAEP patterns. Create IB project architecture document. |
| P2 | PLAN-013 | IB Project Domain Knowledge Structure | Define the knowledge engine structure for IB Project (RL, KB, AN layers). |
| P3 | PLAN-014 | IB Project Governance Initialization | Initialize governance standards and templates for IB Project. |

## Future

| Priority | Plan ID | Title | Description | Phase |
| --- | --- | --- | --- | --- |
| P4 | PLAN-015 | FAEP Plugin/Bootstrap Template Implementation | Implement reusable plugin and bootstrap templates based on FRKP patterns. | Phase 2 |
| P5 | PLAN-016 | FAEP Integration Contract Specification | Define formal integration contracts between engines. | Phase 3 |
| P6 | PLAN-017 | Risk Project Architecture Definition | Define Risk Project architecture within FAEP framework. | Phase 3 |
| P7 | PLAN-018 | KPGF Extraction from FRKP | Extract reusable governance framework into KPGF. | Phase 4 |
| P8 | PLAN-019 | FAEP Core Repository Creation | Create dedicated FAEP repository and migrate core artifacts. | Phase 4 |
| P9 | PLAN-020 | AI Agent Engine Specification | Define formal AI Agent Engine interface and capabilities. | Phase 4 |

---

## Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Master Architecture Definition (PLAN-011) |
