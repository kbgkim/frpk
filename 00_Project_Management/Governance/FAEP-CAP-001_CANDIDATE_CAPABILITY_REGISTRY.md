# FAEP-CAP-001 — Candidate Capability Registry

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-CAP-001 |
| Document Name | Candidate Capability Registry |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-CAP-000; FAEP-FOUNDATION-000; FAEP-FOUNDATION-001; FAEP-VALIDATION-000; FAEP-VALIDATION-001; FAEP-CONTRACT-000; FAEP-CONTRACT-001; FRKP-003; FRKP-004; FRKP-005; PLAN-016; PLAN-020 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-020 |

---

# 1. Purpose

This registry records Candidate Capabilities discovered from FAEP Reference Implementations.

Candidate Capabilities are implementation patterns demonstrated by FRKC, FRKP, or Risk Platform. They are distinct from Candidate Contracts (FAEP-CONTRACT-001). Capability Discovery identifies what implementations *can do*. Contract proposals define how implementations *shall interoperate*.

No Capability Standard shall be created from this registry. This registry exists for discovery and classification only.

---

# 2. Registry Rules

| Rule | Description |
| --- | --- |
| CR-001 | Capability IDs follow the pattern CAP-{DOMAIN}-{NNN} where DOMAIN is KNW, PUB, EXE, GOV, or AI |
| CR-002 | IDs are assigned sequentially within each domain |
| CR-003 | Each capability must reference at least one Reference Implementation as evidence |
| CR-004 | Speculative or unsupported capabilities are recorded in the Backlog section, not as Candidates |
| CR-005 | Registry entries do not modify Core Contracts, Standards, or frozen Foundation artifacts |

---

# 3. Capability Discovery Summary

| Metric | Count |
| --- | --- |
| Total Candidate Capabilities Discovered | 36 |
| Knowledge Domain (CAP-KNW) | 8 |
| Publishing Domain (CAP-PUB) | 8 |
| Execution Domain (CAP-EXE) | 14 |
| Governance Domain (CAP-GOV) | 5 |
| AI-Ready Domain (CAP-AI) | 1 |
| Backlog Capabilities | 9 |

---

# 4. Candidate Capability Registry

## 4.1 Knowledge Domain

### CAP-KNW-001 — Canonical Knowledge Storage

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-001 |
| Title | Canonical Knowledge Storage |
| Description | Store authoritative knowledge items with unique identifiers, semantic versioning, lifecycle states, and structured metadata. Each item exists in exactly one canonical location within FRKC. |
| Primary Domain | Knowledge |
| Secondary Domains | Governance |
| Provider(s) | FRKC — Knowledge items in RL, KB, AN layers |
| Consumer(s) | FRKP (publishing), Risk Platform (formula references), AI Platform (retrieval) |
| Implementation Evidence | FRKC repository — documents/artifacts with IDs (RL-170, KB-271, etc.), versions, status fields, cross-references |
| Maturity | Production — FRKC v0.1 certified with observations |
| Cross-Program Occurrence | 1 (FRKC only) |
| Overlap with Existing Contracts | CC-KNW-001 (Knowledge Contract) — capability is broader than contract scope |
| Overlap with Other Candidates | CAP-KNW-005 (Knowledge Layering) — canonical items are stored per layer |
| Validation Priority | P2 — High |

### CAP-KNW-002 — Evidence Registration & Mapping

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-002 |
| Title | Evidence Registration & Mapping |
| Description | Register evidence sources with unique IDs, metadata, and lifecycle state. Map evidence to knowledge items. Support certification workflows. |
| Primary Domain | Knowledge |
| Secondary Domains | Governance |
| Provider(s) | FRKC — evidence items in FRKC repository with EVD- prefixed IDs; FRKP — evidence mapping in publication workflow |
| Consumer(s) | FRKP (evidence-driven publishing), Risk Platform (PromotionEvidence) |
| Implementation Evidence | FRKC evidence register (EVD-000340 series); FRKP evidence mapping in PLAN-005/PLAN-006; Risk Platform PromotionEvidence entity |
| Maturity | Production in FRKC and Risk Platform; formal evidence lifecycle differs between implementations |
| Cross-Program Occurrence | 3 (FRKC, FRKP, Risk Platform) |
| Overlap with Existing Contracts | CC-EVD-001 (Evidence Contract) — partially covered; FAEP-STD-003 (Evidence Standard) |
| Overlap with Other Candidates | CAP-EXE-009 (Evidence-Gated Promotion) — overlaps in governance evidence workflow |
| Validation Priority | P1 — Critical |

### CAP-KNW-003 — Terminology Management

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-003 |
| Title | Terminology Management |
| Description | Define, maintain, and govern canonical glossary terms. Each term has exactly one authoritative definition. Support synonym tracking and cross-domain term resolution. |
| Primary Domain | Knowledge |
| Secondary Domains | None |
| Provider(s) | FRKC — glossary files in knowledge corpus |
| Consumer(s) | FRKP (publication), Risk Platform (formula documentation) |
| Implementation Evidence | FRKC glossary and terminology definitions; FRKP Terminology Standard (FRKP-TERM-100) |
| Maturity | Production — glossary exists in FRKC |
| Cross-Program Occurrence | 2 (FRKC, FRKP) |
| Overlap with Existing Contracts | CC-KNW-001 — covered as part of knowledge management |
| Overlap with Other Candidates | None |
| Validation Priority | P3 — Medium |

### CAP-KNW-004 — Domain Classification

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-004 |
| Title | Domain Classification |
| Description | Classify knowledge artifacts by risk domain (Operational Risk, Credit Risk, Market Risk, etc.). Enable domain-scoped queries and navigation. |
| Primary Domain | Knowledge |
| Secondary Domains | Publishing |
| Provider(s) | FRKC — domain metadata on knowledge items; FRKP — bundle domain scoping |
| Consumer(s) | FRKP (bundle organization), AI Platform (domain-scoped retrieval) |
| Implementation Evidence | FRKC domain fields on knowledge items; FRKP bundle domain scoping (Bundle-007 = Operational Risk); FRKP-DOC-100 domain indices |
| Maturity | Production |
| Cross-Program Occurrence | 2 (FRKC, FRKP) |
| Overlap with Existing Contracts | Covered by CC-KNW-001 metadata requirements |
| Overlap with Other Candidates | None |
| Validation Priority | P3 — Medium |

### CAP-KNW-005 — Knowledge Layering

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-005 |
| Title | Knowledge Layering |
| Description | Organize knowledge across a defined layer architecture (RL → KB → AN → FC → MF → IMP → ARCH). Each layer serves a distinct purpose in the knowledge lifecycle. |
| Primary Domain | Knowledge |
| Secondary Domains | Publishing |
| Provider(s) | FRKC — knowledge corpus organized by layer; FRKP — directory structure mirrors layers |
| Consumer(s) | FRKP (publication), AI Platform (layer-aware retrieval) |
| Implementation Evidence | FRKP directory structure (01-07 layers); FRKP-DOC-100 layer index; FRKC layer assignments on knowledge items |
| Maturity | Production |
| Cross-Program Occurrence | 2 (FRKC, FRKP) |
| Overlap with Existing Contracts | CC-KNW-001 describes knowledge layers conceptually |
| Overlap with Other Candidates | CAP-KNW-001 (Canonical Knowledge Storage) — items stored per layer |
| Validation Priority | P2 — High (FRKP-specific bias confirmed by PLAN-016; needs validation against non-FRKP implementations) |

