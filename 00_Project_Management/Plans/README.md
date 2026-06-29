# FRKP Planning Framework

## Purpose

This directory manages planning and execution for the Financial Risk Knowledge Platform (FRKP).

The planning framework governs the lifecycle of knowledge engineering, evidence readiness, publishing, review, bundle development, freeze, and release.

It is independent from software implementation planning used in other projects.

## Scope

The framework applies to FRKP and FRKC ecosystem work that affects:

* Knowledge coverage
* Evidence readiness
* Publishing mappings
* FRKP documents
* Bundles
* Reviews
* Releases
* Governance execution

## Operating Principle

FRKP planning follows the platform lifecycle.

```text
Knowledge
    |
    v
Evidence
    |
    v
Publishing
    |
    v
Review
    |
    v
Release
```

## Directory Layout

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

## Files

| File | Purpose |
| --- | --- |
| README.md | Overview of the planning framework |
| PLAN_STANDARD.md | Lifecycle, categories, status model, numbering, templates, and integration rules |
| PLAN_INDEX.md | Master register of all plans |
| active.md | Current active plan list |
| next-session.md | Planning handoff for the next AI or human session |
| CURRENT_WORK.md | Current execution focus and immediate tasks |

## Folders

| Folder | Purpose |
| --- | --- |
| 01_active/ | Plans currently being executed |
| 02_review/ | Plans in review, freeze, closure, or release approval |
| 03_history/ | Completed, cancelled, or deferred plans |

## Required Session Integration

Planning work must remain compatible with:

* MASTER_SESSION.md
* AI_SESSION_HANDOFF.md
* FRKP-FRKC-001 Evidence-Driven Publishing Workflow
* FRKP Governance
* Bundle Standards
* Document Standards

Existing standards are authoritative. This planning framework organizes execution and does not replace governance.

