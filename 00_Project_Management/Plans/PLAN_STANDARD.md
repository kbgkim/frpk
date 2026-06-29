# PLAN_STANDARD

## Financial Risk Knowledge Platform (FRKP)

---

# Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PLAN-STD-001 |
| Document Name | FRKP Planning Standard |
| Version | 1.0.0 |
| Status | Active |
| Created | 2026-06-28 |
| Purpose | Define the FRKP planning and execution management framework |

---

# 1. Purpose

This standard defines how FRKP plans are created, reviewed, executed, completed, and archived.

The planning framework is optimized for the FRKP and FRKC ecosystem. It manages knowledge engineering, evidence-driven publishing, bundle development, review, freeze, and release activities.

This standard does not replace existing repository governance, bundle standards, document standards, or evidence-driven publishing rules.

---

# 2. Planning Lifecycle

Every plan follows the lifecycle below unless the plan is explicitly cancelled or deferred.

```text
Idea
    |
    v
Boundary Review
    |
    v
Knowledge Gap Review
    |
    v
Evidence Readiness Review
    |
    v
Publishing Mapping Review
    |
    v
Execution
    |
    v
Bundle or Document Review
    |
    v
Freeze
    |
    v
Closure
    |
    v
Release or Archive
```

## Lifecycle Definitions

| Stage | Purpose |
| --- | --- |
| Idea | Capture a proposed work item without committing execution resources |
| Boundary Review | Confirm scope, repository layer, bundle relationship, and exclusions |
| Knowledge Gap Review | Identify missing concepts, documents, mappings, formulas, or glossary terms |
| Evidence Readiness Review | Confirm FRKC evidence is available, traceable, and sufficient |
| Publishing Mapping Review | Confirm FRKC-to-FRKP target mappings and publication layer readiness |
| Execution | Produce or update planned artifacts |
| Bundle or Document Review | Verify standards, cross-references, evidence use, and reviewer requirements |
| Freeze | Stop scope expansion and allow only correction-level edits |
| Closure | Record completion evidence, residual risks, and follow-up plans |
| Release or Archive | Include in release scope or move to history |

---

# 3. Plan Categories

Plans must declare one primary category and may declare secondary categories.

| Category | Purpose |
| --- | --- |
| Boundary Review | Defines scope, exclusions, repository layer, bundle alignment, and acceptance limits |
| Knowledge Review | Assesses canonical concepts, glossary terms, domain coverage, and knowledge gaps |
| Evidence Review | Confirms evidence bundles, source traceability, citations, and confidence level |
| Publishing Review | Confirms FRKC publishing mappings and FRKP layer placement |
| Bundle Review | Coordinates bundle completeness, consistency, freeze readiness, and release readiness |
| Architecture Review | Reviews repository structure, platform architecture, and cross-layer dependencies |
| Quality Review | Checks document standards, links, naming, navigation, formatting, and consistency |
| Release Review | Confirms release scope, freeze status, completion evidence, and residual risk |
| Governance Review | Validates compatibility with FRKP governance and existing standards |

---

# 4. Plan Status Model

## Status Values

| Status | Meaning |
| --- | --- |
| Proposed | Captured but not approved for execution |
| Planned | Accepted into planning scope but not active |
| Active | Currently being executed |
| Review | Execution complete and awaiting review, freeze, closure, or release decision |
| Completed | Closed with required deliverables and completion evidence |
| Deferred | Paused or moved out of current planning horizon |
| Cancelled | Closed without completion because the plan is no longer valid |

## Transition Rules

```text
Proposed -> Planned
Proposed -> Cancelled
Planned -> Active
Planned -> Deferred
Active -> Review
Active -> Deferred
Active -> Cancelled
Review -> Active
Review -> Completed
Review -> Deferred
Completed -> 03_history
Deferred -> Planned
Cancelled -> 03_history
```

Rules:

* A plan becomes Active only when it is listed in `active.md` and has an execution owner.
* A plan enters Review when deliverables are complete enough for validation.
* A plan may return from Review to Active if required corrections are material.
* A plan is Completed only after a closure report records deliverables, validation, and residual risks.
* Deferred and Cancelled plans must retain the reason and date.

---

# 5. Numbering Policy

Plan IDs use sequential numbering only.

```text
PLAN-001
PLAN-002
PLAN-003
```

Rules:

* Do not use category prefixes.
* Do not reuse retired numbers.
* Do not renumber existing plans.
* File names should use:

```text
PLAN-###_SHORT_TITLE.md
```

---

# 6. Repository Layout

```text
00_Project_Management/
    Plans/
        README.md
        PLAN_STANDARD.md
        PLAN_INDEX.md
        active.md
        next-session.md
        CURRENT_WORK.md
        01_active/
        02_review/
        03_history/
```

## Placement Rules