### CAP-KNW-006 — Cross-Reference Linking

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-006 |
| Title | Cross-Reference Linking |
| Description | Create and maintain resolvable links between related knowledge artifacts. Support bidirectional reference resolution and link integrity validation. |
| Primary Domain | Knowledge |
| Secondary Domains | Publishing, Governance |
| Provider(s) | FRKC — cross-reference fields on knowledge objects; FRKP — cross-reference tables; Risk Platform — PLAN cross-references |
| Consumer(s) | All platforms consuming FRKC knowledge |
| Implementation Evidence | FRKC cross_references metadata field; FRKP navigation indices; Risk Platform PLAN cross-references |
| Maturity | Production |
| Cross-Program Occurrence | 3 (FRKC, FRKP, Risk Platform) |
| Overlap with Existing Contracts | CC-NAV-001 (Navigation Contract); FAEP-STD-004 (Navigation and Cross-Reference Standard) — capability is broader |
| Overlap with Other Candidates | CAP-PUB-004 (Navigation Index Management) — cross-references are part of navigation |
| Validation Priority | P1 — Critical |

### CAP-KNW-007 — Metadata Enforcement

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-007 |
| Title | Metadata Enforcement |
| Description | Define mandatory metadata schemas for knowledge objects. Validate compliance against metadata rules. Enforce schema evolution policies. |
| Primary Domain | Knowledge |
| Secondary Domains | Governance |
| Provider(s) | FRKC — 18-field mandatory metadata model; FRKP — document information tables |
| Consumer(s) | FRKP (publication), AI Platform (metadata-driven retrieval) |
| Implementation Evidence | FRKP-005 Section 7 — metadata model with 18 fields, 10 validation rules, 5 evolution rules; FRKP document information tables |
| Maturity | Specification complete; partial implementation in FRKC (metadata fields exist but automated validation not verified) |
| Cross-Program Occurrence | 2 (FRKC, FRKP) |
| Overlap with Existing Contracts | CC-MET-001 (Metadata Contract) — directly overlaps |
| Overlap with Other Candidates | None |
| Validation Priority | P3 — Medium (metadata model flagged as over-generalized in PLAN-016) |

### CAP-KNW-008 — Knowledge Versioning

| Field | Value |
| --- | --- |
| Capability ID | CAP-KNW-008 |
| Title | Knowledge Versioning |
| Description | Version every knowledge artifact using semantic versioning. Maintain version history. Support corpus-level version snapshots. Govern breaking changes. |
| Primary Domain | Knowledge |
| Secondary Domains | Governance |
| Provider(s) | FRKC — version fields on all knowledge objects; FRKP — VERSION file, CHANGELOG |
| Consumer(s) | FRKP (publication), Risk Platform (formula version references) |
| Implementation Evidence | FRKC version fields on all object types; FRKP VERSION file (0.1.0); CHANGELOG; FRKP-005 Section 13 version strategy |
| Maturity | Production — version tracking operational; automated compatibility checking deferred |
| Cross-Program Occurrence | 2 (FRKC, FRKP) |
| Overlap with Existing Contracts | CC-VER-001 (Version Contract) — directly overlaps |
| Overlap with Other Candidates | None |
| Validation Priority | P3 — Medium |

---

## 4.2 Publishing Domain

### CAP-PUB-001 — Evidence-Driven Publishing

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-001 |
| Title | Evidence-Driven Publishing Workflow |
| Description | Execute a standard workflow from evidence identification through knowledge publication. Each publication step requires evidence mapping before proceeding. |
| Primary Domain | Publishing |
| Secondary Domains | Knowledge, Governance |
| Provider(s) | FRKP — FRKP-FRKC-001 workflow; FRKC — evidence sources |
| Consumer(s) | FRKP bundle publications, downstream platforms consuming published bundles |
| Implementation Evidence | FRKP-FRKC-001 (Evidence-Driven Publishing Workflow); PLAN-005, PLAN-006 evidence mapping; Bundle-007 publication |
| Maturity | Production — validated through Bundle-007 |
| Cross-Program Occurrence | 1 (FRKP) |
| Overlap with Existing Contracts | CC-EVD-001 (Evidence Contract) — publishing workflow is an implementation of evidence contract |
| Overlap with Other Candidates | CAP-KNW-002 (Evidence Registration & Mapping) — publishing workflow consumes registered evidence |
| Validation Priority | P2 — High |

### CAP-PUB-002 — Bundle Lifecycle Management

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-002 |
| Title | Bundle Lifecycle Management |
| Description | Manage content bundles through a defined lifecycle: Planned → Boundary Review → Knowledge Review → Evidence Review → Publishing Review → Execution → Freeze → Release. |
| Primary Domain | Publishing |
| Secondary Domains | Governance |
| Provider(s) | FRKP — bundle process for Bundle-007 |
| Consumer(s) | FRKP downstream release consumers |
| Implementation Evidence | Bundle-007 lifecycle (PLAN-004 through PLAN-009); FRKP-DOC-100 bundle status tracking; FAEP-STD-002 Bundle Standard |
| Maturity | Production — Bundle-007 frozen |
| Cross-Program Occurrence | 1 (FRKP) |
| Overlap with Existing Contracts | CC-BUN-001 (Bundle Contract); FAEP-STD-002 (Bundle Standard) |
| Overlap with Other Candidates | CAP-EXE-006 (PLAN-based Execution) — alternative lifecycle model for Risk Platform |
| Validation Priority | P2 — High (PLAN-016 flagged Bundle vs. PLAN as overlapping governance models) |

### CAP-PUB-003 — Document Authoring & Publication

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-003 |
| Title | Document Authoring & Publication |
| Description | Create, review, approve, and publish structured documents. Support document lifecycle from draft through frozen. Maintain document registers and manifests. |
| Primary Domain | Publishing |
| Secondary Domains | Knowledge |
| Provider(s) | FRKP — all 7 layers (RL, KB, AN, FC, MF, IMP, ARCH); Risk Platform — documentation portal |
| Consumer(s) | Human readers, AI agents, downstream platforms |
| Implementation Evidence | FRKP document layers with templates, standards, navigation; Risk Platform docs/portal with 9 calculator standard docs |
| Maturity | Production |
| Cross-Program Occurrence | 2 (FRKP, Risk Platform) |
| Overlap with Existing Contracts | CC-DOC-001 (Document Contract); CC-DE-001 (Document Engine) |
| Overlap with Other Candidates | CAP-PUB-004 (Navigation Index Management) — documents require navigation for discoverability |
| Validation Priority | P2 — High |

### CAP-PUB-004 — Navigation Index Management

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-004 |
| Title | Navigation Index Management |
| Description | Create and maintain navigation structures, document indexes, cross-reference tables, and content maps. Enable hierarchical and semantic navigation. |
| Primary Domain | Publishing |
| Secondary Domains | Knowledge |
| Provider(s) | FRKP — FRKP-DOC-100 Master Document Index; directory-based navigation; cross-reference tables |
| Consumer(s) | All FRKP consumers, AI agents |
| Implementation Evidence | FRKP-DOC-100; directory hierarchy (01-13 layers); cross-reference indices |
| Maturity | Production |
| Cross-Program Occurrence | 1 (FRKP) |
| Overlap with Existing Contracts | CC-NAV-001 (Navigation Contract); FAEP-STD-004 |
| Overlap with Other Candidates | CAP-KNW-006 (Cross-Reference Linking) — navigation indices are a publishing concern; cross-references are a knowledge concern |
| Validation Priority | P3 — Medium |

