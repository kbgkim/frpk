# PLAN-017 - FAEP Contract Lifecycle and Candidate Validation

## Plan Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-017 |
| Title | FAEP Contract Lifecycle and Candidate Validation |
| Status | Completed |
| Category | Contract Governance |
| Owner | FAEP Architecture Board |
| Repository | https://github.com/kbgkim/frpk |
| Branch | feature/bundle-007-operational-risk |
| Created | 2026-06-28 |
| Completed | 2026-06-28 |

---

## Executive Summary

PLAN-017 establishes the FAEP Contract Lifecycle and introduces Candidate Contracts as the governed holding state between observed implementation patterns and FAEP Core Contracts.

PLAN-016 identified valuable concepts from the Risk Platform, including Compiler Pipeline, Execution Plan, and Determinism Modes. PLAN-017 explicitly does not promote those concepts to Core. Instead, it creates a lifecycle and registry that require cross-program validation before Core promotion.

Verdict: GO - FAEP Contract Lifecycle Established.

---

## 1. Objective

Define the complete lifecycle of FAEP Contracts and govern how new contracts are proposed, validated, promoted, deprecated, and retired.

This plan governs future evolution of FAEP Core without changing existing Core Contracts.

---

## 2. Scope

In scope:

- Contract lifecycle governance.
- Candidate Contract definition.
- Candidate registry creation.
- Promotion, validation, deprecation, retirement, and approval rules.
- Initial registration of PLAN-016 candidates as Candidate only.
- Planning state updates.

Out of scope:

- Implementation.
- Repository migration.
- Core Contract creation.
- Core Contract modification.
- Frozen artifact modification.
- Release or commit activity.

---

## 3. Source of Truth

Source priority used:

1. FAEP Standards.
2. FAEP Specifications.
3. Program Governance.
4. PLAN-016 Validation Report.
5. ADR Registry.
6. Current Core Contracts.

---

## 4. Deliverables

| Deliverable | Status | Location |
| --- | --- | --- |
| Contract Lifecycle Standard | Completed | 00_Project_Management/Governance/FAEP-CONTRACT-000_CONTRACT_LIFECYCLE_STANDARD.md |
| Candidate Contract Registry | Completed | 00_Project_Management/Governance/FAEP-CONTRACT-001_CANDIDATE_CONTRACT_REGISTRY.md |
| PLAN-017 history record | Completed | 00_Project_Management/Plans/03_history/PLAN-017_FAEP_CONTRACT_LIFECYCLE_AND_CANDIDATE_VALIDATION.md |
| PLAN_INDEX.md update | Completed | 00_Project_Management/Plans/PLAN_INDEX.md |
| active.md update | Completed | 00_Project_Management/Plans/active.md |
| CURRENT_WORK.md update | Completed | 00_Project_Management/Plans/CURRENT_WORK.md |
| next-session.md update | Completed | 00_Project_Management/Plans/next-session.md |
| PROJECT_STATE.md update | Completed | 00_Project_Management/Sessions/PROJECT_STATE.md |

---

## 5. Contract Lifecycle Summary

FAEP Contracts now follow this lifecycle:

```text
Idea -> Proposal -> Candidate -> Validated -> Core -> Deprecated -> Retired
```

| Stage | Purpose |
| --- | --- |
| Idea | Capture a potentially reusable pattern or problem. |
| Proposal | Submit the idea for architecture review. |
| Candidate | Register a non-Core contract for validation. |
| Validated | Record sufficient cross-program evidence for Core recommendation. |
| Core | Govern FAEP-conformant programs normatively. |
| Deprecated | Preserve compatibility while discouraging new use. |
| Retired | Preserve historical traceability only. |

Each stage includes entry criteria, exit criteria, required evidence, required validation, and required reviewers.

---

## 6. Candidate Registry Summary

PLAN-017 created FAEP-CONTRACT-001 as the Candidate Contract Registry.

Each Candidate Contract includes:

- Candidate ID.
- Title.
- Origin.
- Origin Program.
- Origin Reference Implementation.
- Problem Statement.
- Scope.
- Dependencies.
- Validation Status.
- Supporting Evidence.
- Required Programs for Validation.
- Promotion Recommendation.
- Current Status.
- Related ADR.
- Related Standards.
- Related Specifications.

---

## 7. Initial Candidate List

The following concepts were registered as Candidate only:

