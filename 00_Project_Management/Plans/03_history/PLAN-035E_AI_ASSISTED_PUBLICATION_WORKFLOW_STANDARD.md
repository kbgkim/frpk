# PLAN-035E - AI-Assisted Publication Workflow Standard

## Document Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-035E |
| Title | AI-Assisted Publication Workflow Standard |
| Status | Completed |
| Category | Publication Governance; Workflow Standard |
| Owner | Codex |
| Bundle | Bundle-007 |
| Created | 2026-06-29 |
| Completion Date | 2026-06-29 |

---

# 1. Objective

Create the official AI-Assisted Publication Workflow specification for the FRKP Publishing Program.

The specification defines responsibilities, workflow stages, inputs, outputs, review gates, provider mapping, and execution responsibilities by capability rather than by fixed provider.

This plan is governance-only. It does not modify Bundle-007 source contents, publication contents, FAEP Foundation artifacts, standards, contracts, the Execution Model, or the Validation Framework.

---

# 2. Repository Verification

| Check | Result |
| --- | --- |
| Required branch | feature/bundle-007-operational-risk |
| Current branch | feature/bundle-007-operational-risk |
| Branch verification | PASS |
| Repository synchronization | PASS - `git rev-list --left-right --count HEAD...origin/feature/bundle-007-operational-risk` returned `0 0` |
| Source of truth | Repository documents only |
| Worktree status | Existing staged, modified, and untracked FRKP artifacts were present before PLAN-035E and were preserved. |

No previous conversation memory was used as source of truth.

---

# 3. Required Baseline Reviewed

| Baseline | Review Use |
| --- | --- |
| FRKP-PROGRAM-000 | Confirmed Publication Program ownership, governance hierarchy, publication responsibilities, and preservation commitments. |
| FRKP-PROGRAM-001 | Confirmed publication workflow stages, inputs, outputs, transition rules, freeze, and official publication model. |
| FRKP-EDITORIAL-003 | Confirmed provider-neutral capability model, automation categories, review responsibilities, and provider replaceability. |
| FRKP-EDITORIAL-004 | Confirmed execution profile catalog, contract routing, review requirements, and ordered AUTO/SEMI-AUTO/MANUAL review structure. |
| BUNDLE-007_REVIEW_PACKAGE | Confirmed validated handoff from Engineering Review to GPT review and remaining semantic, financial, architecture, publication, and traceability conditions. |
| PLAN-035A | Confirmed review package generation as the bounded Engineering Review handoff and the no-source-modification constraint. |

---

# 4. Scope

In scope:

- Create the AI-Assisted Publication Workflow governance specification.
- Define the workflow from Authoring through Publication.
- Define responsibilities by capability rather than provider.
- Record current provider mapping for OpenCode, Codex, and GPT.
- Define stage inputs, outputs, and completion criteria.
- Define Engineering, Semantic, Publication, and Freeze review gates.
- Document workflow diagram, capability matrix, provider mapping, review gates, and future runtime readiness.

Out of scope:

- Bundle modifications.
- Publication modifications.
- FAEP Foundation changes.
- Standards changes.
- Contract changes.
- Execution Model changes.
- Validation Framework changes.
- Repository migration.
- Implementation.
- Release.
- Publication freeze.

---

# 5. Deliverables

| Deliverable | Location | Status |
| --- | --- | --- |
| AI-Assisted Publication Workflow | `00_Project_Management/Governance/FRKP-EDITORIAL-005_AI_ASSISTED_PUBLICATION_WORKFLOW.md` | Created |
| PLAN-035E history record | `00_Project_Management/Plans/03_history/PLAN-035E_AI_ASSISTED_PUBLICATION_WORKFLOW_STANDARD.md` | Created |

---

# 6. Workflow Standard Summary

The standardized workflow is:

```text
Authoring
  -> Engineering Review
    -> Review Package
      -> Semantic Review
        -> Repository Apply
          -> Freeze Review
            -> Publication
```

The standard records the Bundle-007 validated provider sequence as an example:

```text
OpenCode
  -> Codex
    -> GPT
      -> Codex
        -> GPT
```

The governance rule is that capabilities remain stable while providers remain replaceable.

---

# 7. Capability Model Summary

| Capability | Standard Responsibility |
| --- | --- |
| Authoring Capability | Produces draft content or governed candidate documents. |
| Engineering Validation Capability | Verifies branch, synchronization, deterministic consistency, metadata, links, and patch safety. |
| Semantic Review Capability | Reviews meaning, terminology, assumptions, and conceptual consistency. |
| Financial Review Capability | Reviews financial, regulatory, capital, formula, and risk-domain claims. |
| Architecture Review Capability | Reviews architecture boundaries, components, workflow, and platform implications. |
| Publication Review Capability | Reviews publication readiness, metadata, navigation, and handoff completeness. |
| Freeze Approval Capability | Determines whether freeze conditions are satisfied and residual risks are acceptable. |
| Repository Update Capability | Applies approved repository changes while preserving unrelated work. |
| Governance Capability | Maintains lifecycle state, plan records, escalation outcomes, and final verdicts. |

---

# 8. Provider Mapping Summary

| Provider | Current Role in Workflow |
| --- | --- |
| OpenCode | Authoring provider. |
| Codex | Engineering validation and repository update provider. |
| GPT | Semantic, financial, architecture, publication, and freeze-review provider. |

Providers are replaceable. The workflow is governed by capability responsibility and review evidence, not by provider identity.

---

# 9. Review Gates Summary

| Gate | Purpose |
| --- | --- |
| Engineering Gate | Confirm branch, sync, repository source of truth, deterministic review state, and scope control. |
| Semantic Gate | Confirm conceptual, domain, financial, architecture, and traceability readiness. |
| Publication Gate | Confirm publication metadata, navigation, reading order, quality conditions, and authorization readiness. |
| Freeze Gate | Confirm review completion, residual risk, scope lock, change control, and freeze decision. |

---

# 10. Preservation Statement

PLAN-035E did not modify:

- FAEP Foundation.
- Standards.
- Contracts.
- Bundle contents.
- Publication contents.
- Execution Model.
- Validation Framework.
- Bundle-007 source documents.
- Published handbook contents.

PLAN-035E did not perform:

- Implementation.
- Repository migration.
- Publication edit.
- Release.
- Publication freeze.
- Bundle remediation.

---

# 11. Acceptance Criteria

| Criterion | Status |
| --- | --- |
| Required branch verified before work | PASS |
| Repository synchronization verified before work | PASS |
| Repository treated as only source of truth | PASS |
| Required baseline documents reviewed | PASS |
| Governance specification created | PASS |
| PLAN-035E history record created | PASS |
| Workflow diagram defined | PASS |
| Capability matrix defined | PASS |
| Provider mapping defined | PASS |
| Inputs, outputs, and completion criteria defined | PASS |
| Review gates defined | PASS |
| Future runtime readiness documented without implementation | PASS |
| No Bundle modifications performed | PASS |
| No publication modifications performed | PASS |
| No Foundation, Standards, Contracts, Execution Model, or Validation Framework changes performed | PASS |

---

# 12. Final Verdict

GO — AI-Assisted Publication Workflow Standard Established
