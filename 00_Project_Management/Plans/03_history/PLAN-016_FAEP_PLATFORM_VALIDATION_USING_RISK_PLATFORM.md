# PLAN-016 — FAEP Platform Validation Using Risk Platform

## Plan Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-016 |
| Title | FAEP Platform Validation Using Risk Platform |
| Status | Completed |
| Category | Platform Validation |
| Owner | FAEP Architecture Board |
| Risk Repository | https://github.com/kbgkim/risk |
| FRKP Repository | https://github.com/kbgkim/frpk |
| Created | 2026-06-28 |
| Completed | 2026-06-28 |

---

## Executive Summary

This PLAN validates the FAEP Platform against the existing production-grade Risk Platform (`github.com/kbgkim/risk`). The Risk Platform is an operational Spring Boot application with 306+ completed plans, a next-generation formula execution engine, IB simulation engines, formula governance lifecycle, ArchUnit-enforced architecture, and a mature plan-based execution model.

**Key Finding:** The Risk Platform is significantly more mature than FAEP currently recognizes. FAEP describes Program-300 (Risk Platform) as "Defined — Architecture specified in FRKP-003 and FRKP-004; no dedicated repository or implementation." In reality, the Risk Platform already has a production repository, a formula engine with compiler/sandbox/governance, ArchUnit tests enforcing package boundaries, a maker-checker governance workflow, and a comprehensive PLAN-based execution model that mirrors FAEP's own plan architecture.

**Verdict: CONDITIONAL GO — Minor FAEP refinements recommended.**

FAEP Core contracts and standards are sufficient to describe the Risk Platform architecture. However, FAEP must evolve in specific areas to correctly reflect the Risk Platform's existing maturity. Five refinements are recommended (3 High, 2 Medium priority).

---

## 1. Program Mapping

### Risk Platform → FAEP Program-300

| FAEP Element | Risk Platform Mapping | Status |
| --- | --- | --- |
| **Program-300 Purpose** | Implement computational engines — Formula, Risk Analytics, Runtime | ✅ Supported |
| **Owner** | Risk Platform Lead (existing lead, PLAN-based governance) | ✅ Supported |
| **Current Maturity** | FAEP states "Defined — no repository." Actual: **Production-grade repository with 306+ completed plans, V6.5 lockdown, next-gen formula engine operational** | ⚠️ FAEP underestimates maturity |
| **Target Maturity** | FAEP targets "Operational — dedicated repository." Actual: Already operational beyond FAEP's target | ✅ Exceeds target |
| **Dependencies** | Program-000 (Core Contracts), Program-100 (FRKC knowledge), Program-200 (FRKP publishing) | ✅ Supported |
| **Repository** | `github.com/kbgkim/risk` — Gradle multi-module (11 submodules, Spring Boot 3.3.0, Java 17) | ✅ Supported |

### FAEP Engine Mapping to Risk Platform

| FAEP Engine | Risk Platform Implementation | Maturity |
| --- | --- | --- |
| Formula Engine (FE-001) | `core:core-analysis/calculator` — Lexer, Parser, AST, Compiler, FunctionRegistry, VariableResolver | Production |
| Risk Analytics Engine (RAE-001) | `engine:risk-engine` — IB Waterfall/Pricing/BookBuilding; `engine:raroc-engine` — RAROC | Production |
| Runtime Engine (RE-001) | `calculator/runtime/` — Sandbox execution, GovernanceGuard, CalculationContext, ExecutionTrace, RuntimeCompiledPlan | Production |
| Governance Engine (GE-001) | `application/formula` — Lifecycle states, promotion evidence, release snapshots, maker-checker | Production |
| Evidence Engine (EE-001) | `domain/formula/PromotionEvidence` — Evidence-gated promotion workflow | Partial |
| Document Engine (DE-001) | `docs/` — Documentation portal, 9 calculator standard docs, ADR, architecture docs | Production |
| AI Agent Engine (AAE-001) | `Project_Management/ai-session/` — AI session management, bootstrap, active, invariants, workflow modes | Production |
| Bootstrap Engine (BE-001) | `Project_Management/plan/` — PLAN-based execution, templates in `docs/standard/` | Production |

### Dependency Analysis

| Dependency | Direction | FAEP Claim | Risk Reality |
| --- | --- | --- | --- |
| Risk → FRKC/FRKP Knowledge | Consumes | FRKP provides formula documentation | Risk has its own docs, no FRKC dependency |
| Risk → FAEP Core | Conforms to contracts | Core Contracts govern engines | Risk has its own contracts (CompileRequest, RuntimeCompiledPlan, etc.) |
| Risk → Publishing | Publishes via FRKP | FRKP publishes bundles | Risk publishes its own docs independently |

---

## 2. Capability Mapping

### Risk Platform Capabilities → FAEP Engines

