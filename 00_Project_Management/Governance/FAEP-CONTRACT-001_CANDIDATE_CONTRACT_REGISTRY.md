# FAEP-CONTRACT-001 - Candidate Contract Registry

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-CONTRACT-001 |
| Document Name | Candidate Contract Registry |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-CONTRACT-000; FAEP-000; FAEP-001; FAEP-002; FRKP-004; FRKP-005; FAEP-STD-000; FAEP-STD-005; FAEP-ADR-000; PLAN-016; PLAN-017 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-017 |

---

# 1. Purpose

This registry records FAEP Candidate Contracts.

Candidate Contracts are non-Core contract proposals under validation. They may guide future architecture work, but they are not mandatory FAEP Core requirements until promoted through FAEP-CONTRACT-000.

---

# 2. Registry Rules

Each Candidate Contract entry must include:

- Candidate ID
- Title
- Origin
- Origin Program
- Origin Reference Implementation
- Problem Statement
- Scope
- Dependencies
- Validation Status
- Supporting Evidence
- Required Programs for Validation
- Promotion Recommendation
- Current Status
- Related ADR
- Related Standards
- Related Specifications

Registry rule: Candidate entries do not modify existing Core Contracts.

---

# 3. Candidate Registry Summary

| Candidate ID | Title | Origin Program | Origin Reference Implementation | Validation Status | Current Status | Promotion Recommendation |
| --- | --- | --- | --- | --- | --- | --- |
| FAEP-CAND-001 | Compiler Pipeline Contract | Program-300 Risk Platform | Risk Platform | Single implementation validated | Candidate | Do not promote until at least one non-Risk program demonstrates concrete compiler lifecycle need |
| FAEP-CAND-002 | Execution Plan Contract | Program-300 Risk Platform | Risk Platform | Single implementation validated | Candidate | Do not promote until another runtime or analytics program needs content-addressed execution plans |
| FAEP-CAND-003 | Determinism Modes Contract | Program-300 Risk Platform | Risk Platform | Single implementation validated | Candidate | Do not promote until multiple execution engines require shared determinism and execution mode semantics |
| FAEP-CAND-004 | Shadow Mode Migration Contract | Program-300 Risk Platform | Risk Platform | Observed in one implementation | Candidate | Hold for validation by engine upgrade programs |
| FAEP-CAND-005 | Bitemporal Data Contract | Program-300 Risk Platform | Risk Platform | Observed in one implementation | Candidate | Hold for validation by IB or Business Platform temporal data needs |
| FAEP-CAND-006 | Universal Variable Codec Contract | Program-300 Risk Platform | Risk Platform | Observed in one implementation | Candidate | Hold for validation by cross-engine serialization needs |
| FAEP-CAND-007 | Execution Mode Contract | Program-300 Risk Platform | Risk Platform | Overlaps FAEP-CAND-003 | Candidate | Merge or keep subordinate to Determinism Modes after further review |
| FAEP-CAND-008 | Governance Guardian Contract | Program-300 Risk Platform | Risk Platform | Observed in one implementation | Candidate | Hold for validation by Governance or Runtime implementations outside Risk |
| FAEP-CAND-009 | PLAN Execution Contract | Program-300 Risk Platform; FRKP planning system | Risk Platform; FRKP | Multi-source pattern observed, not contract-validated | Candidate | Consider for PLAN-018 standard simplification before Core promotion |
| FAEP-CAND-010 | Architecture Enforcement Contract | Program-300 Risk Platform | Risk Platform | Observed in one implementation | Candidate | Hold for validation by at least one non-Java or non-ArchUnit platform |

---

# 4. Candidate Details

