# AI_SESSION_HANDOFF

## Financial Risk Knowledge Platform (FRKP)

---

# Document Information

| Item          | Value                                                        |
| ------------- | ------------------------------------------------------------ |
| Document ID   | FRKP-SESSION-005                                             |
| Document Name | AI Session Handoff                                           |
| Version       | 1.0.0                                                        |
| Status        | Active                                                       |
| Created       | 2026-06-28                                                   |
| Last Updated  | 2026-06-28                                                   |
| Purpose       | Standard handoff document for new ChatGPT and Codex sessions |

---

# 1. Objective

This document provides the minimum required context for any new AI session working on the Financial Risk Knowledge Platform (FRKP).

Its purpose is to enable a new ChatGPT thread or Codex session to continue development without requiring the complete previous conversation history.

---

# 2. Repository

Repository

```text
https://github.com/kbgkim/frpk
```

Primary Branch

```text
main
```

Current Stable Version

```text
Version 1.0.0
```

Repository Status

```text
Frozen Baseline
```

GitHub is the official source of truth.

---

# 3. Read These Documents First

Before performing any work, review the following documents in order.

1. 00_Project_Management/Governance/FRKP-002_AI_OPERATING_MODEL.md
2. 00_Project_Management/Sessions/MASTER_SESSION.md
3. 00_Project_Management/Sessions/PROJECT_STATE.md
4. 00_Project_Management/Sessions/AI_SESSION_HANDOFF.md
5. 00_Project_Management/Sessions/BOOTSTRAP_CODEX.md for Codex sessions, or 00_Project_Management/Sessions/BOOTSTRAP_CHATGPT.md for ChatGPT sessions.

These documents define the durable operating context.

---

# 4. Current Repository Status

Repository Foundation

Completed

Version 1.0

Released

Current Development

Version 1.1

Current Bundle

Bundle-007

Operational Risk

---

# 5. Mandatory Repository Rules

The following rules are mandatory.

* Never rename published document IDs.
* Preserve bundle structure.
* Preserve repository layer structure.
* Follow all FRKP standards.
* Keep Markdown links valid.
* Maintain navigation consistency.
* Preserve backward compatibility.
* Extend the repository incrementally.

---

# 6. Working Principles

The AI should act as:

* Repository Architect
* Knowledge Engineer
* Documentation Reviewer
* Financial Risk Domain Expert

The AI should not behave as a generic Markdown generator.

Every change should improve the repository as a knowledge platform.

---

# 7. ChatGPT Responsibilities

Use ChatGPT for:

* Knowledge design
* Formula explanation
* Architecture design
* Review
* Planning
* Bundle design
* Domain modeling

---

# 8. Codex Responsibilities

Use Codex for:

* Repository-wide edits
* Large document generation
* Navigation updates
* Cross-reference generation
* Validation
* Repository restructuring
* Automation

---

# 9. Session Startup Checklist

Before starting work:

* Pull latest repository.
* Confirm Version.
* Read FRKP-002_AI_OPERATING_MODEL.md.
* Read MASTER_SESSION.
* Read PROJECT_STATE.md.
* Read the appropriate bootstrap document.
* Review current roadmap.
* Confirm target bundle.
* Review existing related documents.
* Verify document numbering.

Only after completing these checks should implementation begin.

---

# 10. Session Completion Checklist

Before ending the session:

* Verify document consistency.
* Verify navigation.
* Verify Markdown links.
* Update MASTER_SESSION if needed.
* Update SESSION_HISTORY if a milestone has been completed.
* Commit with a meaningful Git message.
* Push changes to GitHub.

---

# 11. Current Priority

Current work should focus on:

Bundle-007

Operational Risk

Recommended document order:

```text
RL

↓

KB

↓

AN

↓

FC

↓

MF

↓

IMP

↓

ARCH

↓

BUNDLE
```

---

# 12. AI Prompt Template

The following prompt can be used to start a new ChatGPT or Codex session.

```text
This session continues the Financial Risk Knowledge Platform (FRKP).

Repository:
https://github.com/kbgkim/frpk

Current Version:
1.0.0

Read the following documents before beginning work:

- FRKP-002_AI_OPERATING_MODEL.md
- MASTER_SESSION.md
- PROJECT_STATE.md
- AI_SESSION_HANDOFF.md
- BOOTSTRAP_CODEX.md or BOOTSTRAP_CHATGPT.md

Use GitHub as the authoritative repository.

Follow all FRKP standards.

Preserve all published document IDs.

Continue Version 1.1 development beginning with Bundle-007.
```

---

# 13. Long-Term Goal

The objective of FRKP is to become a comprehensive AI-ready Financial Risk Knowledge Platform covering:

* Financial Regulation
* Risk Management
* Mathematical Models
* Formula Catalog
* System Architecture
* Implementation Guide
* Regulatory Traceability
* Machine-readable Knowledge

Every development session should contribute toward this long-term vision.

## AI Operating Principles

This project follows the governance defined in:

FRKC Repository

GOVERNANCE/FRKC-AI-001_AI_COLLABORATION_PRINCIPLES.md

When conflicts occur, the FRKC governance document takes precedence.

---

# 14. Revision History

| Version | Date       | Description                |
| ------- | ---------- | -------------------------- |
| 1.0.0   | 2026-06-28 | Initial AI Session Handoff |