| # | Risk Capability | FAEP Engine | Mapped | Notes |
| --- | --- | --- | :---: | --- |
| C-001 | Formula DSL Compilation (Lexer → Parser → AST → Optimization → Canonical Plan) | Formula Engine (FE-001) | ✅ | Direct mapping — Risk compiler is a production-grade implementation |
| C-002 | Deterministic Execution (SHA-256 plan hash, Decimal128, HALF_EVEN) | Runtime Engine (RE-001) | ✅ | FAEP Principle PP-013 (Deterministic Processing) validated |
| C-003 | Formula Governance Lifecycle (DRAFT/ACTIVE/DEPRECATED/BLOCKED) | Governance Engine (GE-001) | ✅ | Mature maker-checker workflow |
| C-004 | Release Snapshots & Version Management | Release Engine (RLE-001) | ✅ | FormulaReleaseSnapshot, versioned deployment |
| C-005 | Promotion Evidence Gate (maker-checker) | Evidence Engine (EE-001) | ✅ | PromotionEvidence entity, evidence-gated rollout |
| C-006 | Dependency Graph Analysis (direct + transitive impact) | Formula Engine (FE-001) | ✅ | Impact analysis API |
| C-007 | IB Simulation (Waterfall, Pricing, BookBuilding) | Risk Analytics Engine (RAE-001) | ✅ | Domain-specific engines |
| C-008 | RAROC Extension Point | Risk Analytics Engine (RAE-001) | ✅ | Plugin-based engine extension |
| C-009 | ArchUnit Architecture Tests | Governance Engine (GE-001) | ✅ | Package boundary enforcement |
| C-010 | Variable Resolution (multi-dimensional, bitemporal) | Formula Engine (FE-001) | ✅ | VariableResolver, AnalysisVariableResolver |
| C-011 | Execution Trace & Audit (ExecutionTrace, governance audit) | Runtime Engine (RE-001) | ✅ | Traceability chain validated |
| C-012 | REST API (Formula workspace, notebook, auth) | Document Engine (DE-001) | ✅ | Interface layer |
| C-013 | AI Session Management (bootstrap, active, invariants) | AI Agent Engine (AAE-001) | ✅ | Pattern matches FAEP Session Contract |
| C-014 | PLAN-based Execution Model (306+ plans) | Bootstrap Engine (BE-001) | ✅ | FAEP's own plan architecture exists in Risk |
| C-015 | Architecture Decision Records (ADR-001) | Governance Engine (GE-001) | ✅ | ADR standard validated |
| C-016 | Documentation Standards (9 calculator spec docs) | Document Engine (DE-001) | ✅ | Structured documentation |
| C-017 | Numeric Precision Policy (Decimal128, HALF_EVEN) | Formula Engine (FE-001) | ✅ | Precision standard validated |
| C-018 | Codec System (Modern/Legacy/Composite variable codec) | Formula Engine (FE-001) | ✅ | Variable persistence |
| C-019 | Governance Guardians (CoreLifecycleExecutionPolicy, GovernanceGuard, CoreRuntimeSafetyPolicy) | Runtime Engine (RE-001) | ✅ | Policy-first execution |
| C-020 | Operator Review Queue & Governance Metrics | Governance Engine (GE-001) | ✅ | Operational governance |

**Coverage: 20/20 capabilities mapped.** No Risk Platform capability is outside FAEP engine scope.

---

## 3. Contract Validation

### 3.1 Knowledge Contract (CC-KNW-001)

| Aspect | FAEP Contract | Risk Platform | Status |
| --- | --- | --- | --- |
| Knowledge documents | Structured, cross-referenced, versioned | Docs portal with 9 calculator specs, architecture docs, standards | ⚠️ Supported (no formal Knowledge Engine layer separation) |
| Knowledge layers | RL → KB → AN → FC → MF → IMP → ARCH | Risk has docs/ standards/ but not FRKP-style layering | ⚠️ Partially Supported |
| Cross-references | Resolvable links between knowledge artifacts | Docs have cross-references but not formalized | ⚠️ Partially Supported |
| Metadata | Mandatory 18 fields | Documents have metadata (Status, Last Reviewed, Source of Truth) but not 18-field formal schema | ⚠️ Partially Supported |
| Versioning | Semantic versioning | Documentation uses Current/Reference/Archived/Superseded status, not semver | ⚠️ Partially Supported |

**Verdict: Partially Supported.** Risk Platform does not use FRKP-style knowledge layering or the 18-field metadata model. It has its own documentation conventions. FAEP Knowledge Contract is more prescriptive than Risk requires.

### 3.2 Formula Contract (CC-FRM-001)

| Aspect | FAEP Contract | Risk Platform | Status |
| --- | --- | --- | --- |
| Formula definition | Symbol standardization, parameters | Formula DSL with variables, operators, functions; FunctionMetadata with determinism/side-effect/sandbox levels | ✅ Supported |
| Formula derivation | Mathematical derivation documented | Formula specification in calculator standard docs | ✅ Supported |
| Formula catalog | FC documents in FRKP | FormulaGroup entity in domain; FormulaDefinition repository | ✅ Supported |
| Executable formulas | FormulaCompiler → CompiledFormula | Production compiler producing CompiledFormula with SHA-256 hash | ✅ Supported |
| Symbol standards | FRKP-SYM-001 | Risk has convention but no formal symbol standard document | ⚠️ Partially Supported |
| Traceability | Every formula references evidence | PromotionEvidence links formulas to governance evidence | ✅ Supported |

**Verdict: Supported.** The Risk Platform's formula engine exceeds FAEP Formula Contract expectations in many areas (compiler architecture, determinism enforcement, function registry SPI).

