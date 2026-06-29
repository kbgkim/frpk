# FRKP-004 — FAEP Core Platform Specification

---

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-004 |
| Document Name | FAEP Core Platform Specification |
| Version | 1.0.0 |
| Status | Active |
| Plan | PLAN-012 |
| Owner | FAEP Governance |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Purpose | Define FAEP Core as the platform specification that all future Financial AI projects shall conform to. FRKP is the first Reference Implementation. |

---

# 1. Purpose

This document defines **FAEP Core** as the platform specification that governs every future Financial AI project.

FAEP Core is the **platform contract**.

It is not an application.

It is not FRKP.

It is not the Risk Project.

It is the architectural and governance foundation upon which all FAEP-conformant projects are built.

This specification defines:

- **What** a FAEP-conformant project must satisfy.
- **How** platform components are structured and governed.
- **What contracts** govern inter-engine communication.
- **What lifecycle** governs knowledge, evidence, formulas, documents, releases, and agents.
- **How** plugins extend the platform.
- **How** new projects are bootstrapped into FAEP compliance.

**FRKP** is the first Reference Implementation and demonstrates every contract defined herein.

**Risk Project** is the first Computational Engine.

**IB Project** is the first Business Platform built on FAEP.

---

# 2. Vision

FAEP Core envisions a future where:

1. **Every Financial AI project shares a common architectural foundation.** No project starts from zero. Every project inherits FAEP Core contracts, governance, and patterns.

2. **Knowledge, evidence, formulas, and risk analytics are universally traceable.** Any claim can be traced to its evidence. Any formula can be traced to its knowledge source. Any risk number can be traced to its computation origin. Any release can be traced to its governance decisions.

3. **Governance is automated and AI-assisted.** Standards compliance is checked by AI agents. Freeze certification is evidence-driven. Release decisions are supported by automated readiness assessments. Human authority remains for final governance decisions.

4. **Engines are pluggable and replaceable.** The Knowledge Engine, Formula Engine, Risk Analytics Engine, and all others conform to defined contracts. An engine can be replaced without changing the Core. New engines can be added without breaking existing ones.

5. **AI agents are first-class platform citizens.** AI agents are not external tools. They are platform engines with defined contracts, boundaries, and governance rules. They orchestrate, validate, monitor, and assist across the entire platform.

6. **Projects are bootstrappable in hours, not weeks.** A new FAEP-conformant project can be created from reusable templates, governance stubs, and engine wiring patterns. The Bootstrap Engine automates scaffolding while preserving architectural integrity.

7. **The platform outlives any single project.** FAEP Core is independent of FRKP, Risk Project, and IB Project. It is the enduring contract. Projects come and go. The platform remains.

---

# 3. FAEP Philosophy

FAEP is guided by five foundational philosophies plus two cross-cutting philosophies.

## 3.1 Knowledge First

Knowledge is the primary asset. Every platform artifact — evidence, formula, document, release, agent — exists to serve knowledge.

- Knowledge precedes publication.
- Knowledge is structured, cross-referenced, and versioned.
- Knowledge is the single source of truth for all derived artifacts.
- Knowledge is stored in authoritative knowledge corpora (e.g., FRKC).

## 3.2 Evidence First

Every platform claim must be traceable to authoritative evidence.

- Evidence precedes knowledge.
- No publication without evidence mapping.
- Evidence is identified, registered, and certified.
- Evidence-to-publication traceability is automated and auditable.

## 3.3 Architecture First

Architecture precedes implementation. Every platform component is defined by contract before it is built.

- Contracts are defined before engines.
- Interfaces are defined before integration.
- Standards are defined before content creation.
- Governance is defined before execution.

## 3.4 Governance First

Governance is not an afterthought. It is a first-class platform concern embedded in every lifecycle.

- Every artifact has a defined lifecycle with governance gates.
- Every lifecycle gate requires evidence.
- Every governance decision is documented and traceable.
- Human authority is reserved for decisions that AI cannot make.

## 3.5 AI Native

AI is not an add-on. It is a native platform capability.

- AI agents are platform engines with defined contracts.
- AI agents assist, validate, orchestrate, and report.
- AI agents do not replace human governance authority.
- AI agents are governed by the same lifecycle and traceability rules as all other platform components.

## 3.6 Reusable by Design

Every pattern, template, contract, and standard is designed for reuse.

- FRKP patterns are extracted into FAEP Core.
- FAEP Core patterns are available to all projects.
- New projects inherit platform patterns rather than inventing new ones.
- Reuse reduces duplication, inconsistency, and maintenance burden.

---

# 4. Platform Principles

FAEP Core is governed by the following principles. Every FAEP-conformant project must satisfy all mandatory principles. Recommended principles should be satisfied where practicable.

## Mandatory Principles

| # | Principle | Description | Category |
| --- | --- | --- | --- |
| 1 | **Single Source of Truth** | Every piece of knowledge, evidence, formula, and governance rule exists in exactly one authoritative location. Derived artifacts reference the source rather than duplicating it. | Knowledge |
| 2 | **Everything Traceable** | Every claim, decision, formula, and release is traceable to its origin through a documented chain. Traceability is automated and auditable. | Traceability |
| 3 | **Everything Versioned** | Every platform artifact is versioned using semantic versioning. Version changes are documented in revision histories. Breaking changes require major version increments. | Versioning |
| 4 | **Evidence Driven** | No knowledge is published without supporting evidence. Evidence is identified, mapped, and certified before publication proceeds. | Evidence |
| 5 | **Contract Before Implementation** | Every engine, plugin, and integration point is defined by contract before implementation begins. Contracts specify inputs, outputs, boundaries, and error conditions. | Architecture |
| 6 | **Reference Implementation Pattern** | Every FAEP Core contract is accompanied by at least one reference implementation. FRKP serves as the primary reference implementation for all Core contracts. | Architecture |
| 7 | **Plugin Architecture** | All engines are plugins that conform to Core contracts. Engines can be added, removed, or replaced without modifying the Core. | Architecture |
| 8 | **Domain Isolation** | Each domain (Knowledge, Formula, Risk, Evidence, Governance) is isolated from others. Domains communicate only through defined integration points. No domain directly accesses another domain's internal state. | Architecture |
| 9 | **Human + AI Collaboration** | AI agents assist but do not replace human governance. Humans retain authority over acceptance, freeze, release, and strategic decisions. AI agents execute, validate, and report within human-defined boundaries. | Governance |
| 10 | **Immutable Freeze** | Frozen artifacts must not be modified. Changes to frozen artifacts require a new version and a new freeze. Freeze certificates record the evidence baseline and deferred items. | Governance |
| 11 | **AI Agent Ready** | Every platform artifact must be processable by AI agents. Documents use consistent structure. Metadata is machine-readable. Cross-references are resolvable. Standards are checkable by automated validators. | AI |

## Recommended Principles

| # | Principle | Description | Category |
| --- | --- | --- | --- |
| 12 | **Knowledge as Code** | Knowledge artifacts are treated with the same rigor as code: versioned, reviewed, tested, and deployed through defined pipelines. | Knowledge |
| 13 | **Deterministic Processing** | Given the same inputs and contracts, all engine implementations produce the same outputs. Determinism enables testing, validation, and cross-engine verification. | Engineering |
| 14 | **Fail Closed** | When a governance check cannot be completed, the default decision is to fail closed (deny). Human override is required to proceed. | Governance |
| 15 | **Progressive Formalization** | Contracts may start as text-based specifications and progressively formalize to machine-readable schemas (JSON Schema, OpenAPI, gRPC) as the platform matures. | Architecture |
| 16 | **Backward Compatibility** | New versions of any contract must be backward compatible with previous versions unless a breaking change is explicitly documented and approved through governance. | Versioning |
| 17 | **Minimum Viable Governance** | Governance rules must be proportional to the artifact's criticality. A bundle review requires more governance than a typo fix. Governance overhead must not exceed governance value. | Governance |
| 18 | **Self-Documenting** | Platform contracts, engine boundaries, and integration points are documented as close to the specification as possible. External documentation references the specification rather than duplicating it. | Architecture |