## FAEP-CAND-001 - Compiler Pipeline Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-001 |
| Title | Compiler Pipeline Contract |
| Origin | PLAN-016 gap G-001 and recommendation R-001 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform formula compiler |
| Problem Statement | FAEP Formula Contract defines formula responsibilities but does not define reusable compiler lifecycle boundaries for expression parsing, semantic validation, optimization, and executable plan generation. |
| Scope | Candidate boundary for compiler stages, compiler inputs, intermediate representation handoff, validation outputs, diagnostics, and traceability from source expression to executable artifact. |
| Dependencies | Formula Engine; Runtime Engine; Governance Engine; Evidence traceability where formulas are evidence-backed. |
| Validation Status | Single implementation validated by Risk Platform only. |
| Supporting Evidence | PLAN-016 G-001, C-001, and R-001; Risk compiler pattern Lexer -> Parser -> AST -> Optimization -> Canonical Plan -> Runtime Binding. |
| Required Programs for Validation | Risk Platform plus at least one of IB Platform, AI Platform, or another computational Business Platform. |
| Promotion Recommendation | Candidate only. Do not promote until multiple programs require a shared compiler lifecycle. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-006; FAEP-ADR-010 |
| Related Standards | FAEP-STD-000; FAEP-STD-005 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-002 - Execution Plan Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-002 |
| Title | Execution Plan Contract |
| Origin | PLAN-016 gap G-002 and recommendation R-002 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform runtime compiled plan |
| Problem Statement | FAEP Runtime Contract defines execution environment responsibilities but does not specify reusable execution plan identity, schema, content addressing, or runtime handoff. |
| Scope | Candidate boundary for execution plan identity, content hash, versioned plan schema, operation representation, input binding, runtime compatibility, audit trail, and replay support. |
| Dependencies | Runtime Engine; Formula Engine; Version Engine; Governance Engine; Release Engine. |
| Validation Status | Single implementation validated by Risk Platform only. |
| Supporting Evidence | PLAN-016 G-002, C-002, and R-002; Risk RuntimeCompiledPlan and SHA-256 plan hashing. |
| Required Programs for Validation | Risk Platform plus IB simulation, AI planning/runtime, or another analytics runtime implementation. |
| Promotion Recommendation | Candidate only. Promote only if another runtime needs portable execution plans or content-addressed replay. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-006; FAEP-ADR-010; FAEP-ADR-011 |
| Related Standards | FAEP-STD-001; FAEP-STD-004; FAEP-STD-005; FAEP-STD-006 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-003 - Determinism Modes Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-003 |
| Title | Determinism Modes Contract |
| Origin | PLAN-016 gap G-003 and recommendation R-003 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform function metadata and execution mode enforcement |
| Problem Statement | FAEP Principle PP-013 requires deterministic processing but does not define determinism levels, sandbox behavior, replay semantics, or execution mode policy. |
| Scope | Candidate boundary for determinism levels, execution modes, sandbox restrictions, non-deterministic function policy, replay mode, simulation mode, debug mode, and governance override. |
| Dependencies | Runtime Engine; Governance Engine; Formula Engine; Evidence Engine for audit. |
| Validation Status | Single implementation validated by Risk Platform only. |
| Supporting Evidence | PLAN-016 G-003, G-007, C-002, and R-003; Risk PURE / CONTROLLED / NON_DETERMINISTIC levels and PRODUCTION / REPLAY / SIMULATION / DEBUG modes. |
| Required Programs for Validation | Risk Platform plus at least one other execution-bearing platform. |
| Promotion Recommendation | Candidate only. Promote only when multiple execution engines need shared determinism semantics. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-006; FAEP-ADR-014 |
| Related Standards | FAEP-STD-003; FAEP-STD-005; FAEP-STD-006 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-004 - Shadow Mode Migration Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-004 |
| Title | Shadow Mode Migration Contract |
| Origin | PLAN-016 gap G-004 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform compiler shadow mode |
| Problem Statement | FAEP does not define how a platform safely introduces a new engine implementation while comparing it against a legacy implementation. |
| Scope | Candidate boundary for dual execution, comparison criteria, feature flagging, rollout gates, divergence evidence, and governance approval. |
| Dependencies | Runtime Engine; Governance Engine; Release Engine; Version Engine. |
| Validation Status | Observed in one implementation. |
| Supporting Evidence | PLAN-016 G-004 and FAEP-STD-006 release/freeze governance. |
| Required Programs for Validation | Any two programs performing engine replacement or major migration. |
| Promotion Recommendation | Keep as Candidate. Revisit when another platform performs an engine migration. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-010; FAEP-ADR-014 |
| Related Standards | FAEP-STD-005; FAEP-STD-006 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-005 - Bitemporal Data Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-005 |
| Title | Bitemporal Data Contract |
| Origin | PLAN-016 gap G-005 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform variable resolution |
| Problem Statement | FAEP does not define temporal validity and transaction-time semantics for data used by formulas or analytics. |
| Scope | Candidate boundary for valid time, transaction time, temporal query semantics, audit replay, and time-scoped variable resolution. |
| Dependencies | Runtime Engine; Metadata Engine; Evidence Engine; Version Engine. |
| Validation Status | Observed in one implementation. |
| Supporting Evidence | PLAN-016 G-005 and C-010. |
| Required Programs for Validation | Risk Platform plus IB or Business Platform temporal data workflows. |
| Promotion Recommendation | Keep as Candidate. Promote only if temporal semantics become cross-program contract needs. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-011 |
| Related Standards | FAEP-STD-003; FAEP-STD-004 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-006 - Universal Variable Codec Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-006 |
| Title | Universal Variable Codec Contract |
| Origin | PLAN-016 gap G-006 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform variable codec system |
| Problem Statement | FAEP does not define reusable serialization or codec rules for variables shared across engines or stored across compatibility generations. |
| Scope | Candidate boundary for variable serialization, legacy codec support, composite codec resolution, schema versioning, and compatibility behavior. |
| Dependencies | Formula Engine; Runtime Engine; Metadata Engine; Version Engine. |
| Validation Status | Observed in one implementation. |
| Supporting Evidence | PLAN-016 G-006 and C-018. |
| Required Programs for Validation | Risk Platform plus another engine exchanging formula or analytics variables. |
| Promotion Recommendation | Keep as Candidate. Promote only when cross-engine serialization becomes a repeated problem. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-010; FAEP-ADR-015 |
| Related Standards | FAEP-STD-001; FAEP-STD-004 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-007 - Execution Mode Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-007 |
| Title | Execution Mode Contract |
| Origin | PLAN-016 gap G-007 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform CalculationContext execution modes |
| Problem Statement | FAEP does not distinguish runtime modes such as production, replay, simulation, and debug. |
| Scope | Candidate boundary for execution mode names, allowed behaviors, governance gates, and compatibility with determinism policy. |
| Dependencies | Runtime Engine; Governance Engine; Release Engine. |
| Validation Status | Observed in one implementation and overlaps FAEP-CAND-003. |
| Supporting Evidence | PLAN-016 G-007 and C-002. |
| Required Programs for Validation | Risk Platform plus at least one additional execution-bearing program. |
| Promotion Recommendation | Candidate only. Prefer consolidation with FAEP-CAND-003 unless validation shows mode semantics need a separate Core Contract. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-014 |
| Related Standards | FAEP-STD-005; FAEP-STD-006 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-008 - Governance Guardian Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-008 |
| Title | Governance Guardian Contract |
| Origin | PLAN-016 gap G-008 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform GovernanceGuard and lifecycle policies |
| Problem Statement | FAEP Governance Contract requires enforcement but does not define a reusable policy-first runtime guard boundary. |
| Scope | Candidate boundary for guard invocation, policy chain, fail-closed behavior, override evidence, and audit output. |
| Dependencies | Governance Engine; Runtime Engine; Evidence Engine; AI Agent Engine. |
| Validation Status | Observed in one implementation. |
| Supporting Evidence | PLAN-016 G-008 and C-019. |
| Required Programs for Validation | Risk Platform plus AI Platform or another runtime-governed Business Platform. |
| Promotion Recommendation | Candidate only. Promote only if multiple programs need consistent runtime governance interception. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-014; FAEP-ADR-015 |
| Related Standards | FAEP-STD-003; FAEP-STD-005 |
| Related Specifications | FRKP-004 |