### 3.3 Evidence Contract (CC-EVD-001)

| Aspect | FAEP Contract | Risk Platform | Status |
| --- | --- | --- | --- |
| Evidence IDs | Stable evidence identifier | PromotionEvidence has entity but no formal Evidence ID standard | ⚠️ Partially Supported |
| Evidence registration | Registered with metadata | Evidence exists in governance workflow but not as first-class knowledge artifact | ⚠️ Partially Supported |
| Evidence mapping | Mapped to publications | Promotion evidence gates formula rollout | ✅ Supported |
| Evidence certification | Certified for governance use | Evidence reviewed in maker-checker workflow | ✅ Supported |
| Evidence lifecycle | Identified → Registered → Mapped → Certified → Superseded → Archived | PromotionEvidence follows workflow-based lifecycle, not the formal FAEP 8-stage model | ⚠️ Partially Supported |
| Evidence registers | Published as release artifacts | Not formalized as standalone register | ❌ Missing |

**Verdict: Partially Supported.** Risk Platform has evidence concepts in governance workflow but lacks the formal evidence identification, registration, and register publishing that FAEP Evidence Contract specifies.

### 3.4 Runtime Contract (CC-RE-001)

| Aspect | FAEP Contract | Risk Platform | Status |
| --- | --- | --- | --- |
| Execution environment | Batch processing, real-time calculation | RuntimeCompiledPlan, opcode-based IR, sandboxed execution | ✅ Supported |
| Inputs | Executable formulas, data, config | CompileRequest, CalculationContext with environment fingerprint | ✅ Supported |
| Outputs | Results, execution logs, metrics | CalculationResult, ExecutionTrace, governance audit events | ✅ Supported |
| Batch processing | Defined | Batch execution via calculator runtime | ✅ Supported |
| Real-time calculation | Defined | API-triggered evaluation | ✅ Supported |
| Execution management | Management API | GovernanceGuard, CoreLifecycleExecutionPolicy, CoreRuntimeSafetyPolicy | ✅ Supported |
| Data pipelining | Data flow between stages | Compiler pipeline (Lexer → Parser → AST → Optimizer → Canonical Plan → Runtime Binding → Execution) | ✅ Supported |
| Resource allocation | Bounded resources | Sandbox with determinism levels (PRODUCTION/REPLAY/SIMULATION/DEBUG) | ✅ Supported |

**Verdict: Supported.** The Risk Platform's runtime engine is production-grade and fully supports the FAEP Runtime Contract. It exceeds expectations with its opcode-based IR, SHA-256 plan hashing, and execution mode system.

### 3.5 Governance Contract (CC-GOV-001)

| Aspect | FAEP Contract | Risk Platform | Status |
| --- | --- | --- | --- |
| Governance rules | Standards, policies, processes | Operating rules, calculator standards, architecture tests | ✅ Supported |
| Standards | Document ID, architecture, bundle, document standards | Document status system, PLAN-based execution, ArchUnit tests | ✅ Supported |
| Certification | Freeze, release certificates | Release snapshots, promotion evidence, PLAN completion | ✅ Supported |
| Compliance checking | Automated compliance | ArchUnit architecture tests, governance guardians, compiler shadow mode | ✅ Supported |
| Review management | Review lifecycle | Operator review queue, governance metrics, PLAN boundary reviews | ✅ Supported |
| Policy enforcement | Automated enforcement | CoreLifecycleExecutionPolicy, GovernanceGuard at runtime | ✅ Supported |

**Verdict: Supported.** Risk Platform governance is mature and operational. The FAEP Governance Contract maps well to Risk's existing governance model.

### 3.6 Plugin Contract (CC-PLG-001)

| Aspect | FAEP Contract | Risk Platform | Status |
| --- | --- | --- | --- |
| Plugin registration | Plugin registry | DomainFunctionProvider SPI, FunctionRegistry — function-level plugin model | ✅ Supported |
| Plugin isolation | No cascading failures | Module isolation via Gradle multi-module; core does not know web/DB | ✅ Supported |
| Plugin lifecycle | Specified → Registered → Resolved → Deployed → Active → Updated → Decommissioned | Engine lifecycle matches but not formalized as plugin lifecycle | ⚠️ Partially Supported |
| Plugin dependencies | Declared dependencies | Gradle module dependencies; FunctionRegistry dependency resolution | ✅ Supported |
| Plugin versioning | Semantic versioning | Formula versioning via snapshots; module-level versioning not formalized | ⚠️ Partially Supported |
| Plugin metadata | 11 mandatory fields | No formal plugin metadata schema | ❌ Missing |

**Verdict: Partially Supported.** Risk Platform has plugin patterns (DomainFunctionProvider SPI, RAROC engine extension point) but does not formalize them under a FAEP-style Plugin Contract. The function-level SPI model is effective but narrower than FAEP's engine-level plugin model.

### Contract Validation Summary