---

# 5. Core Platform Components

FAEP Core defines sixteen platform engines. Each engine has a single primary responsibility.

## 5.1 Knowledge Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | KE-001 |
| **Primary Responsibility** | Manage structured knowledge documents across all domains |
| **Core Contract** | CC-KE-001 |
| **Reference Implementation** | FRKP (RL, KB, AN layers) |
| **Inputs** | Evidence sources, regulatory texts, domain expertise |
| **Outputs** | Reference Library, Knowledge Base, Analysis documents |
| **Key Functions** | Document creation, cross-referencing, versioning, knowledge retrieval, domain classification |
| **Integration Points** | Formula Engine, Evidence Engine, Document Engine, Governance Engine |

## 5.2 Formula Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | FE-001 |
| **Primary Responsibility** | Define, derive, and manage mathematical formulas and computations |
| **Core Contract** | CC-FE-001 |
| **Reference Implementation** | FRKP (FC, MF layers); Risk Project (executable) |
| **Inputs** | Knowledge from Knowledge Engine, regulatory formula definitions, symbol standards |
| **Outputs** | Formula Catalog, Mathematical Foundation documents, executable formula contracts |
| **Key Functions** | Formula definition, symbol standardization, mathematical derivation, formula computation |
| **Integration Points** | Knowledge Engine, Risk Analytics Engine, Runtime Engine, Evidence Engine |

## 5.3 Risk Analytics Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | RAE-001 |
| **Primary Responsibility** | Execute risk calculations and produce analytics |
| **Core Contract** | CC-RAE-001 |
| **Reference Implementation** | Risk Project (future) |
| **Inputs** | Formulas from Formula Engine, market data, portfolio data, scenario parameters |
| **Outputs** | Risk measures, analytics reports, scenario results, computed metrics |
| **Key Functions** | Risk calculation, aggregation, scenario generation, stress testing, reporting, validation |
| **Integration Points** | Formula Engine, Runtime Engine, Knowledge Engine, Evidence Engine |

## 5.4 Runtime Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | RE-001 |
| **Primary Responsibility** | Provide execution environment for formulas and analytics |
| **Core Contract** | CC-RE-001 |
| **Reference Implementation** | Risk Project (future) |
| **Inputs** | Executable formulas, calculation requests, data inputs, configuration |
| **Outputs** | Calculation results, execution logs, performance metrics |
| **Key Functions** | Batch processing, real-time calculation, data pipelining, execution management, resource allocation |
| **Integration Points** | Formula Engine, Risk Analytics Engine, Governance Engine |

## 5.5 Evidence Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | EE-001 |
| **Primary Responsibility** | Manage evidence identification, registration, mapping, and traceability |
| **Core Contract** | CC-EE-001 |
| **Reference Implementation** | FRKC (knowledge corpus); FRKP (mappings) |
| **Inputs** | Evidence sources (regulatory texts, research papers, project documents, external references) |
| **Outputs** | Evidence IDs, evidence registers, evidence-to-publication mappings, certification artifacts |
| **Key Functions** | Evidence identification, evidence registration, evidence mapping, traceability tracking, evidence certification |
| **Integration Points** | Knowledge Engine, Governance Engine, Document Engine, Release Engine |

## 5.6 Governance Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | GE-001 |
| **Primary Responsibility** | Define and enforce platform-wide governance rules and standards |
| **Core Contract** | CC-GE-001 |
| **Reference Implementation** | FRKP (Governance/); KPGF (future extract) |
| **Inputs** | Platform policies, standards, templates, review results, compliance evidence |
| **Outputs** | Governance documents, certificates (freeze, release), standards, templates, compliance reports |
| **Key Functions** | Standard definition, document lifecycle management, certification, compliance checking, review management, policy enforcement |
| **Integration Points** | All engines (provides governance rules); Evidence Engine, AI Agent Engine, Release Engine |

## 5.7 Document Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | DE-001 |
| **Primary Responsibility** | Create, store, navigate, and publish platform documents |
| **Core Contract** | CC-DE-001 |
| **Reference Implementation** | FRKP (all layers) |
| **Inputs** | Knowledge documents, evidence mappings, governance metadata, templates |
| **Outputs** | Published documents, navigation structures, indexes, cross-references, document registers |
| **Key Functions** | Document creation, formatting, navigation generation, index creation, cross-reference validation, link integrity checking |
| **Integration Points** | Knowledge Engine, Evidence Engine, Governance Engine, Publishing Engine |

## 5.8 Publishing Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | PE-001 |
| **Primary Responsibility** | Manage publication lifecycle from review-ready to released |
| **Core Contract** | CC-PE-001 |
| **Reference Implementation** | FRKP (bundle review, freeze, release) |
| **Inputs** | Finalized documents, governance approvals, evidence certification, release criteria |
| **Outputs** | Published artifacts, release packages, distribution artifacts, publication certificates |
| **Key Functions** | Publication orchestration, format conversion, distribution management, release packaging, publication certification |
| **Integration Points** | Document Engine, Governance Engine, Release Engine, AI Agent Engine |

## 5.9 AI Agent Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | AAE-001 |
| **Primary Responsibility** | Orchestrate and automate platform tasks through AI agents |
| **Core Contract** | CC-AAE-001 |
| **Reference Implementation** | FRKP (AI Operating Model patterns) |
| **Inputs** | Task requests, platform state, engine outputs, human instructions |
| **Outputs** | Task execution results, validation reports, status dashboards, session handoffs |
| **Key Functions** | Task orchestration, document validation, cross-reference checking, state monitoring, session handoff, engine coordination, reporting |
| **Integration Points** | All engines (orchestration and automation layer); Human reviewers (escalation) |

## 5.10 Bootstrap Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | BE-001 |
| **Primary Responsibility** | Enable rapid creation of new FAEP-conformant projects |
| **Core Contract** | CC-BE-001 |
| **Reference Implementation** | FRKP (Templates/); FAEP Core (future) |
| **Inputs** | Project requirements, domain scope, engine selection, governance template selection |
| **Outputs** | Bootstrapped project repository, initial document scaffold, governance setup, engine wiring configuration |
| **Key Functions** | Template application, repository scaffolding, governance initialization, engine wiring, seed knowledge injection |
| **Integration Points** | Governance Engine, Knowledge Engine, AI Agent Engine, Document Engine |

## 5.11 Plugin Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | PLE-001 |
| **Primary Responsibility** | Manage plugin registration, isolation, lifecycle, and dependency resolution |
| **Core Contract** | CC-PLE-001 |
| **Reference Implementation** | FAEP Core (future) |
| **Inputs** | Plugin packages, registration requests, dependency declarations |
| **Outputs** | Plugin registry, resolved dependency graph, lifecycle events, isolation boundaries |
| **Key Functions** | Plugin registration, dependency resolution, lifecycle management, isolation enforcement, version compatibility checking |
| **Integration Points** | Bootstrap Engine, Governance Engine, AI Agent Engine, all engine plugins |

## 5.12 Workflow Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | WE-001 |
| **Primary Responsibility** | Define and execute platform workflows |
| **Core Contract** | CC-WE-001 |
| **Reference Implementation** | FRKP (evidence-driven publishing workflow); FAEP Core (future) |
| **Inputs** | Workflow definitions, trigger events, engine state |
| **Outputs** | Workflow execution status, completed tasks, state transitions |
| **Key Functions** | Workflow definition, state machine management, task orchestration, conditional branching, error handling |
| **Integration Points** | All engines (workflow triggers and callbacks); AI Agent Engine, Governance Engine |

