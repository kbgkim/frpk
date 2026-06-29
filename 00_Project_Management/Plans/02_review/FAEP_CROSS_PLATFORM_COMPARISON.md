# FAEP Cross-Platform Comparison

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-CROSS-PLATFORM-COMPARISON-033 |
| Title | FAEP Cross-Platform Comparison |
| Status | Review |
| Owner | FAEP Architecture Board |
| Plan | PLAN-033 |
| Created | 2026-06-29 |
| Scope | Validation only |

---

# 1. Purpose

This document compares FRKP and the Risk Platform using the existing FAEP Validation Framework and score model. It does not redefine categories, weights, levels, contracts, standards, or candidate lifecycle rules.

---

# 2. Platform Profiles

| Dimension | FRKP | Risk Platform |
| --- | --- | --- |
| Platform type | Publishing-oriented knowledge and governance reference implementation | Execution-oriented Spring Boot risk/formula platform |
| Primary evidence mode | Governance documents, standards, traceability, publication workflow | Source code, tests, runtime artifacts, PLAN records, architecture governance |
| FAEP relationship | First FAEP Reference Implementation | Independent platform validated against FAEP |
| Validation level | Level 2 - Reference Implementation | Level 1 - Reference Candidate |
| Normalized score | 76.3 / 100 | 65.0 / 100 |
| Score confidence | Medium | High for execution evidence; Medium for FAEP conformance evidence |

---

# 3. Category-by-Category Comparison

| Category | FRKP Score | Risk Score | Comparison |
| --- | ---: | ---: | --- |
| Core Contracts | 8.0 | 5.0 | FRKP satisfies the broad FAEP contract model as source implementation. Risk strongly validates execution contracts but has partial coverage of publishing/knowledge/document contracts. |
| Standards | 9.0 | 4.0 | FRKP is FAEP-native. Risk has mature local standards but not FAEP standard conformance. |
| Governance | 8.0 | 6.0 | FRKP aligns directly to FAEP-002. Risk has strong PLAN governance, but it is independent and requires equivalence mapping. |
| Knowledge | 9.0 | 4.0 | FRKP implements FRKC/knowledge architecture. Risk has technical docs and standards but no proven FRKC compatibility. |
| Traceability | 7.0 | 8.0 | FRKP has strong governance traceability. Risk has stronger implementation-backed runtime/audit/PLAN traceability. |
| Architecture | 8.0 | 7.0 | FRKP defines the FAEP engine model. Risk validates execution-oriented engine subsets. |
| Package Boundaries | 5.0 | 9.0 | FRKP uses directory conventions. Risk has automated ArchUnit/module/package enforcement. |
| Documentation | 9.0 | 8.0 | Both are strong. FRKP is more FAEP-standardized; Risk is more software-operations focused. |
| Testing | 4.0 | 9.0 | FRKP has review evidence but no verified automated test suite. Risk has recent build, module test, architecture test, and benchmark compile evidence. |
| ADR Compliance | 7.0 | 5.0 | FRKP uses FAEP ADR governance. Risk has ADR/review decisions but not broad FAEP-STD-005 format coverage. |
| Candidate Contracts | 7.0 | 9.0 | FRKP registers and governs candidates. Risk supplies stronger implementation evidence for several candidates. |
| Platform Isolation | 8.0 | 9.0 | Both are isolated. Risk is physically and operationally independent from FRKP/FRKC. |
| Release and Freeze | 7.0 | 8.0 | FRKP has FAEP freeze evidence with V1.1 blockers. Risk has strong release snapshot and health revalidation evidence, but not FAEP-STD-006 format. |

---

# 4. Shared Capabilities

| Capability | FRKP Evidence | Risk Evidence |
| --- | --- | --- |
| Governance execution model | FAEP-002, PLAN history, execution model | PLAN_INDEX, completed PLAN records, repository health plans |
| Traceability | FRKP traceability scaffold, evidence-driven publishing | Formula audit trace, resolution audit, governance evidence, PLAN traceability |
| Release lifecycle | Foundation freeze policy, Bundle-007 freeze, release blockers | V6.5 lockdown, release snapshots, repository health closure |
| Documentation portal | Governance/plan/review structure and master indexes | `docs/README.md`, calculator standards, architecture docs |
| Candidate discovery | Candidate contract and capability registries | Mature observed patterns supplying candidate evidence |
| Platform isolation | FRKP platform boundary and downstream isolation | Independent repository, no runtime dependency on FRKP/FRKC |
| Architecture decision practice | FAEP ADR registry and architecture documents | ADR and review-plan decision records |

---