| Contract | Status |
| --- | --- |
| Knowledge Contract (CC-KNW-001) | ⚠️ Partially Supported — Risk uses own conventions, not FAEP layering |
| Formula Contract (CC-FRM-001) | ✅ Supported — Risk exceeds expectations |
| Evidence Contract (CC-EVD-001) | ⚠️ Partially Supported — Formal evidence ID/register missing |
| Runtime Contract (CC-RE-001) | ✅ Supported — Production-grade, exceeds expectations |
| Governance Contract (CC-GOV-001) | ✅ Supported — Mature governance model |
| Plugin Contract (CC-PLG-001) | ⚠️ Partially Supported — SPI exists but not formalized |

---

## 4. Standard Validation

### 4.1 Document Identification Standard (FAEP-STD-001)

| Requirement | Risk Platform | Status |
| --- | --- | --- |
| Unique IDs within namespace | PLAN-NNN, ADR-NNN, document status system | ✅ Supported |
| Stability — IDs not renamed | PLAN IDs are immutable | ✅ Supported |
| Readability — prefix identifies type | PLAN, ADR prefixes | ✅ Supported |
| Machine-readability | Consistent ASCII tokens | ✅ Supported |
| Backward compatibility | Legacy IDs preserved | ✅ Supported |

**Verdict: Supported.** Risk Platform's PLAN-NNN and ADR-NNN identification system is consistent with FAEP-STD-001.

### 4.2 Bundle Standard (FAEP-STD-002)

| Requirement | Risk Platform | Status |
| --- | --- | --- |
| Bundle lifecycle | Planned → Boundary Review → ... → Freeze → Release | Risk uses PLAN-based lifecycle with boundary reviews and completion gate | ⚠️ Partially Supported |
| Bundle metadata | Owner, scope, dependencies | PLAN metadata includes Domain tags | ⚠️ Partially Supported |
| Bundle freeze | Immutable baseline with certificate | Risk has V6.5 LOCKDOWN REPORT, release snapshots | ⚠️ Partially Supported |
| Bundle review | Review gates | PLAN boundary reviews, operator review queues | ✅ Supported |

**Verdict: Partially Supported.** Risk Platform does not use "Bundle" terminology. It uses PLAN-based execution with similar lifecycle stages but different naming. The FAEP Bundle Standard is FRKP-derived and does not fully describe Risk's execution model.

### 4.3 Evidence Standard (FAEP-STD-003)

| Requirement | Risk Platform | Status |
| --- | --- | --- |
| Evidence lifecycle | 8-stage model | PromotionEvidence follows workflow lifecycle, not 8-stage model | ⚠️ Partially Supported |
| Evidence metadata | 10 mandatory fields | PromotionEvidence has some fields, not full 10-field schema | ⚠️ Partially Supported |
| Traceability | Evidence to artifact mapping | Promotion evidence gates formula rollout | ✅ Supported |
| Integrity | Evidence verification | Maker-checker workflow provides integrity | ✅ Supported |
| Versioning | Semantic versioning | Not formalized for evidence | ❌ Missing |

**Verdict: Partially Supported.** Evidence concepts exist but are not formalized to FAEP Evidence Standard level.

### 4.4 Navigation and Cross-Reference Standard (FAEP-STD-004)

| Requirement | Risk Platform | Status |
| --- | --- | --- |
| Navigation structure | Document hierarchy and indexes | docs/README.md, PLAN_INDEX.md, document status system | ✅ Supported |
| Cross-references | Resolvable links | PLAN cross-references, ADR links, Source of Truth hierarchy | ✅ Supported |
| Semantic links | Knowledge relationships | Not formalized as semantic graph | ❌ Missing |
| Machine-readable navigation | AI-agent processable | Document structure is consistent, AI session management exists | ✅ Supported |

**Verdict: Supported.** Risk Platform has good navigation and cross-reference conventions that align with FAEP-STD-004.

### 4.5 Architecture Decision Standard (FAEP-STD-005)

| Requirement | Risk Platform | Status |
| --- | --- | --- |
| ADR format | Context → Decision → Consequences | ADR-001 follows this format | ✅ Supported |
| ADR numbering | Sequential | ADR-NNN pattern | ✅ Supported |
| ADR lifecycle | Active/Superseded/Archived | ADR-001 is Current | ✅ Supported |
| ADR traceability | Links to standards/specs | ADR-001 links to regulatory compliance, legacy fallback policy | ✅ Supported |

**Verdict: Supported.** Risk Platform's ADR-001 demonstrates FAEP-STD-005 compliance.

### 4.6 Release and Freeze Standard (FAEP-STD-006)

| Requirement | Risk Platform | Status |
| --- | --- | --- |
| Release lifecycle | Planned → Scope Locked → Readiness Assessed → RC → Validated → Released → Certified → Archived | Formula release snapshots, V6.5 lockdown, PLAN completion gate | ⚠️ Partially Supported |
| Freeze lifecycle | Freeze Requested → Gate Review → Frozen → Correction Window → Baseline → Superseded | V6.5 LOCKDOWN_REPORT.md, PLAN completion = implicit freeze | ⚠️ Partially Supported |
| Release candidate | Candidate package | FormulaReleaseSnapshot serves as RC | ✅ Supported |
| Acceptance criteria | Defined per release | Plan acceptance criteria in boundary reviews | ✅ Supported |

**Verdict: Partially Supported.** Risk Platform has release and freeze concepts but uses different terminology. V6.5 lockdown and PLAN completion serve similar purposes.