## 5.13 Search Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | SE-001 |
| **Primary Responsibility** | Provide search and retrieval across all platform artifacts |
| **Core Contract** | CC-SE-001 |
| **Reference Implementation** | FRKP (navigation, cross-reference, master index); FAEP Core (future) |
| **Inputs** | Indexed artifacts, search queries, filter parameters |
| **Outputs** | Search results, ranked matches, cross-reference hits, navigation paths |
| **Key Functions** | Full-text search, metadata search, cross-reference search, faceted filtering, result ranking |
| **Integration Points** | Document Engine, Knowledge Engine, Evidence Engine, Metadata Engine |

## 5.14 Metadata Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | ME-001 |
| **Primary Responsibility** | Manage metadata for all platform artifacts |
| **Core Contract** | CC-ME-001 |
| **Reference Implementation** | FRKP (document information, standards); FRKC (metadata) |
| **Inputs** | Artifact metadata, standard definitions, classification schemas |
| **Outputs** | Metadata registers, classification taxonomies, metadata validation reports |
| **Key Functions** | Metadata schema definition, metadata extraction, metadata validation, classification management, metadata search |
| **Integration Points** | All engines (metadata provisioning and validation); Search Engine, Governance Engine |

## 5.15 Version Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | VE-001 |
| **Primary Responsibility** | Manage versioning of all platform artifacts |
| **Core Contract** | CC-VE-001 |
| **Reference Implementation** | FRKP (VERSION, CHANGELOG, semantic versioning); FAEP Core (future) |
| **Inputs** | Version change requests, artifact identifiers, version policies |
| **Outputs** | Version assignments, version compatibility reports, version history records |
| **Key Functions** | Version assignment, compatibility checking, breaking change detection, version history management, dependency version resolution |
| **Integration Points** | Release Engine, Plugin Engine, Governance Engine, Document Engine |

## 5.16 Release Engine

| Attribute | Description |
| --- | --- |
| **Engine ID** | RLE-001 |
| **Primary Responsibility** | Manage platform releases from readiness assessment to distribution |
| **Core Contract** | CC-RLE-001 |
| **Reference Implementation** | FRKP (V1.0 release, V1.1 release process); FAEP Core (future) |
| **Inputs** | Release candidates, readiness assessments, freeze certificates, governance approvals |
| **Outputs** | Releases, release notes, distribution packages, release certificates |
| **Key Functions** | Release readiness assessment, release packaging, release validation, release distribution, release certification |
| **Integration Points** | Governance Engine, Version Engine, Publishing Engine, AI Agent Engine |

---

# 6. Core Contracts

Every FAEP Core engine is governed by a Core Contract. Core Contracts define:

- **Input Contract** — what inputs the engine accepts, their format, and validation rules
- **Output Contract** — what outputs the engine produces, their format, and quality criteria
- **Boundary Contract** — what the engine is responsible for and what it is not
- **Integration Contract** — how the engine communicates with other engines
- **Lifecycle Contract** — what lifecycle the engine's artifacts follow
- **Governance Contract** — what governance rules apply to the engine's operation

## Contract Definitions

| Contract ID | Name | Owner Engine | Governed Artifacts |
| --- | --- | --- | --- |
| CC-PRJ-001 | Project Contract | Bootstrap Engine | Project structure, naming, repository layout |
| CC-BUN-001 | Bundle Contract | Governance Engine | Bundle structure, lifecycle, review gates |
| CC-KNW-001 | Knowledge Contract | Knowledge Engine | Knowledge documents, layers, cross-references |
| CC-EVD-001 | Evidence Contract | Evidence Engine | Evidence IDs, registers, mappings, certifications |
| CC-FRM-001 | Formula Contract | Formula Engine | Formula definitions, symbols, derivations |
| CC-RSK-001 | Risk Engine Contract | Risk Analytics Engine | Risk calculations, parameters, outputs |
| CC-DOC-001 | Document Contract | Document Engine | Document structure, metadata, navigation |
| CC-NAV-001 | Navigation Contract | Document Engine | Navigation structure, links, indexes |
| CC-MET-001 | Metadata Contract | Metadata Engine | Metadata schemas, classifications, validation |
| CC-VER-001 | Version Contract | Version Engine | Version numbering, compatibility, history |
| CC-REL-001 | Release Contract | Release Engine | Release lifecycle, readiness, packaging |
| CC-PLG-001 | Plugin Contract | Plugin Engine | Plugin registration, isolation, dependencies |
| CC-AGT-001 | Agent Contract | AI Agent Engine | Agent capabilities, boundaries, escalation rules |
| CC-GOV-001 | Governance Contract | Governance Engine | Governance rules, standards, certification |
| CC-SES-001 | Session Contract | AI Agent Engine | Session state, handoff, restoration |

---

# 7. Lifecycle Definitions

Every FAEP Core artifact follows a defined lifecycle. The lifecycle defines stages, transitions, gates, and governance requirements.

## 7.1 Project Lifecycle

```
Proposed → Planned → Active → Review → Completed → Archived
              ↘          ↘         ↘
              Deferred   Deferred  Deferred
```

| Stage | Description | Gate |
| --- | --- | --- |
| Proposed | Project idea captured without commitment | None |
| Planned | Project accepted into planning scope | Boundary review |
| Active | Project is being executed | Resource allocation |
| Review | Project deliverables complete, awaiting validation | Quality review |
| Completed | Project closed with deliverables and evidence | Closure report |
| Deferred | Project paused or postponed | Deferral reason |
| Archived | Project moved to permanent storage | Archive record |

## 7.2 Bundle Lifecycle

```
Planned → Boundary Review → Knowledge Review → Evidence Review
    ↘         ↘
  Deferred   Deferred

Evidence Review → Publishing Review → Publishing Execution → Bundle Review
                                                                     ↘
                                                                   Deferred

Bundle Review → Freeze Gate → Freeze Certification → Release Gate → Released
                                                       ↘
                                                     Deferred
```

| Stage | Description | Gate |
| --- | --- | --- |
| Planned | Bundle identified and scoped | — |
| Boundary Review | Confirm scope, exclusions, layer placement | Boundary approval |
| Knowledge Review | Assess knowledge gaps, canonical concepts | Knowledge readiness |
| Evidence Review | Confirm evidence availability and traceability | Evidence readiness |
| Publishing Review | Confirm publishing mappings and target layers | Publishing readiness |
| Publishing Execution | Create or update bundle documents | — |
| Bundle Review | Verify standards, cross-references, evidence use | Quality check |
| Freeze Gate | Stop scope expansion, correction-only edits | Freeze readiness |
| Freeze Certification | Issue freeze certificate with evidence baseline | Certificate issued |
| Release Gate | Confirm release readiness | Release readiness |
| Released | Bundle included in platform release | Release certificate |

## 7.3 Knowledge Lifecycle

```
Draft → Review → Approved → Frozen → Superseded → Archived
                        ↘         ↘
                      Deferred   Superseded
```

| Stage | Description |
| --- | --- |
| Draft | Initial creation |
| Review | Under review for accuracy and standards compliance |
| Approved | Approved for publication |
| Frozen | Immutable baseline |
| Superseded | Replaced by newer version |
| Deferred | Not yet ready for current cycle |
| Archived | Moved to permanent storage |

## 7.4 Evidence Lifecycle

```
Identified → Registered → Mapped → Certified → Superseded → Archived
```

| Stage | Description |
| --- | --- |
| Identified | Evidence source located |
| Registered | Evidence ID assigned |
| Mapped | Mapped to publications |
| Certified | Evidence verified and certified |
| Superseded | Replaced by newer evidence |
| Archived | Moved to permanent storage |

## 7.5 Formula Lifecycle

```
Specified → Derived → Cataloged → Implemented → Validated → Frozen → Superseded
```

