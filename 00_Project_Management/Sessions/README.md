# Sessions

## Financial Risk Knowledge Platform (FRKP)

This directory contains the operational documents used to maintain long-term continuity across ChatGPT conversations, Codex sessions, and GitHub-based development.

These documents provide the current project state, long-term context, operating rules, and development history required to continue the project without relying on previous conversation history.

---

# Purpose

The **Sessions** directory establishes a standardized AI collaboration framework for FRKP.

It ensures that every new development session begins with the same repository understanding, architectural principles, and governance rules.

---

# Recommended Reading Order

When starting a new ChatGPT conversation or Codex task, read the documents in the following order.

| Order | Document              | Purpose                                                  |
| ----: | --------------------- | -------------------------------------------------------- |
|     1 | MASTER_SESSION.md     | Current project status and active milestone              |
|     2 | SESSION_BOOTSTRAP.md  | Operating rules for every new AI session                 |
|     3 | FRKP_CONTEXT.md       | Long-term project philosophy and repository architecture |
|     4 | SESSION_HISTORY.md    | Chronological project history and major milestones       |
|     5 | AI_SESSION_HANDOFF.md | Standard handoff template for new AI sessions            |

---

# Document Responsibilities

## MASTER_SESSION.md

Maintains the current state of the repository.

Typical contents include:

* Current Version
* Current Bundle
* Repository Status
* Current Milestone
* Next Priority
* Active Roadmap

This document is updated whenever the project status changes.

---

## SESSION_BOOTSTRAP.md

Defines the standard operating procedure for every new ChatGPT or Codex session.

Typical contents include:

* Repository Rules
* Standards
* Naming Conventions
* Bundle Rules
* Session Startup Checklist
* Session Completion Checklist

This document changes infrequently.

---

## FRKP_CONTEXT.md

Provides the long-term context of the project.

Typical contents include:

* Vision
* Mission
* Repository Philosophy
* Layer Architecture
* Bundle Architecture
* AI Collaboration Model
* Long-Term Roadmap

This document represents the stable conceptual foundation of FRKP.

---

## SESSION_HISTORY.md

Records major development milestones and project evolution.

Typical contents include:

* Completed Sessions
* Architectural Decisions
* Repository Evolution
* Lessons Learned
* Next Session Planning

This document is append-only.

---

## AI_SESSION_HANDOFF.md

Provides a ready-to-use handoff package for new AI sessions.

Typical contents include:

* Repository Summary
* Current Version
* Mandatory Rules
* Current Priority
* Standard Prompt Template

This document is used whenever a new ChatGPT thread or Codex task begins.

---

# Standard Session Workflow

Every new development session should follow this workflow.

```text
GitHub Repository
        │
        ▼
Pull Latest Changes
        │
        ▼
Read MASTER_SESSION
        │
        ▼
Read SESSION_BOOTSTRAP
        │
        ▼
Read FRKP_CONTEXT
        │
        ▼
Review SESSION_HISTORY
        │
        ▼
Use AI_SESSION_HANDOFF
        │
        ▼
Begin Development
```

---

# Repository Authority

The official source of truth is:

```text
GitHub Repository
https://github.com/kbgkim/frpk
```

All AI-generated work should ultimately be committed to the GitHub repository.

---

# AI Collaboration Model

## ChatGPT

Recommended for:

* Knowledge Engineering
* Financial Domain Analysis
* Formula Design
* Architecture Review
* Documentation Planning
* Review and Decision Support

---

## Codex

Recommended for:

* Repository-wide Refactoring
* Large-scale Document Generation
* Navigation Updates
* Cross-reference Generation
* Validation
* Automation
* Repository Maintenance

---

# Maintenance Guidelines

When updating the Sessions directory:

* Update **MASTER_SESSION.md** whenever the project status changes.
* Append new milestones to **SESSION_HISTORY.md**.
* Revise **SESSION_BOOTSTRAP.md** only when operational rules change.
* Revise **FRKP_CONTEXT.md** only when long-term architecture or philosophy changes.
* Update **AI_SESSION_HANDOFF.md** when startup instructions need revision.

---

# Current Baseline

Repository Version

```text
Version 1.0.0
```

Repository Status

```text
Frozen Baseline
```

Current Development Target

```text
Version 1.1
Bundle-007 — Operational Risk
```

---

# Long-Term Goal

The Sessions framework enables FRKP to be developed continuously across multiple AI conversations, multiple Codex executions, and multiple repository versions without losing project context.

It establishes a sustainable operating model for long-term AI-assisted knowledge engineering.

---

# Revision History

| Version | Date       | Description             |
| ------- | ---------- | ----------------------- |
| 1.0.0   | 2026-06-28 | Initial Sessions README |
