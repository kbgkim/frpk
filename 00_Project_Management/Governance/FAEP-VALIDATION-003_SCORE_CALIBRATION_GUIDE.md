# FAEP-VALIDATION-003 - Score Calibration Guide

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-VALIDATION-003 |
| Document Name | Score Calibration Guide |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-VALIDATION-000; FAEP-VALIDATION-001; FAEP-VALIDATION-002; FRKP_REFERENCE_VALIDATION_REPORT; FAEP_VALIDATION_GAP_ANALYSIS; PLAN-031; PLAN-032 |
| Created | 2026-06-29 |
| Last Updated | 2026-06-29 |
| Plan | PLAN-032 |

---

# 1. Purpose

This guide standardizes how validators calibrate category scores and score confidence when applying FAEP-VALIDATION-001.

It does not change score ranges, weights, category minimums, level mappings, or governance approval rules. It provides practical guidance for recording rationale and avoiding inconsistent score interpretation across FRKP, Risk Platform, IB Platform, and future Business Platforms.

---

# 2. Calibration Principles

1. Use FAEP-VALIDATION-001 as the scoring authority.
2. Preserve all 13 validation categories and weights.
3. Score only from repository evidence or approved validation artifacts.
4. Distinguish specification evidence from implementation evidence.
5. Distinguish framework conformance from general engineering quality.
6. Record category applicability before assigning a score.
7. Assign score confidence separately from the score.
8. Do not use a high total score to override category minimum failures.

---

# 3. Score Range Assessment

| Range | Current Practicality | Calibration Guidance |
| --- | --- | --- |
| 0 | Practical | Use when no usable evidence exists. Do not infer score from platform reputation. |
| 1-2 | Practical | Use for awareness, early draft, or unsupported claims. |
| 3-4 | Practical | Use for developing evidence with material gaps. PLAN-031 Testing score of 4.0 is an example when review evidence exists but automated or repeatable validation evidence is not verified. |
| 5-6 | Practical | Use when minimum category evidence exists and the implementation can be validated at Reference Candidate or early Reference Implementation level. |
| 7-8 | Practical | Use for strong category evidence with clear traceability, but not enough independent audit, automation, or cross-program proof for exemplary status. |
| 9-10 | Practical but requires restraint | Reserve for complete, repeatable, independently reviewable, or certified evidence. Source implementation status alone is not sufficient. |

Conclusion: the score ranges are practical. No range change is recommended.

---

# 4. Weighting Assessment

| Category Group | Current Weights | Assessment |
| --- | ---: | --- |
| Normative foundation: Core Contracts and Standards | 27.0% | Balanced. These categories should remain dominant because they determine FAEP conformance. |
| Structural alignment: Governance and Architecture | 20.0% | Balanced. Governance and architecture are central but should not outweigh Core Contracts and Standards. |
| Knowledge and Traceability | 16.0% | Balanced. PLAN-031 showed these are important differentiators, but not enough evidence exists to justify changing weights. |
| Quality categories: Package Boundaries, Documentation, Testing, ADR Compliance, Platform Isolation, Release and Freeze | 34.0% | Balanced as a group. Some categories need clearer evidence guidance, not new weights. |
| Candidate Contracts | 3.0% | Balanced. Candidate discovery should influence maturity but not dominate conformance scoring. |

Conclusion: category weighting is balanced. No weight change is recommended by PLAN-032.

---

# 5. Calibration Worksheet

Every scored category should record the following fields.

| Field | Description |
| --- | --- |
| Category | FAEP-VALIDATION-000 category. |
| Applicability | Applicable, Partially Applicable, Not Applicable, or Equivalent Evidence. |
| Required Evidence Reviewed | Evidence records used from FAEP-VALIDATION-002. |
| Optional Evidence Reviewed | Additional evidence used to increase confidence or score. |
| Missing Evidence | Evidence gaps that cap score or confidence. |
| Raw Score | 0.0 through 10.0. |
| Weight | Category weight from FAEP-VALIDATION-001. |
| Weighted Contribution | Raw Score multiplied by weight. |
| Score Rationale | Why this score, not the adjacent score above or below. |
| Confidence | High, Medium, or Low. |
| Confidence Rationale | Why the confidence level is appropriate. |
| Level Minimum Impact | Whether the score blocks Level 1, 2, 3, or 4. |
| Calibration Notes | Any judgment calls, equivalence claims, or future review triggers. |