## FAEP-CAND-009 - PLAN Execution Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-009 |
| Title | PLAN Execution Contract |
| Origin | PLAN-016 gap G-009 |
| Origin Program | Program-300 Risk Platform; Program-200 FRKP |
| Origin Reference Implementation | Risk Platform PLAN system; FRKP planning system |
| Problem Statement | FAEP uses PLANs internally and Risk has extensive PLAN-based execution, but Core does not distinguish PLAN-based execution from Bundle-based execution as a reusable governance primitive. |
| Scope | Candidate boundary for plan identification, activation, review, completion, history, evidence, and handoff state. |
| Dependencies | Governance Engine; Workflow Engine; Release Engine; AI Agent Engine. |
| Validation Status | Multi-source pattern observed, not yet validated as a Core Contract. |
| Supporting Evidence | PLAN-016 G-009; existing FRKP PLAN_INDEX, active.md, CURRENT_WORK.md, next-session.md, and history records. |
| Required Programs for Validation | FRKP, Risk Platform, and one future platform using PLAN execution independently. |
| Promotion Recommendation | Candidate only. PLAN-018 should first clarify Bundle versus PLAN as governance models before any Core promotion. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-013; FAEP-ADR-014 |
| Related Standards | FAEP-STD-000; FAEP-STD-002; FAEP-STD-005; FAEP-STD-006 |
| Related Specifications | FAEP-002; FRKP-004 |

## FAEP-CAND-010 - Architecture Enforcement Contract

