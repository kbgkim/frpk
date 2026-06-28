# SESSION_BOOTSTRAP

## Financial Risk Knowledge Platform (FRKP)

---

# Document Information

| Item          | Value                                                     |
| ------------- | --------------------------------------------------------- |
| Document ID   | FRKP-SESSION-002                                          |
| Document Name | Session Bootstrap                                         |
| Version       | 1.0.0                                                     |
| Status        | Active                                                    |
| Created       | 2026-06-28                                                |
| Last Updated  | 2026-06-28                                                |
| Purpose       | Standard bootstrap for all new ChatGPT and Codex sessions |

---

# 1. Purpose

This document defines the mandatory operating rules for every new AI session working on the Financial Risk Knowledge Platform (FRKP).

Every new ChatGPT thread and every Codex task shall use this document as the initial project bootstrap.

The objective is to ensure continuity, consistency, and repository stability across long-term development.

---

# 2. Repository

Official Repository

```text
https://github.com/kbgkim/frpk
```

Repository Branch

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

The GitHub repository is the authoritative source for all future work.

---

# 3. Required Reading Order

Before performing any work, review the following documents in order.

1. MASTER_SESSION.md
2. SESSION_BOOTSTRAP.md
3. FRKP_CONTEXT.md
4. Current Roadmap
5. Current Bundle documents

No implementation shall begin before understanding the current project status.

---

# 4. Repository Philosophy

FRKP is a **Knowledge Platform**, not merely a Markdown document collection.

All work shall contribute to one or more of the following goals:

* Knowledge Organization
* Regulatory Traceability
* Formula Standardization
* Architecture Consistency
* AI Readability
* Long-term Maintainability

---

# 5. Repository Architecture

The repository follows an eight-layer architecture.

1. Reference Library
2. Knowledge Base
3. Analysis
4. Formula Catalog
5. Mathematical Foundation
6. Implementation Guide
7. Architecture
8. Bundle Review

Every new knowledge domain shall follow this layer order.

---

# 6. Bundle Development Model

Each Bundle represents one independent knowledge domain.

A complete bundle normally consists of:

```text
RL
KB
AN
FC
MF
IMP
ARCH
BUNDLE
```

Bundles shall be expanded incrementally.

Do not modify completed bundles unless correction is required.

---

# 7. Mandatory Standards

Every document shall comply with:

* FRKP-DOC-001
* FRKP-ID-001
* FRKP-FORM-001
* FRKP-ARCH-001
* FRKP-IMP-001
* FRKP-BUNDLE-001
* FRKP-TERM-001
* FRKP-ABBR-001
* FRKP-SYM-001

Violation of these standards is not permitted.

---

# 8. Document Rules

Every document shall:

* have a unique Document ID
* use immutable identifiers
* follow repository naming conventions
* preserve backward compatibility
* include revision history
* maintain cross-reference consistency
* remain technology neutral where appropriate

Published document IDs shall never be renamed.

---

# 9. Git Workflow

Standard workflow:

```text
GitHub
        │
        ▼
Pull Latest
        │
        ▼
Read MASTER_SESSION
        │
        ▼
Implement
        │
        ▼
Review
        │
        ▼
Commit
        │
        ▼
Push
```

Main branch shall always remain stable.

Major work should be performed using feature branches.

---

# 10. AI Operating Principles

When assisting with FRKP:

* Preserve repository consistency.
* Never introduce duplicate document IDs.
* Prefer extending existing structures over creating parallel ones.
* Recommend phased implementation.
* Avoid unnecessary repository restructuring.
* Maintain compatibility with previous releases.

The AI should act as a repository architect rather than a document generator.

---

# 11. Codex Usage Policy

Codex should be used for:

* Repository-wide refactoring
* Large-scale document generation
* Cross-reference updates
* Navigation generation
* Validation
* Consistency checks
* Automation tasks

ChatGPT should be used for:

* Knowledge design
* Domain modeling
* Formula explanation
* Architecture review
* Planning
* Review and decision support

---

# 12. Session Start Checklist

Before beginning work:

* Pull latest repository changes.
* Confirm current version.
* Review MASTER_SESSION.md.
* Confirm target bundle.
* Verify document numbering.
* Check for existing related documents.
* Review applicable standards.

Only then begin implementation.

---

# 13. Session Completion Checklist

Before ending a session:

* Verify document consistency.
* Verify navigation.
* Verify Markdown links.
* Update MASTER_SESSION if required.
* Record significant progress in SESSION_HISTORY.
* Commit changes with a meaningful Git message.
* Push changes to GitHub.

---

# 14. Versioning Policy

Version 1.0

Repository Foundation

Version 1.1+

Incremental Bundle Expansion

Version 2.x

Major Repository Evolution

Every release shall preserve compatibility with previous document identifiers.

---

# 15. Long-Term Vision

FRKP is intended to evolve into a comprehensive Financial Risk Knowledge Platform that supports:

* Financial professionals
* System architects
* Software developers
* Regulatory interpretation
* AI-assisted knowledge retrieval
* Machine-readable financial knowledge

Repository quality and long-term maintainability take precedence over short-term productivity.

---

# 16. Bootstrap Statement

Every new ChatGPT thread or Codex task should assume the following:

* The repository already exists.
* Version 1.0 is frozen.
* GitHub is the authoritative source.
* Existing standards are mandatory.
* Existing document IDs are immutable.
* New work shall extend the repository without breaking compatibility.

This document establishes the baseline operating context for all future FRKP development.

---

# 17. Revision History

| Version | Date       | Description               |
| ------- | ---------- | ------------------------- |
| 1.0.0   | 2026-06-28 | Initial Session Bootstrap |