---

# 6. Score Confidence Calibration

| Confidence | Evidence Condition | Use |
| --- | --- | --- |
| High | Required evidence is complete, current, inspectable, and directly supports the score; major judgment calls are absent or resolved. | Appropriate for level assignment when category minimums are met. |
| Medium | Evidence supports the score but has partial automation, indirect proof, limited review history, or unresolved but non-critical gaps. | Appropriate for provisional or normal validation with documented gaps. |
| Low | Evidence is incomplete, narrative-heavy, stale, or difficult to reproduce. | Use when re-assessment is recommended before promotion or certification. |

Confidence does not directly change the numeric score. It changes how strongly the score can support promotion, certification, and cross-program comparison.

---

# 7. Category Calibration Notes

| Category | Calibration Note |
| --- | --- |
| Core Contracts | Separate source specification, self-implementation, and independent implementation. A source implementation may score strongly, but specification-only contracts should limit exemplary scoring. |
| Standards | Score applicable standards only, but record not-applicable rationale. Automated checks raise confidence, not the weight. |
| Governance | Evaluate decision authority, quality gates, escalation, review cadence, and change control. Independent governance can qualify through explicit equivalence notes. |
| Knowledge | Do not require FRKC implementation for every platform. Require clear knowledge architecture or compatibility rationale. |
| Traceability | Distinguish traceability model from executed traceability records. High scores need evidence chains, not only framework descriptions. |
| Architecture | Engine mapping may include not-applicable engines. Penalize unexplained gaps, not legitimate platform specialization. |
| Package Boundaries | Directory conventions, module rules, package rules, and component boundaries can all qualify. Automated enforcement increases confidence and score ceiling. |
| Documentation | Avoid double counting traceability. Documentation score covers completeness, navigability, and standards alignment. Traceability score covers evidence chains. |
| Testing | For document-first platforms, deterministic checks and governed review protocols may qualify as testing evidence. For software-first platforms, automated unit, integration, and architecture tests should be expected. |
| ADR Compliance | ADR existence is not enough for high scores; coverage and format compliance must be evaluated. |
| Candidate Contracts | Keep Candidate Contracts, Candidate Capabilities, and backlog observations separate. Cross-program evidence is needed for exemplary scores. |
| Platform Isolation | Evaluate inappropriate coupling and independent evolution, not physical repository separation alone. |
| Release and Freeze | Separate frozen historical baselines from current release readiness. Unresolved blockers should be visible in score rationale. |

---

# 8. Calibration Assessment from PLAN-031

| Question | Finding |
| --- | --- |
| Are score ranges practical? | Yes. FRKP and Risk Platform results landed in distinct maturity bands with explainable category minimum effects. |
| Are category weights balanced? | Yes. No evidence supports changing weights. |
| Is additional guidance needed? | Yes. Evidence record structure, applicability notes, score rationale, and confidence calibration are needed. |
| Should FAEP-VALIDATION-001 be amended now? | No. PLAN-032 supports supplemental guidance only. |
| Should prior FRKP scores change? | No. PLAN-031 score remains valid: 76.3/100, Level 2 due category minimums. |

---

# 9. Recommended PLAN-033

Recommended PLAN-033: FAEP Validation Evidence Packet Pilot.

Objective: apply FAEP-VALIDATION-002 and this calibration guide to the PLAN-031 FRKP scorecard and produce a concrete evidence packet example.

Acceptance criteria:

- All 13 categories have evidence records.
- All 13 categories have calibration worksheet entries.
- Confidence rationale is recorded for every category.
- Existing PLAN-031 score and level are either reaffirmed or any proposed adjustment is documented as a recommendation only.
- No framework, score model, Foundation, Standard, Core Contract, Bundle, Publication, implementation, release, or repository migration changes occur.

---

# 10. Preservation Statement

This guide did not modify:

- FAEP Foundation.
- Core Contracts.
- Standards.
- Validation Framework.
- Score Model.
- Execution Model.
- Traceability Framework.
- Editorial Contracts.
- Bundle content.
- Publication content.

This guide did not perform:

- Implementation.
- Release.
- Repository migration.
- Candidate promotion.

---

# 11. Final Verdict

CONDITIONAL GO — Evidence Model Established with Calibration Recommendations

---

## Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-29 | Initial Score Calibration Guide (PLAN-032) |