| Stage | Description |
| --- | --- |
| Specified | Formula defined with symbols and parameters |
| Derived | Mathematical derivation documented |
| Cataloged | Added to Formula Catalog |
| Implemented | Executable implementation created |
| Validated | Results verified against expected outputs |
| Frozen | Immutable formula baseline |
| Superseded | Replaced by newer formula version |

## 7.6 Document Lifecycle

```
Draft → Review → Approved → Published → Frozen → Superseded → Archived
```

| Stage | Description |
| --- | --- |
| Draft | Initial content creation |
| Review | Standards and accuracy review |
| Approved | Ready for publication |
| Published | Available in platform |
| Frozen | Immutable baseline |
| Superseded | Replaced by newer version |
| Archived | Moved to permanent storage |

## 7.7 AI Agent Lifecycle

```
Defined → Trained → Deployed → Active → Review → Decommissioned → Archived
```

| Stage | Description |
| --- | --- |
| Defined | Agent capabilities and boundaries specified |
| Trained | Agent configured for platform context |
| Deployed | Agent available for task execution |
| Active | Agent executing tasks |
| Review | Agent performance and compliance review |
| Decommissioned | Agent removed from active service |
| Archived | Agent specification and history preserved |

## 7.8 Release Lifecycle

```
Planned → Readiness Assessed → Release Candidate → Validated → Released → Certified → Archived
```

| Stage | Description |
| --- | --- |
| Planned | Release scope defined |
| Readiness Assessed | All readiness criteria checked |
| Release Candidate | Artifacts assembled for release |
| Validated | Release candidate validated |
| Released | Release distributed |
| Certified | Release certified with evidence |
| Archived | Release artifacts archived |

## 7.9 Plugin Lifecycle

```
Specified → Registered → Dependencies Resolved → Deployed → Active → Updated → Decommissioned → Archived
```

| Stage | Description |
| --- | --- |
| Specified | Plugin contract and metadata defined |
| Registered | Plugin added to plugin registry |
| Dependencies Resolved | All dependencies verified and resolved |
| Deployed | Plugin available for engine integration |
| Active | Plugin executing within platform |
| Updated | Plugin upgraded to new version |
| Decommissioned | Plugin removed from active service |
| Archived | Plugin specification and history preserved |

---

# 8. Plugin Specification

## 8.1 What is a Plugin

A plugin is a self-contained, FAEP Core-conformant component that implements one or more engine contracts. Every engine in the FAEP platform is a plugin. The Plugin Engine manages plugin registration, isolation, lifecycle, and dependencies.

Key characteristics:

- **Self-contained** — a plugin contains all artifacts required for its operation
- **Contract-conformant** — a plugin implements one or more defined Core Contracts
- **Isolated** — a plugin does not directly access other plugins internal state
- **Versioned** — a plugin uses semantic versioning
- **Registrable** — a plugin is registered in the platform plugin registry
- **Replaceable** — a plugin can be replaced by another plugin implementing the same contract

## 8.2 Plugin Requirements

Every plugin must satisfy:

| Requirement | Description | Mandatory |
| --- | --- | --- |
| Plugin ID | Unique identifier following FAEP ID standards | Yes |
| Plugin Name | Human-readable name | Yes |
| Version | Semantic version number | Yes |
| Contract Declaration | List of Core Contracts implemented | Yes |
| Dependencies | List of required plugins and versions | Yes |
| Metadata | Author, description, license, documentation URL | Yes |
| Lifecycle State | Current plugin lifecycle stage | Yes |
| Integration Points | Declared integration contracts with other plugins | Yes |
| Governance Rules | Applicable governance standards | Yes |
| Test Artifacts | Validation and verification artifacts | Recommended |

## 8.3 Plugin Lifecycle

```
Specified → Registered → Resolved → Deployed → Active → Updated → Decommissioned
```

See Section 7.9 for detailed stage definitions.

## 8.4 Plugin Isolation

Plugins are isolated from each other:

- No plugin directly accesses another plugin's internal state
- Plugins communicate only through defined Core Contract integration points
- Plugin failures must not cascade to other plugins
- Plugin resource usage is bounded and monitored
- Plugin isolation is enforced at the specification level (not technology-specific)

## 8.5 Plugin Registration

The Plugin Engine maintains the plugin registry:

- Every plugin must be registered before deployment
- Registration records: Plugin ID, name, version, contracts, dependencies, metadata
- Registration is versioned — each plugin version is registered separately
- Registration requires contract compliance verification
- Registration may be automated via the Bootstrap Engine

## 8.6 Plugin Dependencies

Plugins may declare dependencies on other plugins:

- Dependencies are declared by Plugin ID and version range
- The Plugin Engine resolves the dependency graph before deployment
- Circular dependencies are not permitted
- Version conflicts are reported and must be resolved before deployment
- Optional dependencies are declared separately from required dependencies

## 8.7 Plugin Metadata

Every plugin must declare:

| Metadata Field | Description | Format |
| --- | --- | --- |
| `plugin_id` | Unique identifier | FAEP-ID-xxx |
| `plugin_name` | Human-readable name | Text |
| `version` | Semantic version | MAJOR.MINOR.PATCH |
| `contracts` | Implemented Core Contracts | List of CC IDs |
| `dependencies` | Required plugin IDs and versions | Key-value pairs |
| `author` | Plugin author or organization | Text |
| `description` | Plugin purpose and scope | Text |
| `license` | Distribution license | Text |
| `documentation` | URL or path to documentation | URI |
| `lifecycle` | Current lifecycle stage | Enum |
| `integration_points` | Declared integration contracts | List of IP IDs |

## 8.8 Plugin Versioning

- Plugins use semantic versioning (MAJOR.MINOR.PATCH)
- MAJOR: breaking contract changes
- MINOR: backward-compatible contract additions
- PATCH: backward-compatible bug fixes
- Breaking changes to plugin dependencies require MAJOR version increment
- Plugin version history is maintained by the Version Engine

---

# 9. Reference Implementations

FAEP Core defines contracts. Reference implementations demonstrate those contracts in practice.

## 9.1 FRKP — First Reference Implementation

| Attribute | Value |
| --- | --- |
| **Role** | Primary Reference Implementation for Knowledge Engine, Evidence Engine, Document Engine, Publishing Engine, Governance Engine |
| **Repository** | https://github.com/kbgkim/frpk |
| **Status** | Active (V1.0 stable, V1.1 development) |
| **Demonstrates** | Knowledge layering (RL → KB → AN → FC → MF → IMP → ARCH), evidence-driven publishing, document standards, bundle lifecycle, freeze certification, AI operating model |

FRKP is the authoritative demonstration of FAEP Core contracts. All future FAEP-conformant projects should reference FRKP patterns as the reference implementation.

## 9.2 Risk Project — First Computational Engine

| Attribute | Value |
| --- | --- |
| **Role** | Reference Implementation for Formula Engine, Risk Analytics Engine, Runtime Engine |
| **Repository** | Not yet created |
| **Status** | Future |
| **Demonstrates** | Formula execution, risk analytics computation, runtime environment, batch processing |

The Risk Project will demonstrate how computational engines integrate with FAEP Core through Formula, Risk Analytics, and Runtime contracts.

## 9.3 IB Project — First Business Platform

| Attribute | Value |
| --- | --- |
| **Role** | First downstream business platform built on FAEP Core |
| **Repository** | Not yet created |
| **Status** | Future |
| **Demonstrates** | FAEP bootstrap process, domain knowledge structuring, business workflow integration |

The IB Project will validate FAEP Core's bootstrap specification and demonstrate how business platforms are built on FAEP foundations.

## 9.4 Future Projects

| Project Type | Role | Target | Engine Focus |
| --- | --- | --- | --- |
| Credit Risk Engine | Computational Engine | Future | Risk Analytics, Runtime |
| Market Risk Engine | Computational Engine | Future | Risk Analytics, Runtime |
| Compliance Platform | Business Platform | Future | Knowledge, Evidence, Governance |
| Regulatory Reporting | Business Platform | Future | Document, Publishing, Governance |