### CAP-PUB-005 — AI Agent Orchestration

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-005 |
| Title | AI Agent Orchestration |
| Description | Deploy AI agents (Codex, ChatGPT) as task executors within the platform. Agents create, validate, review, and publish artifacts under human supervision. |
| Primary Domain | Publishing |
| Secondary Domains | AI-Ready |
| Provider(s) | FRKP — AI operating model with Codex and ChatGPT agents |
| Consumer(s) | FRKP governance, FRKC knowledge workers |
| Implementation Evidence | FRKP-002 (AI Operating Model); AI_SESSION_HANDOFF.md; MASTER_SESSION.md; BOOTSTRAP_CODEX.md; BOOTSTRAP_CHATGPT.md |
| Maturity | Production — actively used in FRKP workflow |
| Cross-Program Occurrence | 1 (FRKP) |
| Overlap with Existing Contracts | CC-AGT-001 (Agent Contract); CC-AAE-001 (AI Agent Engine) |
| Overlap with Other Candidates | CAP-PUB-006 (Session Handoff & Restoration) — agents require session management |
| Validation Priority | P2 — High |

### CAP-PUB-006 — Session Handoff & Restoration

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-006 |
| Title | Session Handoff & Restoration |
| Description | Preserve AI agent session state across interruptions. Enable session handoff between agents (Codex ↔ ChatGPT) and human reviewers. Support session restoration. |
| Primary Domain | Publishing |
| Secondary Domains | AI-Ready |
| Provider(s) | FRKP — session management system; Risk Platform — AI session management |
| Consumer(s) | AI agents, human reviewers |
| Implementation Evidence | FRKP AI_SESSION_HANDOFF.md, MASTER_SESSION.md; PROJECT_STATE.md; Risk Platform ai-session/ directory |
| Maturity | Production |
| Cross-Program Occurrence | 2 (FRKP, Risk Platform) |
| Overlap with Existing Contracts | CC-SES-001 (Session Contract) — directly overlaps |
| Overlap with Other Candidates | CAP-PUB-005 (AI Agent Orchestration) — sessions enable agent orchestration |
| Validation Priority | P2 — High |

### CAP-PUB-007 — Freeze Certification

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-007 |
| Title | Freeze Certification |
| Description | Certify artifacts as frozen with documented evidence baseline, deferred items, accepted risks, and governance approval. Enforce immutability of frozen artifacts. |
| Primary Domain | Publishing |
| Secondary Domains | Governance |
| Provider(s) | FRKP — Bundle-007 freeze certification; Risk Platform — V6.5 lockdown |
| Consumer(s) | Downstream platforms depending on frozen artifacts |
| Implementation Evidence | FRKP-FREEZE-001; PLAN-009 Bundle-007 Freeze Certification; Risk Platform V6.5 LOCKDOWN_REPORT |
| Maturity | Production |
| Cross-Program Occurrence | 2 (FRKP, Risk Platform) |
| Overlap with Existing Contracts | CC-REL-001 (Release Contract); FAEP-STD-006 (Release and Freeze Standard) |
| Overlap with Other Candidates | CAP-EXE-008 (Release Snapshot Management) — freeze is pre-release; release snapshot is post-freeze |
| Validation Priority | P2 — High |

### CAP-PUB-008 — Archive Management