| Field | Value |
| --- | --- |
| Candidate ID | FAEP-CAND-010 |
| Title | Architecture Enforcement Contract |
| Origin | PLAN-016 gap G-010 and recommendation R-005 |
| Origin Program | Program-300 Risk Platform |
| Origin Reference Implementation | Risk Platform ArchUnit tests |
| Problem Statement | FAEP architecture standards require conformance but do not define automated architecture enforcement expectations across implementation technologies. |
| Scope | Candidate boundary for architecture rule declaration, automated enforcement, violation evidence, exceptions, and review gates. |
| Dependencies | Governance Engine; AI Agent Engine; Release Engine; platform-local implementation tooling. |
| Validation Status | Observed in one implementation. |
| Supporting Evidence | PLAN-016 G-010 and C-009. |
| Required Programs for Validation | Risk Platform plus at least one non-Java or non-ArchUnit program. |
| Promotion Recommendation | Candidate only. Consider standard guidance before Core Contract promotion. |
| Current Status | Candidate |
| Related ADR | FAEP-ADR-006; FAEP-ADR-014 |
| Related Standards | FAEP-STD-005; FAEP-STD-006 |
| Related Specifications | FAEP-002; FRKP-004 |

---

# 5. Validation Workflow

```text
Candidate Registered
    -> Origin Evidence Confirmed
    -> Non-Origin Program Review
    -> Reference Validation
    -> Cross-Program Comparison
    -> Promotion / Hold / Reject Recommendation
```

Validation must answer:

- Is this a recurring cross-program problem?
- What part is contract and what part is implementation?
- Can programs implement the contract differently and still conform?
- What governance evidence supports promotion?
- What risks arise if promotion is delayed?
- What risks arise if promotion happens too early?

---

# 6. Promotion Workflow

```text
Candidate -> Validated Candidate -> Core Recommendation -> ADR -> Architecture Board Approval -> Core Contract
```

Promotion requires:

- Candidate registry entry updated.
- Validation evidence attached or referenced.
- At least two independent program needs, unless exception is justified by ADR.
- Related standards and specifications identified.
- Compatibility and migration impact reviewed.
- Architecture Board approval recorded.

---

# 7. Governance Workflow

| Step | Responsible Body | Output |
| --- | --- | --- |
| Candidate proposal | Origin program lead or plan owner | Proposal text |
| Architecture review | FAEP Architecture Board | Accept, reject, or refine decision |
| Registry update | FAEP Architecture Board | Candidate entry |
| Reference validation | Origin and non-origin program leads | Validation evidence |
| Cross-program review | FAEP Program Review Council | Validation summary |
| Core decision | FAEP Architecture Board | Promotion, hold, or rejection |
| Program escalation | FAEP Program Governance Board | Exception or material scope approval |

---

# 8A. Capability Boundary Notes

## PLAN-026A - AI Collaboration Operating Model

PLAN-026A registered the AI Collaboration Operating Model as Candidate Capability `CAP-AI-001`, not as a Candidate Contract.

No FAEP-CAND entry is created for PLAN-026A. The current evidence from PLAN-024, PLAN-025, and PLAN-026 validates capability routing within FRKP Publishing, but does not yet establish a reusable interoperability contract suitable for Candidate Contract registration or Core promotion.

The boundary decision is:

- Candidate Capability: yes, registered in FAEP-CAP-001.
- Candidate Contract: no.
- Core Contract: no.
- Provider standardization: no.

Future contract consideration requires cross-program validation and explicit Architecture Board review.

---
# 8B. Lessons Learned from PLAN-016

1. A production-grade Reference Implementation can reveal important gaps without automatically defining FAEP Core.
2. Risk Platform patterns are valuable, especially compiler lifecycle, execution plan identity, determinism policy, PLAN execution, and architecture enforcement.
3. Single-program maturity is not enough for Core promotion.
4. FAEP must support both dependent and independent platform models.
5. FRKP-derived governance should not be generalized without validation against computational and business platforms.
6. Candidate Contracts are the right holding state for valuable but not-yet-generalized concepts.

---

# 9. Recommended PLAN-018

PLAN-018 should focus on FAEP standard simplification and execution model clarification:

- Distinguish Bundle lifecycle from PLAN lifecycle.
- Clarify minimal metadata and evidence baselines.
- Review PLAN-016 over-generalization findings.
- Decide whether PLAN Execution belongs first as a standard update, a Candidate Contract, or both.
- Preserve Candidate Contracts until cross-program validation exists.

---

# 10. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Candidate Contract Registry created by PLAN-017 |
| 1.0.1 | 2026-06-29 | Added PLAN-026A boundary note: AI Collaboration Operating Model registered as Candidate Capability, not Candidate Contract |