## 9.5 Reference Implementation Map

```
FAEP Core (Contracts)
    │
    ├── FRKP (Knowledge, Evidence, Document, Publishing, Governance)
    │       └── Demonstrates all Core Contracts for knowledge domains
    │
    ├── Risk Project (Formula, Risk Analytics, Runtime)
    │       └── Demonstrates computational engine contracts
    │
    ├── IB Project (Business Platform)
    │       └── Demonstrates bootstrap and business integration contracts
    │
    └── Future Projects (Domain-Specific)
            └── Demonstrate domain specialization within Core Contracts
```

---

# 10. Repository Strategy

## 10.1 Evaluation

### Option A: Single Repository

| Criterion | Assessment |
| --- | --- |
| Simplicity | High — single clone, single workflow |
| Consistency | High — single governance, single CI/CD |
| Traceability | High — all artifacts in one versioned space |
| Scalability | Low — repository grows with each project |
| Isolation | Low — all projects share same history |
| Access Control | Low — single permission boundary |
| Discoverability | Medium — all content in one place |

**Best for:** Small teams, early stages, proof of concept.

### Option B: Multiple Repository

| Criterion | Assessment |
| --- | --- |
| Simplicity | Low — multiple clones, multiple workflows |
| Consistency | Low — requires cross-repository governance synchronization |
| Traceability | Medium — cross-repository references require tooling |
| Scalability | High — each project scales independently |
| Isolation | High — project boundaries are repository boundaries |
| Access Control | High — per-repository permissions |
| Discoverability | Low — content spread across repositories |

**Best for:** Large teams, independent projects, strict access control.

### Option C: Hybrid (Recommended)

| Criterion | Assessment |
| --- | --- |
| Simplicity | Medium — balanced approach |
| Consistency | Medium — Core in single repository, projects in separate repos |
| Traceability | High — Core traces across projects via contracts |
| Scalability | High — projects independent; Core stable |
| Isolation | High — project boundaries respected |
| Access Control | High — per-repository with Core as shared foundation |
| Discoverability | Medium — Core discoverable; projects reference Core |

**Best for:** FAEP Core as shared foundation with independent projects.

## 10.2 Recommendation: Hybrid Approach

FAEP Core recommends a **Hybrid Repository Strategy**:

1. **FAEP Core Repository** — contains Core Contracts, Platform Specification, shared governance, plugin registry, and Bootstrap Engine templates. This is the single source of truth for the platform contract.

2. **Project Repositories** — each FAEP-conformant project has its own repository. FRKP, Risk Project, IB Project, and all future projects operate independently.

3. **Knowledge Corpus Repository** — the authoritative evidence and knowledge source (e.g., FRKC) is a separate repository to maintain independence from any single project.

### Rationale

- The **Core Repository** remains stable, small, and focused. It is the platform contract, not a project implementation.
- Each **Project Repository** owns its content, lifecycle, and release schedule. Projects are independent but conformant.
- The **Knowledge Corpus Repository** maintains evidence independence. No single project owns the evidence.
- Cross-repository references are managed through documented Core Contract IDs and project-level dependency declarations.
- Repository synchronization is managed through release contracts rather than shared code.

### Repository Map

```
FAEP Core Repository (github.com/kbgkim/faep)
    ├── Core Contracts
    ├── Platform Specification
    ├── Governance Standards
    ├── Plugin Registry
    ├── Bootstrap Templates
    └── Reference Implementation Index

FRKP Repository (github.com/kbgkim/frpk)
    └── First Reference Implementation

FRKC Repository (github.com/kbgkim/frkp-knowledge)
    └── Authoritative Knowledge Corpus

Risk Project Repository (future)
    └── Computational Engine

IB Project Repository (future)
    └── Business Platform
```

---

# 11. Project Bootstrap Specification

A project is **FAEP Compatible** when the following artifacts exist and conform to FAEP Core Contracts.

## 11.1 Required Artifacts

| Artifact | Description | Core Contract |
| --- | --- | --- |
| Project Bootstrap Document | Project scope, vision, objectives | CC-PRJ-001 |
| Project Charter | Governance, roles, working rules | CC-PRJ-001 |
| Master Document Index | Complete register of all project documents | CC-DOC-001 |
| Navigation Structure | Document hierarchy and cross-references | CC-NAV-001 |
| Governance Standards | Document ID, architecture, bundle, document standards | CC-GOV-001 |
| Bundle Framework | Bundle definition and lifecycle specification | CC-BUN-001 |
| Session Management | Session handoff documents | CC-AGT-001, CC-SES-001 |
| Plugin Declaration | Registered plugins and their contracts | CC-PLG-001 |
| Version Declaration | Current version and versioning policy | CC-VER-001 |
| Evidence Baseline | Evidence sources and mapping framework | CC-EVD-001 |

## 11.2 Required Directory Structure

A FAEP-conformant project must have at minimum:

```
00_Project_Management/
    01_Foundation/
        FRKP-000_PROJECT_BOOTSTRAP.md
        FRKP-001_PROJECT_CHARTER.md
    02_Sessions/
        PROJECT_STATE.md
        AI_SESSION_HANDOFF.md
        MASTER_SESSION.md
    03_Plans/
        PLAN_INDEX.md
        active.md
        next-session.md
        CURRENT_WORK.md
    04_Governance/
        FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md
        Standards/
        Templates/
```

The directory structure may be adapted per project domain, but the minimum artifacts and governance framework must exist.

## 11.3 Required Standards

A FAEP-conformant project must adopt:

| Standard | Description |
| --- | --- |
| Document ID Standard | Unique, hierarchical document identifiers |
| Document Standard | Template structure and metadata requirements |
| Architecture Standard | Engine documentation and integration specification |
| Bundle Standard | Bundle lifecycle, review, and freeze rules |
| Glossary Standard | Terminology management |
| Abbreviation Standard | Abbreviation registry |

## 11.4 Bootstrap Process

```
1. Define project scope and domain
         │
         ▼
2. Select FAEP Core contracts to implement
         │
         ▼
3. Select reference implementations to follow
         │
         ▼
4. Bootstrap Engine creates repository scaffold
         │
         ▼
5. Governance Engine initializes standards
         │
         ▼
6. Knowledge Engine creates seed documents
         │
         ▼
7. Plugin Engine registers project plugins
         │
         ▼
8. AI Agent Engine initialized with project context
         │
         ▼
9. Human review and project launch
```

---

# 12. Platform Traceability

FAEP Core defines a vertical traceability chain that connects every platform artifact from evidence through to AI agent execution.

## 12.1 Traceability Chain

```
Knowledge (Evidence Sources)
    │
    ▼
Evidence (Registered, Mapped, Certified)
    │
    ▼
Formula (Specified, Derived, Cataloged)
    │
    ▼
Risk Analytics (Computed, Validated)
    │
    ▼
Document (Drafted, Reviewed, Published)
    │
    ▼
Release (Readiness Assessed, Validated, Released)
    │
    ▼
AI Agent (Orchestrated, Validated, Reported)
```

## 12.2 Traceability Contracts

| From | To | Contract | Traceability Rule |
| --- | --- | --- | --- |
| Knowledge | Evidence | CC-EVD-001 | Every knowledge document must reference at least one evidence source |
| Evidence | Formula | CC-FRM-001 | Every formula must reference evidence sources for each input |
| Formula | Risk Analytics | CC-RSK-001 | Every risk calculation must reference the formula definition |
| Risk Analytics | Document | CC-DOC-001 | Every document containing risk analytics must reference the calculation source |
| Document | Release | CC-REL-001 | Every release must reference all included documents and their freeze certificates |
| Release | AI Agent | CC-AGT-001 | Every AI agent task must reference the release context |
| AI Agent | Governance | CC-GOV-001 | Every AI agent action must be governable and auditable |