# 5. Capabilities Present in Risk but Absent or Weaker in FRKP

| Capability | Risk Maturity | FRKP State |
| --- | --- | --- |
| Automated package boundary enforcement | Strong to exemplary | Convention-based; no verified automation |
| Automated unit/integration/architecture testing | Strong to exemplary | Review evidence exists; automated suite not verified |
| Runtime compiled execution plan | Mature implementation evidence | Not applicable / absent |
| Formula compiler pipeline | Mature implementation evidence | Not applicable / absent |
| Deterministic runtime execution | Mature implementation evidence | Conceptual execution model, not formula runtime |
| Runtime audit trace | Mature implementation evidence | Publishing/evidence traceability rather than runtime execution trace |
| Formula release snapshots | Mature implementation evidence | Release/freeze documentation, not formula runtime snapshotting |
| Governance evidence store/query/reporting/KPI | Mature implementation evidence | Governance documents and validation reports; no equivalent runtime evidence store |
| Shadow rollout and migration controls | Mature implementation evidence | Candidate-level concept only |
| Benchmark guard infrastructure | Present | Not verified |

---

# 6. Capabilities Present in FRKP but Absent or Weaker in Risk

| Capability | FRKP Maturity | Risk State |
| --- | --- | --- |
| FAEP-native standards conformance | Strong to exemplary | Independent local conventions |
| FRKC knowledge operating system compatibility | Strong | Not established |
| Publishing workflow | Strong | Not applicable / absent |
| Bundle lifecycle and freeze governance | Strong | PLAN-based lifecycle; no FAEP bundle model |
| Master document governance | Strong | Docs portal exists but not FAEP document standard |
| FAEP ADR registry | Strong | Local ADR/review records only |
| Candidate governance registry | Strong | Supplies candidate evidence but does not govern FAEP registry |
| Evidence-driven publishing model | Strong | Runtime/governance evidence model differs |
| Navigation/cross-reference standards | Strong | Local docs portal and source-of-truth notes; no FAEP navigation standard adoption |

---

# 7. Candidate Capabilities Discovered or Strengthened

No Candidate was promoted. The following capabilities were strengthened as candidate evidence through cross-platform validation:

| Candidate Capability | Source Strength | Cross-Platform Observation |
| --- | --- | --- |
| PLAN Execution | FRKP and Risk | Both platforms use plan records as operational traceability, but with different governance formats. |
| Architecture Enforcement | Risk | Risk demonstrates automated enforcement that FRKP lacks; candidate remains useful for Core evolution. |
| Evidence Model Equivalence | FRKP and Risk | FRKP validates document-first evidence; Risk validates software/runtime evidence. |
| Runtime Execution Evidence | Risk | Risk shows execution evidence patterns not represented by FRKP. |
| Release Snapshot Evidence | Risk | Formula snapshotting provides a lifecycle pattern distinct from FRKP freeze certificates. |
| Governance Evidence Reporting | Risk | Governance evidence store/query/reporting/KPI may inform future FAEP evidence engine design. |
| Documentation Source-of-Truth Notes | FRKP and Risk | Both platforms explicitly define document and plan sources of truth. |

---

# 8. Framework Practicality Assessment

| Question | Result |
| --- | --- |
| Can the same 13 categories evaluate both platforms? | Yes. No category had to be redefined. |
| Can the same score model distinguish maturity shapes? | Yes. FRKP scores higher in FAEP conformance; Risk scores higher in implementation automation. |
| Do category minimums remain useful? | Yes. Risk's total score reaches Level 2 range, but Core Contracts and Standards correctly block Level 2 classification. |
| Does the evidence model support both platform types? | Yes. Document-first and software-first evidence both fit the evidence schema. |
| Does calibration guidance remain useful? | Yes. It prevents conflating general software maturity with FAEP conformance. |
| Is framework revision required now? | No. Evidence packet discipline and equivalence mapping are sufficient next improvements. |

---

# 9. Improvement Recommendations

| Recommendation | Type |
| --- | --- |
| Require an evidence packet for every future cross-platform validation. | Process improvement |
| Add explicit applicability notes for execution-only, publishing-only, and knowledge-only categories. | Calibration improvement |
| Keep FAEP conformance scoring separate from general engineering excellence. | Calibration improvement |
| Do not promote candidate patterns until cross-program validation and governance review are complete. | Governance discipline |
| Consider a future evidence-engine candidate based on Risk's runtime and governance evidence patterns. | Candidate observation only |

---

# 10. Final Verdict

CONDITIONAL GO — Cross-Platform Validation Completed with Improvement Recommendations