| Field | Value |
| --- | --- |
| Capability ID | CAP-PUB-008 |
| Title | Archive Management |
| Description | Move superseded artifacts to permanent archive. Preserve version history. Maintain resolvable references to archived content. |
| Primary Domain | Publishing |
| Secondary Domains | Governance |
| Provider(s) | FRKP — 99_Archive/ directory |
| Consumer(s | FRKP governance, audit |
| Implementation Evidence | FRKP 99_Archive/ directory with superseded content |
| Maturity | Production |
| Cross-Program Occurrence | 1 (FRKP) |
| Overlap with Existing Contracts | Implicit in CC-REL-001 and FAEP-STD-006 |
| Overlap with Other Candidates | None |
| Validation Priority | P4 — Low |

---

## 4.3 Execution Domain

### CAP-EXE-001 — DSL Compilation Pipeline

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-001 |
| Title | DSL Compilation Pipeline |
| Description | Compile domain-specific formula language through pipeline stages: Lexer → Parser → AST → Semantic Validation → Optimization → Canonical Plan → Runtime Binding. |
| Primary Domain | Execution |
| Secondary Domains | None |
| Provider(s) | Risk Platform — formula compiler in core:core-analysis/calculator/compiler/ |
| Consumer(s) | Risk Platform runtime engine, formula governance |
| Implementation Evidence | PLAN-016 C-001, G-001; Risk Platform Lexer, Parser, AST, Optimizer, Canonical Plan stages; CompileRequest/CompiledFormula contracts |
| Maturity | Production — compiler is operational |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-FRM-001 (Formula Contract) — compiler pipeline extends beyond formula definition |
| Overlap with Other Candidates | CAP-EXE-004 (Content-Addressed Execution Plans) — compiler produces execution plans |
| Validation Priority | P1 — Critical (registered as FAEP-CAND-001) |

### CAP-EXE-002 — Deterministic Runtime Execution

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-002 |
| Title | Deterministic Runtime Execution |
| Description | Execute formulas deterministically: given same inputs and contract, produce identical outputs. Use content-addressed plan hashing (SHA-256), deterministic numeric precision (Decimal128, HALF_EVEN), and sandboxed execution. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — RuntimeCompiledPlan, SHA-256 hashing, Decimal128, HALF_EVEN rounding |
| Consumer(s) | Risk Platform analytics, downstream consumers |
| Implementation Evidence | PLAN-016 C-002, G-003; Risk Platform RuntimeCompiledPlan with SHA-256; numeric precision policy; determinism enforcement |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-RE-001 (Runtime Contract); PP-013 (Deterministic Processing Principle) |
| Overlap with Other Candidates | CAP-EXE-003 (Formula Governance Workflow) — determinism is enforced through governance; CAP-EXE-005 (Execution Mode Enforcement) — execution modes control determinism level |
| Validation Priority | P1 — Critical (registered as FAEP-CAND-003) |

### CAP-EXE-003 — Formula Governance Workflow

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-003 |
| Title | Formula Governance Workflow |
| Description | Manage formula lifecycle through defined states: DRAFT → ACTIVE → DEPRECATED → BLOCKED. Support promotion evidence, maker-checker approval, and governance audit. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — formula governance in application/formula; PromotionEvidence workflow |
| Consumer(s) | Risk Platform operators, downstream formula consumers |
| Implementation Evidence | PLAN-016 C-003; Risk Platform formula lifecycle states, PromotionEvidence entity, maker-checker workflow |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-GOV-001 (Governance Contract); CC-FRM-001 (Formula Contract) |
| Overlap with Other Candidates | CAP-EXE-009 (Evidence-Gated Promotion) — promotion evidence is part of this workflow |
| Validation Priority | P2 — High |

### CAP-EXE-004 — Content-Addressed Execution Plans

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-004 |
| Title | Content-Addressed Execution Plans |
| Description | Represent compiled formulas as content-addressed plans with opcode-based intermediate representation. Plans are hashed (SHA-256) for identity, caching, and replay verification. |
| Primary Domain | Execution |
| Secondary Domains | None |
| Provider(s) | Risk Platform — RuntimeCompiledPlan with opcodes (CONST_DECIMAL, READ_INPUT, ADD, etc.) |
| Consumer(s) | Risk Platform runtime, formula cache, replay system |
| Implementation Evidence | PLAN-016 G-002; Risk Platform RuntimeCompiledPlan, opcode IR, SHA-256 content addressing |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-RE-001 (Runtime Contract) — no execution plan format specified |
| Overlap with Other Candidates | CAP-EXE-001 (DSL Compilation Pipeline) — compiler produces execution plans |
| Validation Priority | P1 — Critical (registered as FAEP-CAND-002) |

### CAP-EXE-005 — Execution Mode Enforcement

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-005 |
| Title | Execution Mode Enforcement |
| Description | Execute formulas in distinct modes (PRODUCTION, REPLAY, SIMULATION, DEBUG) with mode-specific sandbox policies, determinism requirements, and governance gates. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — CalculationContext with execution mode; sandbox policy per mode |
| Consumer(s) | Risk Platform governance, formula developers, operators |
| Implementation Evidence | PLAN-016 G-007; Risk Platform PRODUCTION/REPLAY/SIMULATION/DEBUG modes; mode-specific determinism enforcement |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-RE-001 (Runtime Contract) — no execution mode specification |
| Overlap with Other Candidates | CAP-EXE-002 (Deterministic Runtime Execution) — modes control determinism level; FAEP-CAND-007 (Execution Mode Contract) |
| Validation Priority | P1 — Critical (overlaps with FAEP-CAND-003/FAEP-CAND-007) |

### CAP-EXE-006 — Policy-First Governance Guard

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-006 |
| Title | Policy-First Governance Guard |
| Description | Intercept runtime execution with chain-of-responsibility policy guards. Enforce lifecycle policies, safety policies, and governance rules before execution proceeds. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — CoreLifecycleExecutionPolicy, GovernanceGuard, CoreRuntimeSafetyPolicy |
| Consumer(s) | Risk Platform runtime, governance operators |
| Implementation Evidence | PLAN-016 G-008, C-019; Risk Platform guardian classes with policy chain pattern |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-GOV-001 (Governance Contract) — guardian pattern is more specific |
| Overlap with Other Candidates | CAP-EXE-005 (Execution Mode Enforcement) — guardians enforce mode-specific policies |
| Validation Priority | P2 — High (registered as FAEP-CAND-008) |

### CAP-EXE-007 — PLAN-based Execution

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-007 |
| Title | PLAN-based Execution |
| Description | Execute work through a structured PLAN system with unique IDs, boundary reviews, completion gates, status tracking, and cross-PLAN dependency management. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — 306+ PLANs with PLAN-NNN system; FRKP — planning system with PLAN_INDEX.md |
| Consumer(s) | All Risk Platform capabilities; FRKP planning governance |
| Implementation Evidence | Risk Platform PLAN-NNN execution model; FRKP PLAN_INDEX.md, active.md, CURRENT_WORK.md, next-session.md, 03_history/ |
| Maturity | Production in both platforms |
| Cross-Program Occurrence | 2 (Risk Platform, FRKP) |
| Overlap with Existing Contracts | FAEP-STD-002 (Bundle Standard) — PLAN lifecycle vs. Bundle lifecycle; FAEP-CAND-009 (PLAN Execution Contract) |
| Overlap with Other Candidates | CAP-PUB-002 (Bundle Lifecycle Management) — alternative governance model |
| Validation Priority | P1 — Critical (FRKP + Risk Platform both use PLAN-based models) |

### CAP-EXE-008 — Architecture Enforcement

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-008 |
| Title | Architecture Enforcement |
| Description | Define and enforce architecture rules (layer access, package dependency, module boundaries) through automated tests. Prevent architecture violations at build time. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — ArchUnit tests in core module |
| Consumer(s) | Risk Platform development, architecture governance |
| Implementation Evidence | PLAN-016 G-010, C-009; Risk Platform ArchUnit test suite enforcing package boundaries |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | No FAEP architecture enforcement contract exists |
| Overlap with Other Candidates | See FAEP-CAND-010 (Architecture Enforcement Contract) |
| Validation Priority | P2 — High |

### CAP-EXE-009 — Release Snapshot Management

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-009 |
| Title | Release Snapshot Management |
| Description | Create versioned release snapshots of formulas and governance artifacts. Support snapshot comparison, rollback, and deployment. |
| Primary Domain | Execution |
| Secondary Domains | Publishing |
| Provider(s) | Risk Platform — FormulaReleaseSnapshot system |
| Consumer(s) | Risk Platform deployment, formula consumers |
| Implementation Evidence | PLAN-016 C-004; Risk Platform release snapshots, versioned deployment |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-REL-001 (Release Contract); CC-VER-001 (Version Contract) |
| Overlap with Other Candidates | CAP-PUB-007 (Freeze Certification) — freeze is a pre-release artifact state |
| Validation Priority | P2 — High |

### CAP-EXE-010 — Evidence-Gated Promotion

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-010 |
| Title | Evidence-Gated Promotion |
| Description | Gate formula promotion (e.g., DRAFT → ACTIVE) on evidence submission and review. Require maker-checker approval for state transitions. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — PromotionEvidence entity, maker-checker workflow |
| Consumer(s) | Risk Platform governance, formula operators |
| Implementation Evidence | PLAN-016 C-005, G-004; Risk Platform PromotionEvidence, evidence-gated promotion workflow |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-EVD-001 (Evidence Contract) — overlaps partially |
| Overlap with Other Candidates | CAP-KNW-002 (Evidence Registration & Mapping) — Risk Platform uses evidence for formula governance |
| Validation Priority | P2 — High |

### CAP-EXE-011 — Dependency Impact Analysis

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-011 |
| Title | Dependency Impact Analysis |
| Description | Analyze direct and transitive dependencies between formulas, functions, and variables. Provide impact analysis for formula changes. |
| Primary Domain | Execution |
| Secondary Domains | None |
| Provider(s) | Risk Platform — dependency graph analysis API |
| Consumer(s) | Risk Platform governance, formula developers |
| Implementation Evidence | PLAN-016 C-006; Risk Platform direct + transitive impact analysis |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | Not covered by existing Core Contracts |
| Overlap with Other Candidates | CAP-EXE-012 (Variable Resolution) — dependency analysis includes variable dependencies |
| Validation Priority | P3 — Medium |

### CAP-EXE-012 — Variable Resolution

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-012 |
| Title | Variable Resolution |
| Description | Resolve formula variables across multiple dimensions (context, scenario, time). Support multi-context variable lookup with configurable resolution strategy. |
| Primary Domain | Execution |
| Secondary Domains | None |
| Provider(s) | Risk Platform — VariableResolver, AnalysisVariableResolver |
| Consumer(s) | Risk Platform formula compiler and runtime |
| Implementation Evidence | PLAN-016 C-010; Risk Platform VariableResolver with multi-dimensional resolution |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | Not covered by existing Core Contracts |
| Overlap with Other Candidates | CAP-EXE-013 (Variable Codec Serialization) — resolution depends on codec |
| Validation Priority | P3 — Medium |

### CAP-EXE-013 — Variable Codec Serialization

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-013 |
| Title | Variable Codec Serialization |
| Description | Serialize and deserialize variables using a codec system supporting modern, legacy, and composite codecs. Enable cross-version variable compatibility. |
| Primary Domain | Execution |
| Secondary Domains | None |
| Provider(s) | Risk Platform — VariableCodec SPI, Modern/Legacy/Composite codecs |
| Consumer(s) | Risk Platform variable storage, cross-engine data exchange |
| Implementation Evidence | PLAN-016 G-006, C-018; Risk Platform VariableCodec system |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | Not covered by existing Core Contracts |
| Overlap with Other Candidates | CAP-EXE-012 (Variable Resolution) — codec serialization enables resolution |
| Validation Priority | P3 — Medium |

### CAP-EXE-014 — Numeric Precision Governance

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-014 |
| Title | Numeric Precision Governance |
| Description | Define and enforce numeric precision policy across all computations. Specify decimal type, rounding mode, and precision rules. |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — Decimal128, HALF_EVEN rounding, precision policy |
| Consumer(s) | Risk Platform runtime, formula developers |
| Implementation Evidence | PLAN-016 C-017; Risk Platform Decimal128 usage, HALF_EVEN rounding mode |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | Recommended principle PP-013 (Deterministic Processing) — precision contributes to determinism |
| Overlap with Other Candidates | CAP-EXE-002 (Deterministic Runtime Execution) — precision is part of determinism |
| Validation Priority | P3 — Medium |

### CAP-EXE-015 — Operator Review & Governance Metrics

| Field | Value |
| --- | --- |
| Capability ID | CAP-EXE-015 |
| Title | Operator Review & Governance Metrics |
| Description | Provide operator review queue for formula governance actions. Track governance metrics (review time, approval rate, rejection reasons). |
| Primary Domain | Execution |
| Secondary Domains | Governance |
| Provider(s) | Risk Platform — operator review queue, governance metrics dashboard |
| Consumer(s) | Risk Platform operators, governance auditors |
| Implementation Evidence | PLAN-016 C-020; Risk Platform operator review queue, governance metrics |
| Maturity | Production |
| Cross-Program Occurrence | 1 (Risk Platform) |
| Overlap with Existing Contracts | CC-GOV-001 (Governance Contract) — operations monitoring |
| Overlap with Other Candidates | CAP-EXE-003 (Formula Governance Workflow) — review queue is part of governance workflow |
| Validation Priority | P4 — Low |

---

## 4.4 Governance Domain

### CAP-GOV-001 — PLAN Governance Model

| Field | Value |
| --- | --- |
| Capability ID | CAP-GOV-001 |
| Title | PLAN Governance Model |
| Description | Govern work through an integrated PLAN system: PLAN_INDEX, active plans, completed history, status tracking, and PLAN-based execution. |
| Primary Domain | Governance |
| Secondary Domains | Execution |
| Provider(s) | FRKP — PLAN_INDEX.md, active.md, CURRENT_WORK.md, next-session.md, 03_history/; Risk Platform — 306+ PLANs |
| Consumer(s) | All FRKP and Risk Platform governance |
| Implementation Evidence | FRKP planning infrastructure; Risk Platform PLAN-NNN system (306+ plans) |
| Maturity | Production in both platforms |
| Cross-Program Occurrence | 2 (FRKP, Risk Platform) |
| Overlap with Existing Contracts | FAEP-CAND-009 (PLAN Execution Contract) — specifically registered as Candidate |
| Overlap with Other Candidates | CAP-PUB-002 (Bundle Lifecycle Management) — alternative governance approach |
| Validation Priority | P1 — Critical |

### CAP-GOV-002 — Architecture Decision Records

| Field | Value |
| --- | --- |
| Capability ID | CAP-GOV-002 |
| Title | Architecture Decision Records |
| Description | Document architecture decisions with context, decision, consequences, and alternatives. Maintain decision registry with lifecycle states. |
| Primary Domain | Governance |
| Secondary Domains | None |
| Provider(s) | FAEP — FAEP-ADR-000; FRKP — architecture decisions in plans; Risk Platform — ADR-001 |
| Consumer(s) | All FAEP programs, architecture governance |
| Implementation Evidence | FAEP-ADR-000 (33 decisions); FRKP plan documents with AD sections; Risk Platform ADR-001 |
| Maturity | Production |
| Cross-Program Occurrence | 3 (FAEP, FRKP, Risk Platform) |
| Overlap with Existing Contracts | FAEP-STD-005 (Architecture Decision Standard) — capability is broader than standard |
| Overlap with Other Candidates | None |
| Validation Priority | P2 — High |

### CAP-GOV-003 — Contract Lifecycle Governance

| Field | Value |
| --- | --- |
| Capability ID | CAP-GOV-003 |
| Title | Contract Lifecycle Governance |
| Description | Govern platform contracts through a defined lifecycle: Idea → Proposal → Candidate → Validated → Core → Deprecated → Retired. Maintain Candidate Contract Registry. |
| Primary Domain | Governance |
| Secondary Domains | None |
| Provider(s) | FAEP — FAEP-CONTRACT-000, FAEP-CONTRACT-001 |
| Consumer(s) | All FAEP programs |
| Implementation Evidence | FAEP-CONTRACT-000 lifecycle; FAEP-CONTRACT-001 with 10 Candidate Contracts |
| Maturity | Specification complete |
| Cross-Program Occurrence | 1 (FAEP) |
| Overlap with Existing Contracts | The contract lifecycle IS the governance for Core Contracts |
| Overlap with Other Candidates | CAP-GOV-005 (Reference Implementation Validation) — validation is prerequisite for contract promotion |
| Validation Priority | P2 — High |

### CAP-GOV-004 — Foundation Freeze & Evolution

| Field | Value |
| --- | --- |
| Capability ID | CAP-GOV-004 |
| Title | Foundation Freeze & Evolution |
| Description | Declare Foundation freeze with immutable baseline. Govern Foundation evolution through three-layer architecture. Manage Foundation versioning. |
| Primary Domain | Governance |
| Secondary Domains | None |
| Provider(s) | FAEP — FAEP-FOUNDATION-000, FAEP-FOUNDATION-001, FAEP-FOUNDATION-002 |
| Consumer(s) | All FAEP programs |
| Implementation Evidence | FAEP-FOUNDATION-000 (43 frozen artifacts); FAEP-FOUNDATION-001 (three-layer architecture); FAEP-FOUNDATION-002 (versioning policy) |
| Maturity | Specification complete |
| Cross-Program Occurrence | 1 (FAEP) |
| Overlap with Existing Contracts | The Foundation governance governs all other contracts |
| Overlap with Other Candidates | CAP-GOV-005 (Reference Implementation Validation) — validation drives Foundation evolution |
| Validation Priority | P3 — Medium (governance is in place; priority is on capability validation) |

### CAP-GOV-005 — Reference Implementation Validation

| Field | Value |
| --- | --- |
| Capability ID | CAP-GOV-005 |
| Title | Reference Implementation Validation |
| Description | Evaluate Reference Implementations against FAEP Core Contracts, Standards, and Governance. Assign maturity levels. Discover Candidate Contracts. |
| Primary Domain | Governance |
| Secondary Domains | None |
| Provider(s) | FAEP — FAEP-VALIDATION-000, FAEP-VALIDATION-001 |
| Consumer(s) | All current and future Reference Implementations |
| Implementation Evidence | FAEP-VALIDATION-000 (13 categories, 5 levels); FAEP-VALIDATION-001 (scoring model); FRKP validated at Level 2; Risk Platform validated at Level 1 |
| Maturity | Specification complete; initial validation performed |
| Cross-Program Occurrence | 1 (FAEP) |
| Overlap with Existing Contracts | Validation framework governs Reference Implementation evaluation |
| Overlap with Other Candidates | CAP-GOV-003 (Contract Lifecycle Governance) — validation is prerequisite for contract promotion |
| Validation Priority | P3 — Medium |

---

## 4.5 AI-Ready Domain

### CAP-AI-001 — AI Collaboration Operating Model

| Field | Value |
| --- | --- |
| Capability ID | CAP-AI-001 |
| Title | AI Collaboration Operating Model |
| Description | Coordinate AI-assisted architecture, engineering, authoring, editorial, review, governance, knowledge, and publishing work by stable capability rather than by provider-specific product. |
| Primary Domain | AI-Ready |
| Secondary Domains | Governance, Publishing, Knowledge |
| Provider(s) | FRKP — AI collaboration pattern observed across repository audit, editorial correction, and editorial contract extraction; example providers include GPT, Codex, and OpenCode |
| Consumer(s) | FAEP governance, FRKP Publishing, future Risk Platform, IB Project, and Business Platform workflows |
| Implementation Evidence | PLAN-024 Repository Audit; PLAN-025 Critical Editorial Corrections; PLAN-026 Editorial Contract Framework; FAEP-AI-000 Candidate registration |
| Maturity | Candidate — validated in FRKP Publishing only; not Core |
| Cross-Program Occurrence | 1 (FRKP Publishing) |
| Overlap with Existing Contracts | CC-AGT-001 and CC-AAE-001 concepts overlap at agent level, but this candidate is capability-routing guidance rather than a Core Contract |
| Overlap with Other Candidates | CAP-PUB-005 (AI Agent Orchestration); CAP-PUB-006 (Session Handoff & Restoration); CAP-GOV-001 (PLAN Governance Model) |
| Validation Priority | P2 — High |

---
# 5. Provider / Consumer Mapping

| Capability | Provider(s) | Consumer(s) |
| --- | --- | --- |
| CAP-KNW-001 — Canonical Knowledge Storage | FRKC | FRKP, Risk Platform, AI Platform |
| CAP-KNW-002 — Evidence Registration & Mapping | FRKC, FRKP, Risk Platform | FRKP, Risk Platform |
| CAP-KNW-003 — Terminology Management | FRKC | FRKP |
| CAP-KNW-004 — Domain Classification | FRKC, FRKP | FRKP, AI Platform |
| CAP-KNW-005 — Knowledge Layering | FRKC, FRKP | FRKP, AI Platform |
| CAP-KNW-006 — Cross-Reference Linking | FRKC, FRKP, Risk Platform | All platforms |
| CAP-KNW-007 — Metadata Enforcement | FRKC | FRKP, AI Platform |
| CAP-KNW-008 — Knowledge Versioning | FRKC | FRKP, Risk Platform |
| CAP-PUB-001 — Evidence-Driven Publishing | FRKP | Bundle consumers |
| CAP-PUB-002 — Bundle Lifecycle Management | FRKP | Release consumers |
| CAP-PUB-003 — Document Authoring & Publication | FRKP, Risk Platform | Human readers, AI agents |
| CAP-PUB-004 — Navigation Index Management | FRKP | All FRKP consumers |
| CAP-PUB-005 — AI Agent Orchestration | FRKP | FRKP governance |
| CAP-PUB-006 — Session Handoff & Restoration | FRKP, Risk Platform | AI agents, human reviewers |
| CAP-PUB-007 — Freeze Certification | FRKP, Risk Platform | Downstream platforms |
| CAP-PUB-008 — Archive Management | FRKP | Audit |
| CAP-EXE-001 — DSL Compilation Pipeline | Risk Platform | Risk Platform runtime |
| CAP-EXE-002 — Deterministic Runtime Execution | Risk Platform | Analytics consumers |
| CAP-EXE-003 — Formula Governance Workflow | Risk Platform | Operators, consumers |
| CAP-EXE-004 — Content-Addressed Execution Plans | Risk Platform | Runtime, cache, replay |
| CAP-EXE-005 — Execution Mode Enforcement | Risk Platform | Governance, developers |
| CAP-EXE-006 — Policy-First Governance Guard | Risk Platform | Runtime, governance |
| CAP-EXE-007 — PLAN-based Execution | Risk Platform, FRKP | All platform governance |
| CAP-EXE-008 — Architecture Enforcement | Risk Platform | Development, governance |
| CAP-EXE-009 — Release Snapshot Management | Risk Platform | Deployment, consumers |
| CAP-EXE-010 — Evidence-Gated Promotion | Risk Platform | Governance, operators |
| CAP-EXE-011 — Dependency Impact Analysis | Risk Platform | Governance, developers |
| CAP-EXE-012 — Variable Resolution | Risk Platform | Compiler, runtime |
| CAP-EXE-013 — Variable Codec Serialization | Risk Platform | Storage, data exchange |
| CAP-EXE-014 — Numeric Precision Governance | Risk Platform | Runtime, developers |
| CAP-EXE-015 — Operator Review & Governance Metrics | Risk Platform | Operators, auditors |
| CAP-GOV-001 — PLAN Governance Model | FRKP, Risk Platform | All platform governance |
| CAP-GOV-002 — Architecture Decision Records | FAEP, FRKP, Risk Platform | All programs |
| CAP-GOV-003 — Contract Lifecycle Governance | FAEP | All programs |
| CAP-GOV-004 — Foundation Freeze & Evolution | FAEP | All programs |
| CAP-GOV-005 — Reference Implementation Validation | FAEP | All implementations |
| CAP-AI-001 — AI Collaboration Operating Model | FRKP Publishing; example AI providers are replaceable | FAEP governance, FRKP, Risk Platform, IB Project, Business Platforms |

---

# 6. Capability Overlap Analysis

## 6.1 Overlapping Capabilities

| Capability A | Capability B | Overlap Type | Resolution |
| --- | --- | --- | --- |
| CAP-KNW-002 (Evidence Registration) | CAP-EXE-010 (Evidence-Gated Promotion) | Partial — both manage evidence but in different domains (knowledge vs. formula governance) | Keep separate; cross-reference |
| CAP-PUB-002 (Bundle Lifecycle) | CAP-EXE-007 (PLAN-based Execution) | Hierarchical — both govern work through lifecycles (Bundle vs. PLAN) | Keep separate; PLAN-016 confirmed both are valid FAEP models |
| CAP-KNW-005 (Knowledge Layering) | CAP-KNW-001 (Canonical Storage) | Hierarchical — layering is an organizing principle for stored items | Keep; layers add structure to storage |
| CAP-EXE-002 (Deterministic Execution) | CAP-EXE-005 (Execution Mode) | Hierarchical — execution modes control determinism level | Potential merge target; see FAEP-CAND-003/FAEP-CAND-007 overlap |
| CAP-EXE-001 (DSL Compilation) | CAP-EXE-004 (Execution Plans) | Sequential — compiler produces execution plans | Keep separate; distinct stages of same pipeline |
| CAP-PUB-001 (Evidence-Driven Publishing) | CAP-KNW-002 (Evidence Registration) | Sequential — publishing consumes registered evidence | Keep separate; producer/consumer relationship |
| CAP-KNW-006 (Cross-Reference Linking) | CAP-PUB-004 (Navigation Index) | Hierarchical — cross-references are building blocks of navigation | Keep separate; knowledge vs. publishing concern |
| CAP-GOV-001 (PLAN Governance) | CAP-PUB-002 (Bundle Lifecycle) | Overlapping — both are governance models for work execution | Keep separate; see PLAN-016 recommendation to distinguish Bundle vs. PLAN |
| CAP-PUB-005 (AI Agent Orchestration) | CAP-PUB-006 (Session Handoff) | Hierarchical — session management is prerequisite for agent orchestration | Keep separate |
| CAP-EXE-006 (Policy-First Guard) | CAP-EXE-005 (Execution Mode) | Hierarchical — guards enforce mode-specific policies | Keep separate |

## 6.2 Duplicate Candidates Identified

| Duplicate Group | Capabilities | Recommended Action |
| --- | --- | --- |
| Determinism + Execution Mode | FAEP-CAND-003 and FAEP-CAND-007 | Merge; align with CAP-EXE-002 and CAP-EXE-005 |
| Bundle vs. PLAN Lifecycle | CAP-PUB-002 vs. CAP-EXE-007 | Keep distinct until future PLAN determines whether to unify |

## 6.3 Candidates Related to Existing Contracts

| Candidate Capability | Related Core Contract | Relationship |
| --- | --- | --- |
| CAP-KNW-001 (Canonical Storage) | CC-KNW-001 | Broader implementation than contract |
| CAP-KNW-002 (Evidence Registration) | CC-EVD-001 | Broader implementation than contract |
| CAP-KNW-006 (Cross-Reference Linking) | CC-NAV-001 | Broader implementation than contract |
| CAP-KNW-007 (Metadata Enforcement) | CC-MET-001 | Direct implementation |
| CAP-KNW-008 (Knowledge Versioning) | CC-VER-001 | Direct implementation |
| CAP-PUB-003 (Document Authoring) | CC-DOC-001 | Broader implementation than contract |
| CAP-PUB-006 (Session Handoff) | CC-SES-001 | Direct implementation |
| CAP-PUB-005 (AI Orchestration) | CC-AGT-001 | Broader implementation than contract |
| CAP-EXE-001 (DSL Compilation) | CC-FRM-001 | Extends beyond contract scope |
| CAP-EXE-002 (Deterministic Execution) | CC-RE-001 | Extends beyond contract scope |
| CAP-EXE-007 (PLAN-based Execution) | None | New pattern not covered by existing contracts |
| CAP-EXE-008 (Architecture Enforcement) | None | New pattern not covered by existing contracts |

---

# 7. Discovery vs. Speculation Analysis

## 7.1 Confirmed Discovery — Implemented

The following capabilities are confirmed as discovered from actual implementations:

| Count | Capabilities | Source |
| --- | --- | --- |
| 8 | CAP-KNW-001 through CAP-KNW-008 | FRKC knowledge corpus |
| 8 | CAP-PUB-001 through CAP-PUB-008 | FRKP platform |
| 14 | CAP-EXE-001 through CAP-EXE-015 | Risk Platform codebase |
| 5 | CAP-GOV-001 through CAP-GOV-005 | FAEP governance |
| 1 | CAP-AI-001 | FRKP Publishing |
| — | — | — |
| 36 | **Total Candidate Capabilities** | |

## 7.2 Backlog — Speculative / Future

The following capabilities are described in Foundation or architecture documents but are not yet demonstrated by a Reference Implementation. They are recorded in the Backlog, not as Candidates.

| BL-ID | Title | Domain | Source | Reason for Backlog |
| --- | --- | --- | --- | --- |
| BL-CAP-001 | RAG Corpus Preparation | AI-Ready | FRKP-005 | Future Phase 3; not yet implemented |
| BL-CAP-002 | Multi-Strategy Semantic Retrieval | AI-Ready | FRKP-005 | Future Phase 3; not yet implemented |
| BL-CAP-003 | Weighted Context Assembly | AI-Ready | FRKP-005 | Future Phase 3; not yet implemented |
| BL-CAP-004 | Machine-Readable Citation Model | AI-Ready | FRKP-005 | Future Phase 3; not yet implemented |
| BL-CAP-005 | Knowledge Graph Query Engine | AI-Ready | FRKP-005 | Deferred to Phase 2; not yet implemented |
| BL-CAP-006 | Shadow Mode Migration | Execution | Risk Platform | Single implementation; speculative cross-program value |
| BL-CAP-007 | Bitemporal Data Support | Execution | Risk Platform | Single implementation; narrow scope |
| BL-CAP-008 | Universal Variable Codec Standard | Execution | Risk Platform | Single implementation; FAEP deferred |
| BL-CAP-009 | Knowledge Federation Protocol | Knowledge | FRKP-005 | Future Phase 4; not yet implemented |

---

# 8. Recommended Validation Priorities

## P1 — Critical (Validate Next)

| Priority | Capabilities | Rationale |
| --- | --- | --- |
| P1 | CAP-EXE-001 (DSL Compilation), CAP-EXE-002 (Deterministic Execution), CAP-EXE-004 (Content-Addressed Plans), CAP-EXE-005 (Execution Mode) | Risk Platform execution capabilities with highest gap-to-contract ratio. Already registered as FAEP-CAND-001/002/003/007. Cross-program validation by a non-Risk execution engine (e.g., FRKP or IB Project) is required for Core promotion. |
| P1 | CAP-EXE-007 (PLAN-based Execution), CAP-GOV-001 (PLAN Governance Model) | Demonstrated in 2+ implementations (FRKP + Risk Platform). Highest multi-program evidence. |
| P1 | CAP-KNW-002 (Evidence Registration), CAP-KNW-006 (Cross-Reference Linking) | Demonstrated in 3 implementations (FRKC, FRKP, Risk Platform). Most mature cross-program capability set. |

## P2 — High

| Priority | Capabilities | Rationale |
| --- | --- | --- |
| P2 | CAP-KNW-001, CAP-KNW-005 | FRKC-specific; need validation from non-FRKC knowledge platform |
| P2 | CAP-PUB-001 through CAP-PUB-003, CAP-PUB-005 through CAP-PUB-007 | FRKP-specific; need validation from alternative publishing platform |
| P2 | CAP-AI-001 | FRKP Publishing pattern; needs validation through Risk Platform, IB Project, and another Business Platform before Core consideration |
| P2 | CAP-EXE-003, CAP-EXE-006, CAP-EXE-008, CAP-EXE-009, CAP-EXE-010 | Risk Platform execution governance; validation by second execution platform |
| P2 | CAP-GOV-002, CAP-GOV-003 | Widely implemented but already well-governed |

## P3 — Medium

| Priority | Capabilities | Rationale |
| --- | --- | --- |
| P3 | CAP-KNW-003, CAP-KNW-004, CAP-KNW-007, CAP-KNW-008 | Knowledge domain; lower cross-program urgency |
| P3 | CAP-PUB-004 | Publishing-specific; lower cross-program urgency |
| P3 | CAP-EXE-011, CAP-EXE-012, CAP-EXE-013, CAP-EXE-014 | Risk Platform-specific; lower cross-program urgency |
| P3 | CAP-GOV-004, CAP-GOV-005 | Governance already in place; validation methodology exists |

## P4 — Low

| Priority | Capabilities | Rationale |
| --- | --- | --- |
| P4 | CAP-PUB-008 (Archive Management), CAP-EXE-015 (Operator Review) | Narrow scope; low cross-program relevance |

---

# 9. Recommended PLAN-021

PLAN-021 should focus on **Cross-Program Candidate Validation and Capability-Based Contract Evolution.**

## PLAN-021 Scope

| Item | Description |
| --- | --- |
| Title | Cross-Program Candidate Validation |
| Objective | Validate the P1-priority Candidate Capabilities against a non-origin Reference Implementation. Specifically: (a) validate Risk Platform execution capabilities against FRKP or IB Project context, and (b) validate FRKP publishing capabilities against Risk Platform or another publishing platform. |
| Source | FAEP-CAP-001 P1-priority capabilities; FAEP-CAND-001 through FAEP-CAND-010; CAP-EXE-001/002/004/005/007; CAP-KNW-002/006; CAP-GOV-001 |
| Outputs | Cross-program validation report per capability; updated FAEP-CAP-001 validation status; recommendation for which capabilities are ready for Capability Standard creation; updated FAEP-CONTRACT-001 promotion recommendations. |
| Priority | High — directly unblocks the next phase of Foundation evolution. |

## Extended Backlog

| Future Plan | Focus | Trigger |
| --- | --- | --- |
| PLAN-022 | Capability Standard Pilot | After P1 capabilities validated by 2+ programs |
| PLAN-023 | IB Project Bootstrap (if not started) | After capability validation framework proven |

---

# 10. Preservation Statement

FAEP-CAP-001 did not modify:
- FAEP Foundation v1.0 frozen artifacts.
- FAEP Core Contracts (CC-*).
- FAEP Standards (FAEP-STD-000 through FAEP-STD-006).
- FAEP Specifications (FRKP-003, FRKP-004, FRKP-005).
- FAEP Governance documents (FAEP-000, FAEP-001, FAEP-002).
- FAEP ADR Registry (FAEP-ADR-000).
- FAEP Contract Governance (FAEP-CONTRACT-000, FAEP-CONTRACT-001).
- FAEP Validation Framework (FAEP-VALIDATION-000, FAEP-VALIDATION-001).
- FAEP Foundation Governance (FAEP-FOUNDATION-000, FAEP-FOUNDATION-001, FAEP-FOUNDATION-002).
- Bundle structure or repository layout.

FAEP-CAP-001 did not perform:
- Implementation.
- Code.
- Repository migration.
- Commits.
- Releases.

---

# 11. Backlog Registry

## BL-CAP-001 — RAG Corpus Preparation

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-001 |
| Title | RAG Corpus Preparation |
| Domain | AI-Ready |
| Description | Chunk canonical knowledge into semantically coherent chunks. Embed chunks into vector space. Index by keyword, metadata, ontology, and embedding. |
| Source Document | FRKP-005 Section 11.2 |
| Reason for Backlog | Specified in architecture but not yet implemented in FRKC (Phase 3 future) |

## BL-CAP-002 — Multi-Strategy Semantic Retrieval

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-002 |
| Title | Multi-Strategy Semantic Retrieval |
| Domain | AI-Ready |
| Description | Retrieve knowledge using combined strategies: semantic (embedding), keyword, graph traversal, and metadata filtering. |
| Source Document | FRKP-005 Section 11.1 |
| Reason for Backlog | Specified in architecture but not yet implemented in FRKC (Phase 3 future) |

## BL-CAP-003 — Weighted Context Assembly

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-003 |
| Title | Weighted Context Assembly |
| Domain | AI-Ready |
| Description | Assemble retrieved chunks into structured context blocks. Use 6-factor weighted ranking for chunk selection and ordering. |
| Source Document | FRKP-005 Section 11.3, 11.4 |
| Reason for Backlog | Specified in architecture but not yet implemented in FRKC (Phase 3 future) |

## BL-CAP-004 — Machine-Readable Citation Model

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-004 |
| Title | Machine-Readable Citation Model |
| Domain | AI-Ready |
| Description | Generate machine-parseable citations with FRKC ID, version, evidence ID, and certification status. Preserve citations through AI transformation. |
| Source Document | FRKP-005 Section 11.5 |
| Reason for Backlog | Specified in architecture but not yet implemented in FRKC (Phase 3 future) |

## BL-CAP-005 — Knowledge Graph Query Engine

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-005 |
| Title | Knowledge Graph Query Engine |
| Domain | AI-Ready |
| Description | Query the knowledge graph with typed edge traversal, path finding, and version-aware filtering. |
| Source Document | FRKP-005 Section 9.2 |
| Reason for Backlog | Deferred to Phase 2; file-based graph not yet operational |

## BL-CAP-006 — Shadow Mode Migration

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-006 |
| Title | Shadow Mode Migration |
| Domain | Execution |
| Description | Run new engine implementation alongside legacy implementation. Compare results. Gate rollout on divergence thresholds. |
| Source Document | PLAN-016 G-004 |
| Reason for Backlog | Single implementation (Risk Platform); speculative cross-program value; narrow engine upgrade scope |

## BL-CAP-007 — Bitemporal Data Support

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-007 |
| Title | Bitemporal Data Support |
| Domain | Execution |
| Description | Support valid time and transaction time semantics for formula variables. Enable temporal query and audit replay. |
| Source Document | PLAN-016 G-005 |
| Reason for Backlog | Single implementation (Risk Platform); low priority in PLAN-016; narrow scope |

## BL-CAP-008 — Universal Variable Codec Standard

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-008 |
| Title | Universal Variable Codec Standard |
| Domain | Execution |
| Description | Define reusable serialization for variables shared across engines or stored across compatibility generations. |
| Source Document | PLAN-016 G-006 |
| Reason for Backlog | Single implementation (Risk Platform); FAEP deferred to backlog; not yet urgent |

## BL-CAP-009 — Knowledge Federation Protocol

| Field | Value |
| --- | --- |
| BL-ID | BL-CAP-009 |
| Title | Knowledge Federation Protocol |
| Domain | Knowledge |
| Description | Enable multi-corpus knowledge graph federation. Support cross-corpus queries, distributed ontology, and federated evidence chains. |
| Source Document | FRKP-005 Section 14.1 |
| Reason for Backlog | Future Phase 4; not yet implemented; requires multi-platform coordination |

---

# 12. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Candidate Capability Registry created by PLAN-020 |