## 12.3 Traceability Rules

| Rule ID | Description |
| --- | --- |
| TR-PLT-001 | Every platform artifact has a traceable parent and child |
| TR-PLT-002 | Traceability chains are documented and auditable |
| TR-PLT-003 | Broken traceability chains must be flagged and resolved before release |
| TR-PLT-004 | Traceability is automated where possible; manual overrides are documented |
| TR-PLT-005 | Traceability metadata is stored with the artifact, not externally |

---

# 13. Governance Model

FAEP Core defines six governance domains. Each domain has standards, processes, and certification requirements.

## 13.1 Architecture Governance

| Aspect | Description |
| --- | --- |
| Scope | Engine definitions, contracts, integration points, platform structure |
| Standards | FAEP Core Platform Specification, Architecture Standards |
| Processes | Architecture review, contract change management, engine registration |
| Certification | Architecture compliance certificate required for project bootstrap |
| Authority | FAEP Architecture Board |

## 13.2 Knowledge Governance

| Aspect | Description |
| --- | --- |
| Scope | Knowledge documents, layers, cross-references, domain coverage |
| Standards | Document ID Standard, Document Standard, Glossary Standard |
| Processes | Knowledge review, domain coverage assessment, cross-reference validation |
| Certification | Knowledge baseline certification required for publication |
| Authority | Knowledge Domain Lead |

## 13.3 Evidence Governance

| Aspect | Description |
| --- | --- |
| Scope | Evidence identification, registration, mapping, certification |
| Standards | Evidence Contract, Evidence-Driven Publishing Workflow |
| Processes | Evidence mapping review, evidence certification, traceability audit |
| Certification | Evidence certification required for freeze and release |
| Authority | Evidence Manager |

## 13.4 Release Governance

| Aspect | Description |
| --- | --- |
| Scope | Release planning, readiness assessment, validation, distribution |
| Standards | Release Contract, Version Contract |
| Processes | Release readiness assessment, release candidate validation, release certification |
| Certification | Release certificate required for distribution |
| Authority | Release Manager |

## 13.5 AI Governance

| Aspect | Description |
| --- | --- |
| Scope | AI agent capabilities, boundaries, task execution, validation |
| Standards | Agent Contract, AI Operating Model |
| Processes | Agent capability review, task validation, performance monitoring |
| Certification | Agent certification required for deployment |
| Authority | AI Governance Board |

## 13.6 Project Governance

| Aspect | Description |
| --- | --- |
| Scope | Project lifecycle, bootstrap, compliance, closure |
| Standards | Project Contract, Bootstrap Specification |
| Processes | Project bootstrap, compliance review, closure certification |
| Certification | Project compliance certificate required for active status |
| Authority | Project Lead |

---

# 14. Extension Model

FAEP Core is designed to be extended without modification to the Core itself.

## 14.1 Extension Principles

- **Plugin-based** — new engines are added as plugins implementing Core Contracts
- **Contract-stable** — Core Contracts are stable; plugins implement contracts, not modify them
- **Isolated** — new engines are isolated from existing ones
- **Registered** — new engines register through the Plugin Engine
- **Governed** — new engines are subject to the same governance as existing engines

## 14.2 Adding a New Engine

To add a new engine without changing the Core:

1. **Define the Engine Contract** — specify inputs, outputs, boundaries, lifecycle, and integration points following Core Contract format
2. **Register as Plugin** — add the engine as a plugin through the Plugin Engine
3. **Implement Core Contracts** — the new engine must implement applicable Core Contracts (e.g., Governance, Evidence, Document)
4. **Declare Integration Points** — define how the new engine integrates with existing engines
5. **Create Reference Implementation** — demonstrate the contract with a reference implementation
6. **Certify Compliance** — obtain governance certification for the new engine

## 14.3 Extension Examples

| Extension Type | Example | Integration |
| --- | --- | --- |
| New Computational Engine | Credit Risk Engine | Implements Risk Analytics Contract, uses Formula Contract |
| New Knowledge Domain | ESG Risk Knowledge | Implements Knowledge Contract, uses Evidence Contract |
| New AI Agent Capability | Automated Reviewer | Implements Agent Contract, uses Document Contract |
| New Workflow | Compliance Reporting Workflow | Implements Workflow Contract, uses Document and Governance Contracts |

## 14.4 Non-Extension Boundaries

The following must not be changed when extending FAEP Core:

- Core Contract definitions (CC-*)
- Platform Principles (Section 4)
- Governance Model (Section 13)
- Traceability Contracts (Section 12)
- Lifecycle Definitions (Section 7)

Changes to these require a Core Platform Specification update, not an extension.

---

# 15. Migration Strategy

## 15.1 Current State

```
FRKP (Knowledge Engine, Evidence Engine, Document Engine, Governance Engine)
    └── FAEP architecture defined within FRKP (FRKP-003, FRKP-004)

FRKC (Authoritative Knowledge Corpus)
    └── Evidence source for FRKP publications

Risk Project (Not yet created)
    └── Future Formula Engine, Risk Analytics Engine, Runtime Engine

IB Project (Not yet created)
    └── Future Business Platform
```

## 15.2 Target State

```
FAEP Core Repository (github.com/kbgkim/faep)
    ├── Core Contracts
    ├── Platform Specification
    ├── Governance Standards
    ├── Plugin Registry
    ├── Bootstrap Templates
    └── Reference Implementation Index
           │
           ├── FRKP Repository (Reference Implementation)
           │       ├── Knowledge Engine
           │       ├── Evidence Engine
           │       ├── Document Engine
           │       └── Governance Engine
           │
           ├── Risk Project Repository (Computational Engine)
           │       ├── Formula Engine
           │       ├── Risk Analytics Engine
           │       └── Runtime Engine
           │
           ├── IB Project Repository (Business Platform)
           │       └── Business Knowledge, Workflow, Integration
           │
           └── Future Project Repositories (various)
```

## 15.3 Migration Phases

### Phase 1: FAEP Core Definition (Current — PLAN-011, PLAN-012)

| Step | Description | Status |
| --- | --- | --- |
| 1.1 | Define FAEP Master Architecture | ✅ Complete (PLAN-011) |
| 1.2 | Define FAEP Core Platform Specification | ✅ Complete (PLAN-012) |
| 1.3 | Engine contracts defined | ✅ Complete |
| 1.4 | Platform principles and governance defined | ✅ Complete |

### Phase 2: IB Project Bootstrap

| Step | Description | Target |
| --- | --- | --- |
| 2.1 | Define IB Project architecture within FAEP framework | Next PLAN |
| 2.2 | Bootstrap IB Project repository | Next PLAN |
| 2.3 | Apply FAEP Core governance to IB Project | Next PLAN |
| 2.4 | Validate bootstrap process | After Phase 2 |

### Phase 3: Risk Project Integration

| Step | Description | Target |
| --- | --- | --- |
| 3.1 | Define Risk Project engine contracts | Future |
| 3.2 | Implement Formula Engine reference | Future |
| 3.3 | Implement Risk Analytics Engine reference | Future |
| 3.4 | Implement Runtime Engine reference | Future |

### Phase 4: FAEP Core Extraction

| Step | Description | Target |
| --- | --- | --- |
| 4.1 | Create FAEP Core dedicated repository | Future |
| 4.2 | Migrate Core Contracts to FAEP repository | Future |
| 4.3 | Extract KPGF governance framework | Future |
| 4.4 | Migrate project bootstrap templates | Future |
| 4.5 | Establish cross-repository governance synchronization | Future |
| 4.6 | Renumber FAEP documents to FAEP namespace | Future |

### Phase 5: Independent Platform

| Step | Description | Target |
| --- | --- | --- |
| 5.1 | FAEP Core operates as independent platform | Future |
| 5.2 | FRKP operates as pure reference implementation | Future |
| 5.3 | Multiple FAEP-conformant projects active | Future |
| 5.4 | Plugin ecosystem established | Future |
| 5.5 | AI Agent Engine operational | Future |

