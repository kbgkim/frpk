# PLAN-003 - AI Operating Model and Session Resilience Framework

## Document Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-003 |
| Title | AI Operating Model and Session Resilience Framework |
| Status | Completed |
| Category | Governance |
| Secondary Categories | Session Resilience; AI Operations |
| Owner | Codex |
| Bundle | Bundle-007 |
| Related Documents | FRKP-002; PROJECT_STATE.md; BOOTSTRAP_CODEX.md; BOOTSTRAP_CHATGPT.md; MASTER_SESSION.md; AI_SESSION_HANDOFF.md |
| Created | 2026-06-28 |
| Completion Date | 2026-06-28 |

---

# 1. Objective

Establish a durable AI-native operating framework for the FRKC and FRKP dual-repository system, so that Codex, ChatGPT, or future AI sessions can restore project context from repository files without relying on long conversation history.

---

# 2. Scope

Included:

* Create the AI Operating Model.
* Create a machine-readable Project State file.
* Create Codex bootstrap instructions.
* Create ChatGPT bootstrap instructions.
* Add short references from existing session documents.
* Register PLAN-003 in the planning framework.
* Record verification and verdict.

Excluded:

* Bundle-007 domain content changes.
* Evidence Mapping execution.
* FRKC evidence file changes.
* Git commits.
* Document renames.
* FRKP Version 1.0 compatibility changes.

---

# 3. Files Created

* `00_Project_Management/Governance/FRKP-002_AI_OPERATING_MODEL.md`
* `00_Project_Management/Sessions/PROJECT_STATE.md`
* `00_Project_Management/Sessions/BOOTSTRAP_CODEX.md`
* `00_Project_Management/Sessions/BOOTSTRAP_CHATGPT.md`
* `00_Project_Management/Plans/03_history/PLAN-003_AI_OPERATING_MODEL_AND_SESSION_RESILIENCE_FRAMEWORK.md`

---

# 4. Files Modified

* `00_Project_Management/Sessions/MASTER_SESSION.md`
* `00_Project_Management/Sessions/AI_SESSION_HANDOFF.md`
* `00_Project_Management/Plans/PLAN_INDEX.md`
* `00_Project_Management/Plans/active.md`
* `00_Project_Management/Plans/CURRENT_WORK.md`
* `00_Project_Management/Plans/next-session.md`

---

# 5. Design Decisions

* Made repository files, not conversation history, the durable session restoration source.
* Defined Codex as Repository Worker and ChatGPT as Knowledge Editorial Layer.
* Preserved FRKC as the authoritative evidence source and FRKP as the derived publishing platform.
* Added separate bootstrap documents for Codex and ChatGPT because the two roles have different operating boundaries.
* Kept `PROJECT_STATE.md` concise and YAML-style for quick AI parsing.
* Registered the bundle rule that a bundle is a deliverable, not a session boundary.

---

# 6. Restrictions Observed

* Bundle-007 domain content was not modified.
* Evidence Mapping was not performed.
* FRKC evidence files were not changed.
* No commit was made.
* Existing document IDs were preserved.
* No existing documents were renamed.
* FRKP Version 1.0 backward compatibility was preserved.
* New documents are Markdown-native.

---

# 7. Verification Performed

* Verified FRKP branch: `feature/bundle-007-operational-risk`.
* Verified FRKP working tree contains existing modified and untracked files.
* Verified FRKC branch: `main`.
* Verified FRKC working tree contains existing untracked files.
* Read existing session and planning framework documents.
* Confirmed PLAN-001 and PLAN-002 history records exist.
* Scoped edits to governance, session, and planning files.

---

# 8. Remaining Risks

* FRKP working tree remains dirty.
* FRKC working tree remains dirty.
* Some pre-existing session references pointed to older missing files and now require users to follow the new bootstrap order.
* Bundle-007 remains in development and is not frozen.

---

# 9. Recommended Next PLAN ID

Recommended next plan:

```text
PLAN-004 - Bundle-007 Evidence Mapping Readiness
```

PLAN-004 should verify evidence availability and mapping readiness before any further Bundle-007 publication changes.

---

# 10. Verdict

```text
CONDITIONAL GO
```

Reason:

The AI operating model and bootstrap documents are created and linked, and Bundle-007 content was not changed. The verdict remains conditional because both FRKP and FRKC working trees contain modified or untracked files.