### Standard Validation Summary

| Standard | Status |
| --- | --- |
| FAEP-STD-001 (Document ID) | ✅ Supported |
| FAEP-STD-002 (Bundle) | ⚠️ Partially Supported — Risk uses PLANs, not Bundles |
| FAEP-STD-003 (Evidence) | ⚠️ Partially Supported — Informal evidence model |
| FAEP-STD-004 (Navigation) | ✅ Supported |
| FAEP-STD-005 (ADR) | ✅ Supported |
| FAEP-STD-006 (Release/Freeze) | ⚠️ Partially Supported — Different terminology |

---

## 5. Dependency Validation

### Risk Platform Dependency on FAEP Components

| FAEP Component | Risk Dependency | Evidence |
| --- | --- | --- |
| FRKC (Knowledge Corpus) | **None** — Risk has its own docs | Risk docs do not reference FRKC; docs are co-located in risk repository |
| FRKP (Publishing Platform) | **None** — Risk publishes independently | Risk has its own documentation portal, changelog, release process |
| FAEP Core (Contracts) | **None** — Risk has its own contracts | Risk defines its own FormulaCompiler, RuntimeCompiledPlan, CalculationContext interfaces |
| FAEP Governance (Standards) | **None** — Risk has its own standards | Risk operating rules, calculator standards, PLAN execution model |
| FAEP Evidence (FRKC evidence) | **None** — Risk has PromotionEvidence | Risk evidence is governance-internal, not FRKC-sourced |

### Dependency Conclusion

**The Risk Platform is fully isolated.** It does not depend on FRKC, FRKP, FAEP Core, or any FAEP-defined component. It is a self-contained production platform with its own:
- Formula engine contracts
- Governance model
- Documentation standards
- Evidence workflow
- Architecture tests
- Release process

**Implication for FAEP:** FAEP's Program-300 dependency chain (Program-000 → Program-100 → Program-200 → Program-300) assumes Risk consumes FRKC knowledge and FRKP publications. This is incorrect for the current Risk Platform. Risk has evolved independently and does not consume any FAEP-defined artifact.

### Dependency Mapping to FAEP Programs

| Program | FAEP Assumption | Risk Reality | Gap |
| --- | --- | --- | --- |
| Program-000 (Core) | Risk conforms to Core Contracts | Risk has its own contracts, not FAEP-defined | ⚠️ Contracts not shared |
| Program-100 (FRKC) | Risk consumes FRKC knowledge | Risk has own knowledge base | ❌ No knowledge dependency |
| Program-200 (FRKP) | FRKP publishes for Risk | Risk publishes independently | ❌ No publishing dependency |
| Program-300 (Risk) | Risk consumes from 100 & 200 | Risk is self-contained | ❌ Independent operation |
| Program-400 (AI) | AI automates Risk workflows | Risk has its own AI session management | ✅ Independent, compatible |
| Program-500 (Business) | Business consumes Risk analytics | IB simulation exists within Risk | ✅ Value delivery exists |

---

## 6. Capability Gap Analysis

### Capabilities Risk Requires but FAEP Does Not Define

| # | Capability | Risk Implementation | FAEP Gap | Priority |
| --- | --- | --- | --- | --- |
| G-001 | **DSL Compiler Pipeline** — Lexer → Parser → AST → Optimization → Canonical Plan → Runtime Binding | Production compiler in `core:core-analysis/calculator/compiler/` | FAEP Formula Contract specifies formula definition but not the compiler pipeline architecture | High |
| G-002 | **Content-Addressed Execution Plans** — SHA-256 hashed, opcode-based intermediate representation | `RuntimeCompiledPlan` with opcodes (CONST_DECIMAL, READ_INPUT, ADD, etc.) | FAEP Runtime Contract does not specify execution plan format or content addressing | High |
| G-003 | **Determinism Levels** — PURE / CONTROLLED / NON_DETERMINISTIC with sandbox enforcement by execution mode | FunctionMetadata determinism level, execution mode enforcement | FAEP mentions deterministic processing (PP-013) but does not define determinism levels or sandbox modes | High |
| G-004 | **Shadow Mode — Legacy/Modern Compiler Comparison** | Compiler shadow mode for adoption guard | FAEP does not define migration patterns for engine upgrades | Medium |
| G-005 | **Bitemporal Data Support** — valid_time, transaction_time for variable resolution | Variable resolution with bitemporal queries | FAEP does not address temporal data patterns | Low |
| G-006 | **Universal Variable Codec** — Modern/Legacy/Composite serialization | VariableCodec SPI with codec selection | FAEP does not define data serialization contracts | Low |
| G-007 | **Execution Mode System** — PRODUCTION / REPLAY / SIMULATION / DEBUG | CalculationContext with execution mode, sandbox policy per mode | FAEP Runtime Contract does not define execution modes | Medium |
| G-008 | **Governance Guardians Architecture** — Policy-first execution with chain-of-responsibility | CoreLifecycleExecutionPolicy, GovernanceGuard, CoreRuntimeSafetyPolicy | FAEP Governance Contract mentions enforcement but not the guardian pattern | Medium |
| G-009 | **PLAN-based Execution Model** — 300+ completed plans as governance primitive | PLAN-NNN system with boundary reviews, completion gates | FAEP uses PLANs internally but does not standardize PLAN-based execution as a platform primitive | High |
| G-010 | **ArchUnit Architecture Enforcement** — Automated layer/package/dependency rules | ArchUnit tests in core module | FAEP does not define architecture testing standards | Medium |