## 15.4 Migration Rules

| Rule | Description |
| --- | --- |
| MR-001 | No existing frozen artifacts are modified during migration |
| MR-002 | No existing document IDs are renamed |
| MR-003 | FAEP Core contracts remain stable during migration of projects |
| MR-004 | Each project migrates independently at its own pace |
| MR-005 | Backward compatibility is maintained until a documented breaking release |

---

# 16. Open Issues

| Issue ID | Description | Impact | Proposed Resolution | Owner |
| --- | --- | --- | --- | --- |
| OPI-001 | FAEP Core repository location and ownership not established | Blocks Phase 4 | Create FAEP Core repository under kbgkim organization | FAEP Governance |
| OPI-002 | Plugin Engine specification requires formal metadata schema | Low | Define JSON Schema for plugin metadata | FAEP Governance |
| OPI-003 | AI Agent Engine capability boundaries need refinement | Medium | Document concrete agent patterns from FRKP experience | FAEP Governance |
| OPI-004 | Cross-repository reference resolution not specified | Medium | Define reference resolution protocol for multi-repo traceability | FAEP Governance |
| OPI-005 | Evidence Engine integration across project repositories | Medium | Define cross-project evidence sharing protocol | FAEP Governance |
| OPI-006 | Risk Analytics Engine contract requires domain-specific refinement | Low | Defer to Risk Project architecture definition | Risk Project |
| OPI-007 | IB Project bootstrap validation cannot occur until IB Project exists | Low | Defer to Phase 2 | IB Project |
| OPI-008 | Plugin dependency conflict resolution strategy not fully defined | Low | Defer to Plugin Engine implementation | FAEP Governance |

---

# 17. Deferred Items

| DEF ID | Description | Rationale | Target Phase |
| --- | --- | --- | --- |
| DEF-CORE-001 | FAEP Core dedicated repository creation | Keep within FRKP during early phases | Phase 4 |
| DEF-CORE-002 | Plugin Engine reference implementation | Not required until multi-plugin projects exist | Phase 3 |
| DEF-CORE-003 | AI Agent Engine reference implementation | Future capability; contract defined | Phase 5 |
| DEF-CORE-004 | Search Engine reference implementation | Not required until multi-project search needed | Phase 4 |
| DEF-CORE-005 | Workflow Engine formal specification | Workflow patterns exist in FRKP; formalization deferred | Phase 3 |
| DEF-CORE-006 | Metadata Engine formal schema | Metadata patterns exist in FRKP; schema formalization deferred | Phase 3 |
| DEF-CORE-007 | Version Engine automated compatibility checking | Version patterns exist; automation deferred | Phase 4 |
| DEF-CORE-008 | Release Engine automated packaging | Release patterns exist in FRKP; automation deferred | Phase 4 |
| DEF-CORE-009 | FAEP document renumbering to FAEP namespace | Currently under FRKP namespace | Phase 4 |
| DEF-CORE-010 | Formal interface contracts (OpenAPI, gRPC, JSON Schema) | Text-based contracts sufficient for early phases | Phase 3 |

---

# 18. Architecture Decisions

### AD-001: FAEP Core as Platform Contract

**Decision:** FAEP Core is defined as the platform contract — not an application, not FRKP, not the Risk Project. All future Financial AI projects shall conform to FAEP Core contracts.

**Rationale:** Separating the platform contract from any single implementation ensures the platform outlives any project. FRKP, Risk Project, and IB Project are implementations of the contract, not the contract itself.

**Status:** Accepted.

### AD-002: Sixteen-Engine Platform Decomposition

**Decision:** FAEP Core is decomposed into sixteen engines, each with a single primary responsibility. The engines are: Knowledge, Formula, Risk Analytics, Runtime, Evidence, Governance, Document, Publishing, AI Agent, Bootstrap, Plugin, Workflow, Search, Metadata, Version, Release.

**Rationale:** The nine-engine model from FRKP-003 is refined to sixteen engines to reflect the separation of concerns more precisely. Document and Publishing are separated (creation vs. distribution). Version and Release are separated (versioning vs. releasing). Plugin, Workflow, Search, and Metadata are added as first-class engines.

**Status:** Accepted.

### AD-003: Contracts Before Implementation

**Decision:** Every engine is defined by a Core Contract before any implementation begins. Contracts specify inputs, outputs, boundaries, lifecycle, integration, and governance.

**Rationale:** Contract-first architecture ensures consistency, testability, and replaceability. Reference implementations demonstrate contracts without becoming the contract themselves.

**Status:** Accepted.

### AD-004: Reference Implementation Pattern

**Decision:** Every FAEP Core contract is accompanied by at least one reference implementation. FRKP is the primary reference implementation for all Core contracts.

**Rationale:** Reference implementations ground abstract contracts in concrete practice. FRKP demonstrates all contracts through real knowledge engineering work.

**Status:** Accepted.

### AD-005: FRKP as First Reference Implementation

**Decision:** FRKP is designated as the first reference implementation of FAEP Core. FRKP demonstrates Knowledge Engine, Evidence Engine, Document Engine, Publishing Engine, and Governance Engine contracts.

**Rationale:** FRKP already implements these patterns through Bundle-007 and Version 1.0. Extracting FAEP Core from FRKP experience validates the contracts against real-world usage.

**Status:** Accepted.

### AD-006: Plugin Architecture for All Engines

**Decision:** Every engine is a plugin. Engines are registered, isolated, versioned, and replaceable through the Plugin Engine.

**Rationale:** Plugin architecture enables independent development, testing, and deployment of engines. New engines can be added without modifying existing ones. Engines can be replaced without breaking the platform.

**Status:** Accepted.

### AD-007: Hybrid Repository Strategy

**Decision:** FAEP Core recommends a hybrid repository strategy with one Core repository, multiple project repositories, and one knowledge corpus repository.

**Rationale:** The Core repository remains stable and focused. Project repositories are independent. The knowledge corpus is independent of any single project. Cross-repository integration is managed through contracts rather than shared code.

**Status:** Accepted.

### AD-008: Keep Within FRKP During Early Phases

**Decision:** FAEP Core artifacts remain in the FRKP repository (FRKP-003, FRKP-004) during Phases 1-3. Dedicated FAEP Core repository creation is deferred to Phase 4.

**Rationale:** Zero disruption to current workflow. FRKP governance and conventions are mature. Dedicated repository adds overhead without proportional benefit during early phases.

**Status:** Accepted.

### AD-009: Text-Based Contracts Initially

**Decision:** Core Contracts are defined as text-based specifications initially. Formal machine-readable contracts (JSON Schema, OpenAPI, gRPC) are deferred to Phase 3.

**Rationale:** Text-based contracts are sufficient for early phases. Formalization adds overhead without proportional benefit until multiple engine implementations exist.

**Status:** Accepted.

### AD-010: Progressive Formalization

**Decision:** Contracts may start as text and progressively formalize to machine-readable schemas as the platform matures.

**Rationale:** Progressive formalization avoids premature standardization while enabling automation where needed. Each contract formalizes when multiple implementations require unambiguous machine-readable interfaces.

**Status:** Accepted.

### AD-011: Evidence-Driven Traceability

**Decision:** Every platform artifact must be traceable to its evidence source. Traceability is enforced through contracts (CC-EVD-001) and automated where possible.

**Rationale:** Evidence-driven traceability is the foundation of platform trustworthiness. Automated traceability reduces manual audit overhead and ensures consistency.

**Status:** Accepted.

### AD-012: Human + AI Governance Model

**Decision:** AI agents assist but do not replace human governance authority. Humans retain authority over acceptance, freeze, release, and strategic decisions.

**Rationale:** AI agents lack the domain judgment and accountability required for governance decisions. Human authority ensures accountability while AI automation improves efficiency.