| Candidate ID | Title | Source |
| --- | --- | --- |
| FAEP-CAND-001 | Compiler Pipeline Contract | PLAN-016 G-001 / R-001 |
| FAEP-CAND-002 | Execution Plan Contract | PLAN-016 G-002 / R-002 |
| FAEP-CAND-003 | Determinism Modes Contract | PLAN-016 G-003 / R-003 |
| FAEP-CAND-004 | Shadow Mode Migration Contract | PLAN-016 G-004 |
| FAEP-CAND-005 | Bitemporal Data Contract | PLAN-016 G-005 |
| FAEP-CAND-006 | Universal Variable Codec Contract | PLAN-016 G-006 |
| FAEP-CAND-007 | Execution Mode Contract | PLAN-016 G-007 |
| FAEP-CAND-008 | Governance Guardian Contract | PLAN-016 G-008 |
| FAEP-CAND-009 | PLAN Execution Contract | PLAN-016 G-009 |
| FAEP-CAND-010 | Architecture Enforcement Contract | PLAN-016 G-010 |

No candidate was promoted to Core.

---

## 8. Promotion Workflow

The promotion workflow is:

```text
Proposal -> Architecture Review -> Candidate -> Reference Validation -> Core Recommendation -> Architecture Board Approval -> Core Contract
```

Core promotion is allowed only when multiple programs demonstrate concrete need, or when a justified exception is approved through ADR and governance approval.

Minimum validation guidance:

- At least two independent programs should normally validate a contract before Core promotion.
- Examples include Risk plus IB, Risk plus AI, or FRKP plus a Business Platform.
- This is guidance, not a rigid rule.
- Exceptions require ADR documentation and governance approval.

---

## 9. Governance Workflow

| Action | Authority |
| --- | --- |
| Propose | Any program lead, platform lead, plan owner, domain governance body, or Architecture Board member |
| Review | FAEP Architecture Board and affected domain owners |
| Approve Candidate | FAEP Architecture Board |
| Validate | Origin and non-origin program leads |
| Recommend Core | FAEP Architecture Board |
| Approve Core | FAEP Architecture Board, with Program Governance Board for material Core expansion |
| Reject | FAEP Architecture Board with rationale |
| Deprecate | FAEP Architecture Board |
| Retire | FAEP Architecture Board with Program Review Council confirmation |

---

## 10. Validation Workflow

Candidate validation proceeds through:

```text
Candidate Registered -> Origin Evidence Confirmed -> Non-Origin Program Review -> Reference Validation -> Cross-Program Comparison -> Promotion / Hold / Reject Recommendation
```

Validation must prove recurring cross-program need. It must not merely prove that the origin implementation is mature or elegant.

---

## 11. Anti Over-Generalization Rules

PLAN-017 establishes the following rules:

- Never promote because a pattern is elegant.
- Never promote because one implementation is mature.
- Never promote because a pattern appears generally useful in theory.
- Promote because multiple programs need it.
- Preserve implementation freedom unless the contract boundary must be standardized.
- Use ADR and governance approval for exceptions.

---

## 12. Lessons Learned from PLAN-016

1. The Risk Platform is mature enough to reveal FAEP gaps, but not enough by itself to define new Core Contracts.
2. Compiler Pipeline, Execution Plan, and Determinism Modes are valuable candidates, not Core obligations.
3. PLAN-based execution may be a reusable governance primitive, but it must be reconciled with Bundle-based execution before standardization.
4. FAEP must support independent platforms, not only platforms dependent on FRKC and FRKP.
5. Candidate Contracts prevent both loss of valuable ideas and premature over-generalization.

---

## 13. Preservation Statement

PLAN-017 did not modify:

- Version 1.0.0 frozen artifacts.
- Bundle-007 frozen artifacts.
- Existing Standards.
- Existing Specifications.
- Existing Core Contracts.

PLAN-017 did not perform:

- Implementation.
- Repository migration.
- Commits.
- Releases.

---

## 14. Recommended PLAN-018

Recommended PLAN-018:

**FAEP Standard Simplification and Execution Model Clarification**

Recommended scope:

- Distinguish Bundle lifecycle and PLAN lifecycle.
- Simplify metadata and evidence baselines where PLAN-016 identified FRKP-centric bias.
- Decide how PLAN Execution should relate to FAEP-STD-002 and Candidate Contract governance.
- Review Candidate Contracts after at least one non-Risk validation opportunity exists.
- Preserve all frozen artifacts and existing Core Contracts.

---

## 15. Final Verdict

GO - FAEP Contract Lifecycle Established

---

## Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial PLAN-017 contract lifecycle and candidate validation record |
