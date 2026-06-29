# FRKP-002 AI Operating Model

## Financial Risk Knowledge Platform (FRKP)

---

# Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-002 |
| Document Name | AI Operating Model |
| Version | 1.0.0 |
| Status | Active |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Purpose | Define the AI-native operating model for FRKC and FRKP work |

---

# 1. Project Philosophy

FRKP is an evidence-driven publishing platform for financial risk knowledge.

The project follows these principles:

* Knowledge grows before publication.
* Evidence precedes publication.
* Publishing is derived from authoritative evidence.
* AI assists execution, review, and editorial reasoning.
* Human review remains the authority for acceptance, freeze, and release.
* Repository state is the durable source of project continuity.
* Long conversation history is not required to resume work.

---

# 2. FRKC Role

FRKC is the Knowledge Corpus and authoritative evidence source.

FRKC is responsible for:

* Source evidence
* Evidence metadata
* Semantic extraction
* Canonical terminology
* Knowledge graph structures
* Evidence-to-publication mappings
* Knowledge certification artifacts

FRKC answers the question:

```text
What does the evidence support?
```

---

# 3. FRKP Role

FRKP is the Publishing Platform derived from FRKC evidence.

FRKP is responsible for:

* Reference Library documents
* Knowledge Base documents
* Analysis documents
* Formula Catalog documents
* Mathematical Foundation documents
* Implementation Guide documents
* Architecture documents
* Bundle review and release records
* User-facing publication structure

FRKP answers the question:

```text
How should evidence-backed knowledge be published?
```

---

# 4. FRKC and FRKP Relationship

FRKC and FRKP are separate repositories with separate responsibilities.

The operating relationship is:

```text
FRKC evidence
        |
        v
FRKC metadata and semantic structures
        |
        v
FRKC publishing mapping
        |
        v
FRKP publication documents
        |
        v
Human-reviewed release
```

FRKC is authoritative for evidence.

FRKP is authoritative for published platform documents.

FRKP must not invent domain claims when FRKC evidence is required. FRKC must not be treated as a formatting or publishing repository.

---

# 5. AI and Human Roles

## Codex

Codex acts as the Repository Worker.

Codex is responsible for:

* Reading repository state
* Editing files according to an active plan
* Updating indexes, handoffs, and governance references
* Running targeted validation
* Reporting git state and modified files
* Avoiding domain editorial reasoning unless explicitly requested
* Avoiding bundle content changes unless the active plan permits them

## ChatGPT

ChatGPT acts as the Knowledge Editorial Layer.

ChatGPT is responsible for:

* Explaining concepts
* Reviewing logical consistency
* Improving educational clarity
* Supporting bundle design
* Supporting domain interpretation
* Preparing editorial guidance for Codex when repository edits are required

ChatGPT should avoid large-scale repository edits and should delegate repository-worker tasks to Codex.

## Human Reviewer

The Human Reviewer is responsible for:

* Approving plans
* Approving domain interpretations
* Accepting or rejecting bundle outputs
* Freezing releases
* Resolving governance conflicts
* Deciding whether a CONDITIONAL GO may proceed

---

# 6. Evidence-Driven Publishing Workflow

Evidence-driven publishing follows this order:

1. Identify the publishing need.
2. Verify applicable FRKC evidence.
3. Confirm metadata, terminology, and mappings.
4. Draft or update FRKP publication documents.
5. Validate document IDs, links, navigation, and standards.
6. Review for evidence alignment and editorial quality.
7. Record bundle or plan status.
8. Human reviewer approves release or freeze.

Rule:

```text
Evidence precedes publication.
```

---

# 7. Bundle Lifecycle

A bundle is a deliverable, not a session boundary.

Bundle work may span multiple AI sessions and multiple plans. A session can start, pause, or resume within a bundle without redefining the bundle itself.

Bundle lifecycle:

1. Identify bundle scope.
2. Confirm FRKC evidence availability.
3. Create or update layer documents.
4. Validate cross-layer consistency.
5. Produce bundle review.
6. Resolve findings.
7. Freeze or release when approved.

Rule:

```text
Bundle is a deliverable, not a session boundary.
```

---

# 8. Plan Lifecycle

A plan is the execution unit for repository work.

Plan lifecycle:

1. Register the plan.
2. Execute the scoped work.
3. Avoid out-of-scope repository changes.
4. Record files created and modified.
5. Record verification performed.
6. Capture risks and recommended next plan.
7. Close the plan in history.

Plans must not silently expand into unrelated bundle work.

---

# 9. Git and Repository Operating Principles

Repository operations follow these principles:

* Treat GitHub as the shared remote source of truth.
* Verify branch and working tree state before work.
* Do not commit unless explicitly requested.
* Do not reset, rename, or delete documents without explicit authorization.
* Preserve published document IDs.
* Preserve backward compatibility with FRKP Version 1.0.
* Keep FRKC and FRKP responsibilities separate.
* Prefer targeted edits over broad rewrites.
* Record dirty working tree conditions in plan history.

---

# 10. Session Restoration Principles

Every AI session should restore context from repository files, not conversation memory.

Standard restoration order:

1. `00_Project_Management/Governance/FRKP-002_AI_OPERATING_MODEL.md`
2. `00_Project_Management/Sessions/MASTER_SESSION.md`
3. `00_Project_Management/Sessions/PROJECT_STATE.md`
4. `00_Project_Management/Sessions/AI_SESSION_HANDOFF.md`
5. `00_Project_Management/Plans/CURRENT_WORK.md`
6. `00_Project_Management/Plans/active.md`
7. `00_Project_Management/Plans/PLAN_INDEX.md`

Codex sessions should also read:

```text
00_Project_Management/Sessions/BOOTSTRAP_CODEX.md
```

ChatGPT sessions should also read:

```text
00_Project_Management/Sessions/BOOTSTRAP_CHATGPT.md
```

---

# 11. Core Operating Rules

The following rules are mandatory:

```text
Bundle is a deliverable, not a session boundary.
Evidence precedes publication.
Knowledge grows in FRKC; documents grow in FRKP.
```

These rules apply across Codex, ChatGPT, and Human Reviewer workflows.