**Status:** Accepted.

### AD-013: Bundle Lifecycle as Standard

**Decision:** The bundle lifecycle (Planned → Boundary Review → Knowledge Review → Evidence Review → Publishing Review → Execution → Freeze → Release) is defined as the standard lifecycle for all FAEP knowledge work.

**Rationale:** The bundle lifecycle has been validated through FRKP Bundle-007 execution. It provides the right balance of rigor and flexibility for knowledge engineering work.

**Status:** Accepted.

### AD-014: Minimum Viable Governance

**Decision:** Governance rules must be proportional to artifact criticality. Higher-criticality artifacts (releases, freezes) require more governance than lower-criticality artifacts (typo fixes, minor updates).

**Rationale:** Disproportionate governance overhead reduces productivity without proportional quality improvement. Minimum viable governance ensures rigor where needed without bureaucracy everywhere.

**Status:** Accepted.

### AD-015: Domain Isolation Principle

**Decision:** Each platform domain (Knowledge, Formula, Risk, Evidence, Governance) is isolated. Domains communicate only through defined integration points. No domain directly accesses another domain's internal state.

**Rationale:** Domain isolation prevents unintended coupling, enables independent development, and ensures that changes in one domain do not cascade to others.

**Status:** Accepted.

### AD-016: AI Agent Readiness

**Decision:** Every platform artifact must be processable by AI agents. This requires consistent structure, machine-readable metadata, resolvable cross-references, and checkable standards.

**Rationale:** AI agents cannot effectively assist with artifacts they cannot parse. AI agent readiness ensures that automation, validation, and orchestration are feasible across the platform.

**Status:** Accepted.

---

# 19. Future Roadmap

## Phase 1: Current (Complete)

| Step | Description | Status |
| --- | --- | --- |
| Define FAEP Master Architecture | FRKP-003 | Complete |
| Define FAEP Core Platform Specification | FRKP-004 (this document) | Complete |
| Define sixteen-engine decomposition | AD-002 | Complete |
| Define Core Contracts | 15 contracts defined | Complete |
| Define platform principles | 18 principles | Complete |

## Phase 2: IB Project Bootstrap

| Step | Description | Target |
| --- | --- | --- |
| Define IB Project architecture | Architecture document | Next PLAN |
| Bootstrap IB Project repository | Repository scaffold | Next PLAN |
| Apply FAEP Core governance | Governance initialization | Next PLAN |
| Validate bootstrap specification | Lessons learned | After Phase 2 |

## Phase 3: Risk Project Integration

| Step | Description | Target |
| --- | --- | --- |
| Define Risk Project engine contracts | Formula, Risk Analytics, Runtime | Future |
| Implement Risk Project reference | Computational engine | Future |
| Enable cross-project traceability | FRKP ↔ Risk Project | Future |
| Formalize machine-readable contracts | JSON Schema, OpenAPI | Future |

## Phase 4: FAEP Core Extraction

| Step | Description | Target |
| --- | --- | --- |
| Create FAEP Core repository | github.com/kbgkim/faep | Future |
| Extract KPGF governance framework | Reusable governance | Future |
| Migrate Core Contracts to FAEP namespace | Renumbering | Future |
| Establish cross-repository synchronization | Release contracts | Future |
| Implement Plugin Engine | Plugin registry | Future |

## Phase 5: AI Native Platform

| Step | Description | Target |
| --- | --- | --- |
| Implement AI Agent Engine | Orchestration and automation | Future |
| Enable agent-driven publishing | Automated validation | Future |
| Establish plugin ecosystem | Third-party plugins | Future |
| Achieve full platform automation | Human-supervised AI execution | Future |

---

# 20. Appendix

## 20.1 Terminology

| Term | Definition |
| --- | --- |
| **FAEP Core** | The platform contract governing all Financial AI projects. Not an application. Not FRKP. |
| **Core Contract** | A formal specification defining inputs, outputs, boundaries, lifecycle, integration, and governance for a platform engine. |
| **Reference Implementation** | A concrete implementation of a Core Contract that demonstrates the contract in practice. |
| **Plugin** | A self-contained, FAEP Core-conformant component implementing one or more engine contracts. |
| **Engine** | A platform component with a single primary responsibility, implemented as a plugin. |
| **Bootstrap** | The process of creating a new FAEP-conformant project from reusable templates and contracts. |
| **Lifecycle** | A defined sequence of stages an artifact passes through, with gates at each transition. |
| **Freeze** | An immutable state where no further changes are permitted. |
| **Evidence** | Authoritative source material that supports platform claims and decisions. |
| **Traceability** | The ability to trace any artifact through its chain of dependencies to origin. |
| **Governance** | The rules, standards, and processes that control platform operations and decisions. |
| **Bundle** | A scoped collection of knowledge artifacts with defined lifecycle and governance. |
| **Contract-First** | An architectural approach where contracts are defined before implementation. |

## 20.2 Glossary

| Term | Definition |
| --- | --- |
| **AI Agent** | A platform engine that orchestrates, validates, monitors, and assists platform tasks. |
| **AI Native** | A design philosophy where AI is a first-class platform capability, not an add-on. |
| **Architecture Decision** | A recorded architectural choice with rationale and alternatives considered. |
| **Artifact** | Any versioned, governed platform output (document, evidence, formula, release). |
| **Bootstrap Engine** | The engine that creates new FAEP-conformant project scaffolds. |
| **Compatibility** | The ability of a component to work with other components at defined contract levels. |
| **Contract** | A formal specification of what a component provides and requires. |
| **Domain** | A logical area of platform responsibility (Knowledge, Formula, Risk, Evidence, Governance). |
| **Engine** | A platform component with single primary responsibility. |
| **Evidence Engine** | The engine managing evidence identification, registration, mapping, and certification. |
| **Freeze Certificate** | A governance document certifying that an artifact is frozen with identified evidence baseline. |
| **Governance Engine** | The engine defining and enforcing platform-wide governance rules. |
| **Integration Point** | A defined communication channel between two engines. |
| **Knowledge Engine** | The engine managing structured knowledge documents. |
| **Plugin Engine** | The engine managing plugin registration, isolation, lifecycle, and dependencies. |
| **Reference Implementation** | A concrete implementation of a Core Contract. |
| **Release Engine** | The engine managing platform releases from readiness to distribution. |
| **Runtime Engine** | The engine providing execution environment for formulas and analytics. |
| **Version Engine** | The engine managing versioning of all platform artifacts. |

## 20.3 Abbreviations

| Abbreviation | Full Form |
| --- | --- |
| **AAE** | AI Agent Engine |
| **AD** | Architecture Decision |
| **AN** | Analysis |
| **ARCH** | Architecture |
| **BE** | Bootstrap Engine |
| **CC** | Core Contract |
| **DE** | Document Engine |
| **EE** | Evidence Engine |
| **FAEP** | Financial AI Engineering Platform |
| **FC** | Formula Catalog |
| **FE** | Formula Engine |
| **FRKC** | Financial Risk Knowledge Corpus |
| **FRKP** | Financial Risk Knowledge Platform |
| **GE** | Governance Engine |
| **IB** | Investment Banking |
| **ID** | Identifier |
| **IMP** | Implementation |
| **KB** | Knowledge Base |
| **KE** | Knowledge Engine |
| **KPGF** | Knowledge Platform Governance Framework |
| **ME** | Metadata Engine |
| **MF** | Mathematical Foundation |
| **PE** | Publishing Engine |
| **PLE** | Plugin Engine |
| **RAE** | Risk Analytics Engine |
| **RE** | Runtime Engine |
| **RL** | Reference Library |
| **RLE** | Release Engine |
| **SE** | Search Engine |
| **VE** | Version Engine |
| **WE** | Workflow Engine |

---

## Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Core Platform Specification (PLAN-012) |
