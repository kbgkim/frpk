# FAEP-BASELINE-001 - Program Transition Guide

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-BASELINE-001 |
| Document Name | Program Transition Guide |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-BASELINE-000; FAEP-000; FAEP-001; FAEP-002; FAEP-FOUNDATION-001; FAEP-CONTRACT-000; FAEP-CONTRACT-001; FAEP-VALIDATION-000; FAEP-VALIDATION-002; FAEP-AI-000; PLAN-034 |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |
| Plan | PLAN-034 |

---

# 1. Purpose

This guide defines the FAEP Program transition from framework development to operational maintenance.

The transition path is:

```text
Framework Development
    -> Reference Validation
    -> Operational Baseline
    -> Program Maintenance
```

This guide does not freeze future evolution. It defines how operational use proceeds while the Candidate -> Validation -> Core lifecycle remains active.

---

# 2. Phase Definitions

| Phase | Purpose | Entry Signal | Exit Signal |
| --- | --- | --- | --- |
| Framework Development | Define Foundation, governance, standards, contracts, validation, traceability, execution, workflow, and publication frameworks. | FAEP Core and governance documents under active definition. | Framework artifacts created and internally consistent. |
| Reference Validation | Execute the framework against real platforms. | Validation framework and score model available. | FRKP and Risk Platform validation completed without framework redesign. |
| Operational Baseline | Certify the current Foundation for operational project use. | Cross-platform validation complete; IB not yet validated. | Program operating priorities and change policy established. |
| Program Maintenance | Run projects, collect evidence, manage Candidates, and perform governed Foundation releases when justified. | Operational Baseline certified. | Continuing state; exits only for major governance redesign or Foundation release cycle. |

---

# 3. Responsibility Model

| Phase | FAEP Program Governance Board | FAEP Architecture Board | Platform Leads | AI / Automation Providers |
| --- | --- | --- | --- | --- |
| Framework Development | Approves program scope and governance authority | Defines architecture, standards, contracts, and validation framework | Provide domain constraints and reference evidence | Draft, review, edit, and validate under plan scope |
| Reference Validation | Confirms validation targets and accepts verdicts | Executes framework interpretation and scoring | Supply repository evidence and platform context | Support evidence review and scoring records |
| Operational Baseline | Accepts transition into operational use | Certifies baseline and change policy | Adopt baseline for project planning | Operate by capability, not provider identity |
| Program Maintenance | Oversees roadmap, escalations, and release decisions | Maintains Candidate lifecycle and Foundation evolution | Execute platform work and provide validation evidence | Assist with governed execution, validation, and documentation |

---

# 4. Operating Rules

| Rule | Description |
| --- | --- |
| Repository Source of Truth | Repository artifacts are authoritative. Prior conversation memory is not authority. |
| Baseline Stability | Operational Baseline artifacts are stable references for project use. |
| Candidate First | New concepts enter as Candidates or backlog items before Core consideration. |
| Validation Before Promotion | Promotion requires cross-program validation evidence or approved governance exception. |
| No Direct Foundation Modification | Avoid direct edits to Foundation artifacts outside approved release or exception paths. |
| Platform Independence | Reference Implementations evolve independently and provide evidence back to FAEP. |
| Provider Independence | GPT, Codex, OpenCode, and future tools are providers only; capabilities govern responsibility. |

---

# 5. Maintenance Workflow

Program Maintenance proceeds through this recurring workflow:

```text
Operational Need
    -> Plan Registration
    -> Baseline Applicability Check
    -> Candidate / Backlog Classification
    -> Platform Execution or Validation
    -> Evidence Record
    -> Governance Review
    -> Maintain / Promote / Defer / Reject
```

This workflow keeps operational work moving while preserving the Foundation boundary.

---

# 6. Candidate Handling

| Candidate Status | Meaning | Maintenance Action |
| --- | --- | --- |
| Validated | Proven useful in current operational evidence, but not promoted to Core | Keep active; gather cross-program evidence |
| Needs Validation | Supported by one platform or limited evidence | Assign future validation target before promotion discussion |
| Future Validation | Potentially valuable but not operationally urgent | Keep in backlog until project demand exists |

No Candidate is promoted by this guide.

---

# 7. Roadmap Alignment

Operational maintenance should prioritize:

1. Bundle-007 Publication Completion.
2. FRKP v1.1 Release.
3. Risk Platform Evolution.
4. IB Platform Bootstrap.
5. Future Business Platforms.

These priorities are operational sequencing, not Foundation redesign.

---

# 8. PLAN-035 Recommendation

Recommended PLAN-035:

| Field | Recommendation |
| --- | --- |
| Plan ID | PLAN-035 |
| Title | Bundle-007 Publication Completion and FRKP v1.1 Release Readiness |
| Objective | Resolve the deferred Bundle-007 publication completion and FRKP v1.1 release blocker items under the Operational Baseline without modifying FAEP Foundation artifacts or promoting Candidates. |
| Scope | Bundle-007 publication completion checks, FRKP-DOC-100 synchronization, VERSION/CHANGELOG/release-note readiness, and release-candidate state update. |
| Constraints | No Foundation redesign; no Core promotion; no repository migration; no publication beyond readiness artifacts unless explicitly scoped. |

---

# 9. Preservation Statement

This guide did not modify:

- Foundation.
- Core Contracts.
- Standards.
- Validation Framework.
- Execution Model.
- Traceability Framework.
- Workflow Framework.
- Publication Framework.

This guide did not perform:

- Implementation.
- Repository migration.
- Release.
- Candidate promotion.

---

# 10. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Program Transition Guide created by PLAN-034 |