| Location | Rule |
| --- | --- |
| Plans root | Framework files and current PLAN_INDEX |
| 01_active/ | Active execution plans |
| 02_review/ | Plans in review, freeze, closure, or release approval |
| 03_history/ | Completed, deferred, or cancelled plans |

The master index remains in the Plans root regardless of plan file location.

---

# 7. Plan Template

```markdown
# PLAN-### - Title

## Document Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-### |
| Title |  |
| Status | Proposed |
| Category |  |
| Owner |  |
| Bundle |  |
| Related Documents |  |
| Created | YYYY-MM-DD |
| Target Completion | YYYY-MM-DD |
| Completion Date |  |

## Objective

## Scope

## Out of Scope

## Background

## Lifecycle Stage

## FRKC Dependencies

## Evidence Requirements

## Publishing Requirements

## Bundle Integration

## Deliverables

## Acceptance Criteria

## Review Requirements

## Risks and Open Questions

## Execution Notes

## Closure Summary
```

---

# 8. Review Template

```markdown
# PLAN-### Review

## Review Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-### |
| Review Type | Boundary / Knowledge / Evidence / Publishing / Bundle / Quality / Release / Governance |
| Reviewer |  |
| Review Date | YYYY-MM-DD |
| Result | Pass / Pass with Observations / Rework Required / Fail |

## Review Scope

## Evidence Checked

## Standards Checked

## Findings

## Required Corrections

## Observations

## Decision
```

---

# 9. Closure Report Template

```markdown
# PLAN-### Closure Report

## Closure Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-### |
| Title |  |
| Closed By |  |
| Closure Date | YYYY-MM-DD |
| Final Status | Completed / Deferred / Cancelled |

## Deliverables Completed

## Validation Performed

## Compatibility Checks

## Residual Risks

## Follow-up Plans

## Archive Location

## Closure Decision
```

---

# 10. PLAN_INDEX Requirements

`PLAN_INDEX.md` is the master register of all plans.

It must track:

* Plan ID
* Title
* Status
* Category
* Bundle
* Owner
* Related Documents
* Location
* Completion Date

Every new plan must be added to `PLAN_INDEX.md` before execution begins.

---

# 11. Session Management

## MASTER_SESSION.md

`MASTER_SESSION.md` remains the project-level baseline.

Update it only when planning work changes project-level status, current milestone, current bundle, release status, or mandatory standards. The existence of a new plan alone does not require a MASTER_SESSION update.

## AI_SESSION_HANDOFF.md

`AI_SESSION_HANDOFF.md` remains the minimum startup context for new AI sessions.

Update it when a plan changes the next recommended work, active bundle, session startup requirements, or completion checklist.

## Planning Session Files

| File | Use |
| --- | --- |
| active.md | Current Active and Review plans |
| next-session.md | Immediate planning handoff for the next session |
| CURRENT_WORK.md | Current task focus and execution notes |

## Activation Rule

A plan becomes Active when:

* It is listed in `PLAN_INDEX.md`.
* It is listed in `active.md`.
* The owner is identified.
* Scope and acceptance criteria are defined.

## Archive Rule

A plan is archived when:

* Status is Completed, Deferred, or Cancelled.
* Closure information is recorded.
* `PLAN_INDEX.md` is updated.
* The plan file is moved to `03_history/`.

---

# 12. Bundle Integration

Bundle planning follows this sequence.

```text
Bundle
    |
    v
Boundary Review
    |
    v
Knowledge Review
    |
    v
Evidence Review
    |
    v
Publishing Mapping Review
    |
    v
Publishing Execution
    |
    v
Bundle Review
    |
    v
Freeze
    |
    v
Release Review
```

For every bundle plan, record:

* Bundle ID
* Target documents
* Required FRKC evidence
* Publishing mappings
* Review requirements
* Freeze criteria
* Release criteria

---

# 13. FRKC Integration

FRKC is the authoritative knowledge source.

Plans must identify FRKC dependencies where applicable:

* Knowledge gap detection
* Canonical concept availability
* Evidence bundle readiness
* Source traceability
* Glossary readiness
* Formula reference readiness
* Publishing mapping readiness

No FRKP publishing plan should advance beyond Evidence Readiness Review unless required FRKC evidence is available or the gap is explicitly accepted as a risk.

---

# 14. Completion Process

A plan may be marked Completed only when:

* Deliverables are created.
* Required reviews are recorded.
* Compatibility checks are complete.
* Residual risks are documented.
* `PLAN_INDEX.md` is updated.
* Session handoff impact is assessed.
* The plan is moved or marked for `03_history/`.

---

# 15. Compatibility Requirements

Planning artifacts must remain compatible with:

* MASTER_SESSION.md
* AI_SESSION_HANDOFF.md
* FRKP-FRKC-001 Evidence-Driven Publishing Workflow
* FRKP Governance
* Bundle Standards
* Document Standards

Planning must not modify existing document IDs, bundle numbering, governance standards, or repository structure outside the Plans directory.

