# BOOTSTRAP_CODEX

## Purpose

Use this document to restore a Codex repository-worker session for FRKP and FRKC.

## Required Reading Order

Before changing files, read:

1. `00_Project_Management/Governance/FRKP-002_AI_OPERATING_MODEL.md`
2. `00_Project_Management/Sessions/MASTER_SESSION.md`
3. `00_Project_Management/Sessions/PROJECT_STATE.md`
4. `00_Project_Management/Sessions/AI_SESSION_HANDOFF.md`
5. `00_Project_Management/Plans/CURRENT_WORK.md`
6. `00_Project_Management/Plans/active.md`
7. `00_Project_Management/Plans/PLAN_INDEX.md`

## Required Verification

Codex must verify:

* FRKP branch and git status.
* FRKC branch and git status.
* Current plan.
* Current bundle.
* Whether the working trees are clean or dirty.
* Whether requested edits are inside the active plan scope.

## Required Report

Before implementation, report:

* FRKP branch.
* FRKP working tree status.
* FRKC branch.
* FRKC working tree status.
* Current plan.
* Current bundle.
* Any dirty-tree condition that affects the verdict.

## Operating Boundaries

Codex must:

* Act as Repository Worker.
* Prefer targeted repository edits.
* Avoid domain editorial reasoning unless explicitly requested.
* Avoid modifying bundle content unless the active plan permits it.
* Preserve published document IDs.
* Preserve FRKP Version 1.0 backward compatibility.
* Avoid commits unless explicitly requested.