### Candidate FAEP Enhancements (from Gaps)

| Enhancement | Source Gap | Description | Priority |
| --- | --- | --- | --- |
| **CC-FRM-002 — Compiler Contract** | G-001 | Define compiler pipeline contract: input expression → lexer → parser → AST → semantic validation → optimization → canonical plan | High |
| **CC-RE-002 — Execution Plan Contract** | G-002 | Define execution plan format, content addressing, opcode IR, plan hashing | High |
| **CC-RE-003 — Execution Mode Contract** | G-007 | Define execution modes, sandbox levels, determinism tiers | High |
| **CC-GOV-002 — Architecture Test Standard** | G-010 | Define FAEP-wide architecture testing conventions using ArchUnit or equivalent | Medium |
| **CC-GOV-003 — PLAN Execution Standard** | G-009 | Standardize PLAN-based execution as a reusable FAEP governance primitive | Medium |
| **FAEP-STD-007 — Compiler Standard** | G-001/G-004 | Define compiler migration patterns, shadow mode, feature flags | Medium |

---

## 7. Over-Generalization Review

### FAEP Features Evaluated Against Risk Platform Needs

| # | Feature | Assessment | Recommendation | Rationale |
| --- | --- | --- | --- | --- |
| OG-001 | **18-Field Metadata Model (FRKC)** | Over-generalized | **Simplify** | Risk Platform does not need 18-field metadata. It uses a simpler document status system (Current/Reference/Archived/Superseded). FAEP should define a minimal baseline (5-7 fields) with optional extension. |
| OG-002 | **6-Layer Knowledge Architecture (RL→KB→AN→FC→MF→IMP→ARCH)** | Over-generalized | **Simplify** | This is FRKP-specific. Risk Platform does not use this layering. FAEP should classify this as FRKP Reference Implementation pattern, not FAEP Core requirement. |
| OG-003 | **8-Stage Evidence Lifecycle** | Over-generalized | **Simplify** | Risk Platform's PromotionEvidence uses 4 stages (DRAFT→PENDING→APPROVED→REJECTED). The 8-stage FAEP model is FRKP-derived. FAEP should define a minimal evidence lifecycle (4-5 stages) with extension for knowledge platforms. |
| OG-004 | **16-Engine Platform Model** | Appropriate | **Keep** | Risk Platform maps to 10 of 16 engines naturally. The remaining engines (Search, Metadata, Version, Workflow, Plugin, Bootstrap) are appropriate for platform-level specification. No simplification needed. |
| OG-005 | **15 Core Contracts** | Appropriate | **Keep** | Risk Platform validates 6 of 15 contracts directly. Remaining contracts are essential for platform completeness. |
| OG-006 | **Plugin Engine with Registry** | Premature | **Move to Backlog** | Risk Platform uses SPI/function-level plugin (DomainFunctionProvider) rather than engine-level plugin registry. FAEP Plugin Engine with formal registry is not needed for 12-24 months. |
| OG-007 | **Workflow Engine** | Premature | **Move to Backlog** | Risk Platform uses PLAN-based workflow. Formal Workflow Engine adds overhead without benefit. Revisit when 3+ platforms need workflow coordination. |
| OG-008 | **Search Engine** | Premature | **Move to Backlog** | Risk Platform uses file system navigation. Formal Search Engine is premature. Revisit at Phase 4 (multi-repository). |
| OG-009 | **AI Agent Engine Reference Implementation** | Premature | **Move to Backlog** | Risk Platform has AI session management but no agent orchestration engine. FAEP agent patterns are sufficient for now. |
| OG-010 | **Bundle Standard for All Platforms** | Over-generalized | **Simplify** | Risk Platform does not use bundles. FAEP should distinguish between: (a) Bundle lifecycle for knowledge platforms (FRKP-style) and (b) PLAN lifecycle for engineering platforms (Risk-style). Both are valid FAEP execution models. |
| OG-011 | **Knowledge Graph with 6-Hop Traversal** | Premature | **Move to Backlog** | Risk Platform does not use formal knowledge graph. Graph capabilities are FRKC-specific. Revisit when 3+ knowledge-consuming platforms exist. |
| OG-012 | **Machine-Readable Citations** | Premature | **Move to Backlog** | Risk Platform citations are governance-internal. Formal citation model is premature. | 

### Simplification Summary

| Action | Count | Items |
| --- | --- | --- |
| **Keep** | 3 | OG-004 (16 Engines), OG-005 (15 Contracts), OG-009 (AI Agent patterns — keep abstract) |
| **Simplify** | 4 | OG-001 (Metadata), OG-002 (Knowledge Layers), OG-003 (Evidence Lifecycle), OG-010 (Bundle vs. PLAN) |
| **Move to Backlog** | 5 | OG-006 (Plugin Registry), OG-007 (Workflow Engine), OG-008 (Search Engine), OG-011 (Knowledge Graph), OG-012 (Citations) |

---

## 8. Architecture Validation

### Is FAEP Simple Enough to Be Practical?

| Criterion | Assessment | Comment |
| --- | --- | --- |
| **Risk Platform can be described using FAEP concepts** | ✅ Yes | All 20 Risk capabilities map to FAEP engines |
| **Risk Platform Governance fits FAEP model** | ✅ Yes | PLAN-based execution, maker-checker, boundary reviews all align |
| **FAEP contracts are implementable** | ✅ Yes | 6 of 15 contracts validated against production code |
| **FAEP over-specifies for Risk** | ⚠️ Partially | Knowledge layering, evidence lifecycle, bundle standard are FRKP-specific |
| **FAEP under-specifies for Risk** | ✅ Yes | Compiler pipeline, execution plans, determinism modes, guardian patterns are missing |
| **FAEP dependency chain is incorrect** | ❌ No | Risk is fully isolated — does not consume FRKC or FRKP |
| **FAEP terminology matches Risk** | ⚠️ Partially | Risk uses PLANs, not Bundles; PromotionEvidence, not Evidence Registry |
| **16-engine model is workable** | ✅ Yes | Risk maps to 10 engines naturally |
| **FAEP governance is actionable** | ✅ Yes | PLAN-based execution, ADRs, architecture tests all work |

### Architecture Verdict

FAEP is **mostly practical** but has two significant issues:

1. **FRKP-Centric Bias** — FAEP standards and contracts are heavily influenced by FRKP's knowledge-publishing model. The Risk Platform reveals that computational engines need different patterns (compiler pipelines, execution plans, determinism modes) that FAEP does not yet define.

2. **Dependency Chain Error** — FAEP assumes Risk Platform consumes FRKC knowledge and FRKP publications. The Risk Platform is fully self-contained. FAEP must support both dependent and independent platform models.

---

## 9. Recommendations

### High Priority

| # | Recommendation | Area | Rationale | Target |
| --- | --- | --- | --- | --- |
| R-001 | **Add Compiler Pipeline Contract (CC-FRM-002)** | Formula Contract | Risk Platform's compiler architecture (Lexer→Parser→AST→Optimizer→Canonical Plan) is a production-proven pattern that FAEP must support | PLAN-017 |
| R-002 | **Add Execution Plan & Content Addressing Contract (CC-RE-002)** | Runtime Contract | Risk Platform's RuntimeCompiledPlan with SHA-256 hashing, opcode IR, and versioned schema is a critical pattern | PLAN-017 |
| R-003 | **Add Determinism & Execution Mode Contract (CC-RE-003)** | Runtime Contract | Risk Platform's PURE/CONTROLLED/NON_DETERMINISTIC levels and PRODUCTION/REPLAY/SIMULATION/DEBUG modes are essential for computational integrity | PLAN-017 |

### Medium Priority

| # | Recommendation | Area | Rationale | Target |
| --- | --- | --- | --- | --- |
| R-004 | **Distinguish Bundle vs. PLAN Execution Models** | Governance Standard | FAEP-STD-002 assumes bundle lifecycle. Risk uses PLAN lifecycle. FAEP should define both patterns as valid execution models. | PLAN-018 |
| R-005 | **Add Architecture Test Standard** | Governance Standard | Risk Platform's ArchUnit tests are a best practice that FAEP should standardize. | PLAN-018 |
| R-006 | **Correct Program-300 Maturity Assessment** | Program Roadmap | Update FAEP-001 to reflect Risk Platform's actual maturity (Operational, not Defined) | Immediate |
| R-007 | **Simplify Metadata & Evidence Standards to Minimal Baseline** | Standards | Reduce 18-field metadata to 5-7 field minimum; reduce 8-stage evidence lifecycle to 4-5 stages. Add extension mechanism. | PLAN-018 |
| R-008 | **Add PLAN Execution Standard** | Governance Standard | Formalize Risk Platform's PLAN-NNN system as a reusable FAEP governance primitive | PLAN-018 |

### Low Priority

| # | Recommendation | Area | Rationale | Target |
| --- | --- | --- | --- | --- |
| R-009 | **Move Plugin Registry, Workflow Engine, Search Engine, Knowledge Graph to Backlog** | Core Specification | Premature for 12-24 months | Backlog |
| R-010 | **Simplify 18-Field Metadata to 5-7 Field Baseline** | Knowledge Standard | Risk does not need 18 fields | Backlog |

---

## Backlog Candidates

| ID | Candidate | Source | Trigger |
| --- | --- | --- | --- |
| BC-001 | Plugin Registry Reference Implementation | OG-006 | 3+ plugins active across platforms |
| BC-002 | Formal Workflow Engine Specification | OG-007 | 3+ platforms needing coordinated workflows |
| BC-003 | Search Engine Reference Implementation | OG-008 | Multi-repository search required |
| BC-004 | Knowledge Graph Formal Implementation | OG-011 | 3+ knowledge-consuming platforms |
| BC-005 | Machine-Readable Citation Model | OG-012 | Automated cross-repository evidence resolution |
| BC-006 | Bitemporal Data Contract | G-005 | Temporal data patterns needed |
| BC-007 | Universal Codec Standard | G-006 | Cross-engine data serialization needed |

---

## Recommended FAEP Changes

| Change | Area | Priority | Description |
| --- | --- | --- | --- |
| **FAEP-001 Update** | Program Roadmap | High | Correct Risk Platform maturity from "Defined" to "Operational" |
| **CC-FRM-002 New** | Formula Contract | High | Compiler Pipeline Contract |
| **CC-RE-002 New** | Runtime Contract | High | Execution Plan & Content Addressing Contract |
| **CC-RE-003 New** | Runtime Contract | High | Determinism & Execution Mode Contract |
| **FAEP-STD-002 Revision** | Bundle Standard | Medium | Add PLAN execution model as alternative to Bundle lifecycle |
| **FAEP-STD-003 Revision** | Evidence Standard | Medium | Simplify to minimal baseline with extension |
| **FAEP-STD-007 New** | Governance Standard | Medium | Architecture Test Standard |
| **FAEP-STD-008 New** | Governance Standard | Medium | PLAN Execution Standard |
| **FRKP-004 Revision** | Core Specification | Medium | Reclassify FRKP-specific patterns (knowledge layering, 18-field metadata) as Reference Implementation, not Core |

---

## Recommended Risk Platform Changes

| Change | Area | Priority | Description |
| --- | --- | --- | --- |
| Adopt FAEP Document ID Standard | Standards | Low | Align Risk document IDs with FAEP-STD-001 (optional, for cross-program traceability) |
| Formalize Evidence IDs | Evidence | Low | Add stable Evidence IDs to PromotionEvidence entities |
| Document FAEP Contract Alignment | Architecture | Medium | Create mapping document showing how Risk contracts align with FAEP Core Contracts |
| Evaluate FRKC Knowledge Consumption | Knowledge | Low | When FRKC matures, evaluate consuming FRKC for regulatory knowledge rather than maintaining separate docs |

---

## Lessons Learned

1. **FAEP had FRKP-centric blind spot.** The risk of defining a platform specification from a single reference implementation is real. FRKP's knowledge-publishing model influenced FAEP contracts and standards more than appropriate. The Risk Platform validation exposed this bias.

2. **Computational engines need different contracts than knowledge engines.** FAEP's Formula, Risk Analytics, and Runtime contracts were too high-level. Risk Platform's compiler pipeline, execution plans, determinism modes, and guardian patterns reveal the depth required for computational engines.

3. **PLAN-based execution is as valid as Bundle-based execution.** FAEP assumed Bundle lifecycle (FRKP pattern) is the universal governance model. Risk Platform's 306+ PLANs demonstrate that PLAN-based execution is equally valid and potentially more appropriate for engineering platforms.

4. **Dependency chain must support both dependent and independent platforms.** FAEP assumed Risk Platform would consume FRKC and FRKP. In reality, Risk Platform evolved independently and has no FAEP dependencies. FAEP must accommodate both integration models.

5. **Production validation is essential.** This PLAN validated FAEP against a real production system (306+ plans, V6.5 lockdown, next-gen formula engine). The findings are more concrete and actionable than any theoretical architecture review.

---

## Recommended PLAN-017

Based on this validation, PLAN-017 should focus on **FAEP Core Contract Formalization — Compiler, Execution Plan, and Determinism Contracts**.

### PLAN-017 Scope

| Item | Description |
| --- | --- |
| **Title** | FAEP Core Contract Formalization — Compiler, Execution Plan, and Determinism |
| **Objective** | Define CC-FRM-002 (Compiler Pipeline Contract), CC-RE-002 (Execution Plan & Content Addressing Contract), and CC-RE-003 (Determinism & Execution Mode Contract) based on Risk Platform patterns |
| **Source** | Risk Platform compiler architecture, RuntimeCompiledPlan, determinism levels, execution modes |
| **Outputs** | 3 new Core Contracts; FAEP-001 revision (Risk Platform maturity update); FAEP-STD-002 revision (add PLAN execution model) |
| **Priority** | High — addresses the 3 highest-priority gaps identified in PLAN-016 |

### Extended Backlog

| Future Plan | Focus | Trigger |
| --- | --- | --- |
| PLAN-018 | FAEP Standard Simplification (Metadata, Evidence, Bundle/PLAN) | After PLAN-017 |
| PLAN-019 | Architecture Test Standard & PLAN Execution Standard | After PLAN-018 |
| PLAN-020 | Risk Platform FAEP Alignment Roadmap | After PLAN-017 through PLAN-019 |

---

## Final Verdict

| Verdict | Rationale |
| --- | --- |
| **CONDITIONAL GO — Minor FAEP refinements recommended** | FAEP Core contracts and standards are sufficient to describe the Risk Platform architecture. The Risk Platform validates 6 of 15 contracts, 6 of 6 standards, and all 9 platform engines. However, FAEP must evolve to (a) add compiler, execution plan, and determinism contracts, (b) correct the Program-300 maturity assessment, and (c) simplify FRKP-biased standards before full cross-program integration. The 3 High-priority refinements (R-001, R-002, R-003) should be addressed in PLAN-017 before declaring full FAEP-Risk Platform alignment. |

---

## Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Platform Validation Using Risk Platform (PLAN-016) |
