# PLAN-020 — FAEP Capability Discovery Using Reference Implementations

## Plan Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-020 |
| Title | FAEP Capability Discovery Using Reference Implementations |
| Status | Completed |
| Category | Capability Discovery; Governance Definition |
| Owner | FAEP Architecture Board |
| Repository | https://github.com/kbgkim/frpk |
| Branch | feature/bundle-007-operational-risk |
| Related Documents | FAEP-CAP-000; FAEP-CAP-001; FAEP-FOUNDATION-000; FAEP-FOUNDATION-001; FAEP-VALIDATION-000; FAEP-VALIDATION-001; FAEP-CONTRACT-000; FAEP-CONTRACT-001; FRKP-003; FRKP-004; FRKP-005; FAEP-000; FAEP-001; FAEP-002; FAEP-STD-000 through FAEP-STD-006; FAEP-ADR-000; FRKP-002; FRKP-FRKC-001; FRKP-FREEZE-001; FRKP-DOC-100; PLAN-001 through PLAN-019; PLAN_STANDARD.md; PLAN_INDEX.md; active.md; CURRENT_WORK.md; next-session.md; PROJECT_STATE.md |
| Created | 2026-06-28 |
| Completed | 2026-06-28 |

---

## Executive Summary

PLAN-020 performs **Capability Discovery** — not Capability Design — across the three current FAEP Reference Implementations: FRKC (Knowledge Platform), FRKP (Publishing Platform), and Risk Platform (Execution Platform).

The FAEP Foundation v1.0 has been declared frozen. Per FAEP-FOUNDATION-001, future Foundation evolution shall originate from validated Reference Implementations. PLAN-020 extracts only those capabilities that are already demonstrated by actual implementations, without inventing new capabilities or creating Capability Standards.

**Key Results:**

- **35 Candidate Capabilities** discovered across 4 domains (Knowledge, Publishing, Execution, Governance).
- **9 Backlog capabilities** identified as speculative or future-phase (primarily AI-Ready domain).
- **3 P1-Critical capability groups** recommended for cross-program validation.
- **PLAN-021** scoped as Cross-Program Candidate Validation.

**No Core Contracts, Standards, Specifications, frozen artifacts, or repository structure were modified.**

**Verdict: GO — Candidate Capabilities Discovered.**

---

## 1. Objective

Discover capabilities that already exist across current Reference Implementations (FRKC, FRKP, Risk Platform). Do NOT invent new capabilities. Extract only those capabilities demonstrated by actual implementations. Classify them as Candidate Capabilities in a governed registry.

---

## 2. Scope

### In Scope

- Capability Discovery from FRKC Knowledge Platform.
- Capability Discovery from FRKP Publishing Platform.
- Capability Discovery from Risk Platform (Execution Platform).
- Capability classification by domain (Knowledge, Publishing, Execution, Governance, AI-ready).
- Provider / Consumer mapping for each capability.
- Duplicate and overlap analysis.
- Discovery vs. Speculation analysis.
- Validation priority recommendations.
- PLAN-021 recommendation.

### Out of Scope

- Capability Standard creation.
- Capability Design.
- Core Contract modification.
- Standard modification.
- Implementation.
- Code.
- Repository migration.
- Releases.
- Commits.

---

## 3. Constraints

- Architecture and analysis only.
- No Capability Standards.
- No implementation.
- No repository migration.
- Preserve FAEP Foundation v1.0 frozen artifacts.
- Preserve all Core Contracts, Standards, Specifications, and governance documents.

---

## 4. Source of Truth

Source priority used:

1. FRKC Knowledge Operating System Specification (FRKP-005) — for FRKC capabilities.
2. FAEP Core Platform Specification (FRKP-004) — for FRKP capabilities and engine model.
3. FAEP Platform Validation Using Risk Platform (PLAN-016) — for Risk Platform capabilities.
4. FAEP Contract Lifecycle and Candidate Validation (FAEP-CONTRACT-000, FAEP-CONTRACT-001).
5. FAEP Foundation Freeze and Evolution Policy (FAEP-FOUNDATION-000, FAEP-FOUNDATION-001, FAEP-FOUNDATION-002).
6. FAEP Validation Framework (FAEP-VALIDATION-000, FAEP-VALIDATION-001).
7. FAEP Standards (FAEP-STD-000 through FAEP-STD-006).
8. FAEP Program Governance Documents (FAEP-000, FAEP-001, FAEP-002).
9. FAEP Architecture Decision Registry (FAEP-ADR-000).
10. FRKP Evidence-Driven Publishing Workflow (FRKP-FRKC-001).
11. FRKP AI Operating Model (FRKP-002).
12. FRKP Master Document Index (FRKP-DOC-100).

---

## 5. Discovery Methodology

### 5.1 Reference Implementation Analysis

Each Reference Implementation was analyzed for demonstrated capabilities:

| Implementation | Repository | Analysis Method | Key Source Documents |
| --- | --- | --- | --- |
| FRKC | github.com/kbgkim/frkp-knowledge | Knowledge corpus structure, object contracts, metadata | FRKP-005 |
| FRKP | github.com/kbgkim/frpk | Publishing workflow, bundle lifecycle, governance | FRKP-004, FRKP-FRKC-001, FRKP-002 |
| Risk Platform | github.com/kbgkim/risk | Codebase structure, compiler architecture, governance | PLAN-016 |

### 5.2 Capability Extraction Protocol

1. Identify a feature, pattern, or process demonstrated by the implementation.
2. Verify the capability is not already fully specified by a Core Contract or Standard.
3. Map the capability to a Reference Implementation component.
4. Classify by domain.
5. Identify providers and consumers.
6. Compare against other discovered capabilities (overlap detection).
7. If speculative or future-phase, classify as Backlog, not Candidate.

### 5.3 Exclusion Criteria

Capabilities were excluded from the registry when:

- They are already fully specified by FAEP Core Contracts (e.g., standard contract compliance).
- They are implementation-specific internals with no cross-program relevance.
- They exist only as architecture specifications with no demonstrated implementation.

---

## 6. Discovery Results

### 6.1 Knowledge Domain Discoveries (from FRKC)

FRKC demonstrates capabilities in canonical knowledge management, evidence handling, terminology, classification, layering, cross-referencing, metadata, and versioning. These capabilities are production-grade in the FRKC knowledge corpus (v0.1, certified with observations).

**8 Candidate Capabilities discovered** in the Knowledge domain.

### 6.2 Publishing Domain Discoveries (from FRKP)

FRKP demonstrates capabilities in evidence-driven publishing, bundle lifecycle management, document authoring, navigation, AI agent orchestration, session management, freeze certification, and archiving. These capabilities were validated through Bundle-007 execution.

**8 Candidate Capabilities discovered** in the Publishing domain.

### 6.3 Execution Domain Discoveries (from Risk Platform)

Risk Platform demonstrates 14 production-grade execution capabilities including DSL compilation, deterministic runtime, formula governance, execution plans, execution modes, governance guards, PLAN-based execution, architecture enforcement, release management, evidence-gated promotion, dependency analysis, variable resolution, codec serialization, precision governance, and operator review.

**14 Candidate Capabilities discovered** in the Execution domain.

### 6.4 Governance Domain Discoveries (Cross-cutting)

PLAN governance model, architecture decision records, contract lifecycle governance, foundation freeze/evolution, and reference implementation validation are demonstrated by FAEP governance or by FRKP/Risk Platform patterns.

**5 Candidate Capabilities discovered** in the Governance domain.

### 6.5 AI-Ready Domain

All AI-Ready capabilities (RAG corpus, semantic retrieval, context assembly, citations, knowledge graph query) remain in Future Phases for FRKC. These are recorded as Backlog, not Candidates.

**0 Candidate Capabilities** in the AI-Ready domain.
**5 Backlog capabilities** recorded.

---

## 7. Provider / Consumer Mapping

Complete mapping is recorded in FAEP-CAP-001 Section 5.

Key mapping findings:

| Pattern | Occurrence |
| --- | --- |
| Capabilities provided by single implementation | 24 of 35 (68%) |
| Capabilities provided by 2 implementations | 8 of 35 (23%) |
| Capabilities provided by 3 implementations | 3 of 35 (9%) |
| Capabilities consumed primarily within same platform | 18 of 35 (51%) |
| Capabilities consumed across platforms | 17 of 35 (49%) |

Most capabilities (68%) are provided by a single Reference Implementation, confirming the need for cross-program validation before any standardization.

---

## 8. Overlap Analysis Summary

| Overlap Type | Count | Key Examples |
| --- | --- | --- |
| Partial overlap | 10 pairs | Evidence management (knowledge domain vs. formula governance); Determinism vs. Execution Modes |
| Hierarchical | 5 pairs | Knowledge Layering vs. Canonical Storage; Cross-Reference vs. Navigation |
| Sequential (producer/consumer) | 3 pairs | DSL Compilation → Execution Plans; Evidence Registration → Evidence-Driven Publishing |
| Duplicate candidates | 2 | FAEP-CAND-003 (Determinism Modes) and FAEP-CAND-007 (Execution Mode) overlap |
| Competing governance models | 1 | Bundle Lifecycle vs. PLAN-based Execution |

Full details in FAEP-CAP-001 Section 6.

---

## 9. Discovery vs. Speculation Analysis

| Category | Count | Percentage |
| --- | --- | --- |
| Confirmed Discovery (Candidate) | 35 | 80% |
| Backlog (Speculative / Future) | 9 | 20% |
| **Total Identified** | **44** | **100%** |

The AI-Ready domain is entirely speculative (5 of 9 backlog items). The Knowledge, Publishing, Execution, and Governance domains are predominantly confirmed discoveries.

---

## 10. Deliverables

| Deliverable | Location | Description |
| --- | --- | --- |
| FAEP-CAP-000 | 00_Project_Management/Governance/FAEP-CAP-000_CAPABILITY_DISCOVERY_GUIDE.md | Capability Discovery Guide — defines the discovery process, classification criteria, and relationship to FAEP contract lifecycle |
| FAEP-CAP-001 | 00_Project_Management/Governance/FAEP-CAP-001_CANDIDATE_CAPABILITY_REGISTRY.md | Candidate Capability Registry — 35 Candidate Capabilities, 9 Backlog capabilities, provider/consumer mapping, overlap analysis, validation priorities, PLAN-021 recommendation |
| PLAN-020 | 00_Project_Management/Plans/03_history/PLAN-020_FAEP_CAPABILITY_DISCOVERY_USING_REFERENCE_IMPLEMENTATIONS.md | This plan document |
| PLAN_INDEX.md | Updated with PLAN-020 entry | |
| active.md | Updated with completed PLAN-020 | |
| CURRENT_WORK.md | Updated with PLAN-020 completion | |
| next-session.md | Updated with PLAN-020 handoff | |
| PROJECT_STATE.md | Updated with PLAN-020 verdict | |

---

## 11. Key Findings

1. **35 Candidate Capabilities discovered across 4 domains.** No capability was invented; all are extracted from actual implementations.

2. **Risk Platform contributes the most execution capabilities (14).** This confirms PLAN-016's finding that Risk Platform is significantly more mature than FAEP recognized.

3. **FRKP and FRKC remain the sole providers for knowledge and publishing capabilities.** Cross-program validation requires a non-FRKP publishing platform or non-FRKC knowledge platform.

4. **PLAN-based governance is the most cross-cutting capability.** Demonstrated in both FRKP and Risk Platform. Highest priority for standardization consideration.

5. **Evidence management appears in 3 implementations with different semantics.** FRKC (evidence lifecycle), FRKP (evidence-to-publication mapping), and Risk Platform (PromotionEvidence). Overlap analysis confirms these are distinct facets of a broader evidence capability.

6. **AI-Ready domain has zero Candidate capabilities.** Despite extensive specification in FRKP-005, the RAG corpus, semantic retrieval, context assembly, and citation model remain unimplemented.

7. **2 duplicate candidate patterns identified** (Determinism + Execution Mode). Already flagged in FAEP-CAND-003/FAEP-CAND-007 overlap.

8. **FAEP-CAP-001 and FAEP-CONTRACT-001 serve complementary but distinct purposes.** Capability Discovery identifies what implementations *can do*. Contract proposals define how implementations *shall interoperate*.

---

## 12. Recommended PLAN-021

### PLAN-021 — Cross-Program Candidate Validation

| Aspect | Description |
| --- | --- |
| **Title** | Cross-Program Candidate Validation |
| **Objective** | Validate P1-priority Candidate Capabilities against non-origin Reference Implementations. Specifically: (a) validate Risk Platform execution capabilities (CAP-EXE-001, CAP-EXE-002, CAP-EXE-004, CAP-EXE-005, CAP-EXE-007) against FRKP or IB Project context; (b) validate FRKP publishing capabilities (CAP-PUB-001, CAP-PUB-002) against Risk Platform workflow model; (c) validate cross-program capabilities (CAP-KNW-002, CAP-KNW-006, CAP-GOV-001) for consistency. |
| **Source** | FAEP-CAP-001 P1-priority capabilities; FAEP-CAND-001 through FAEP-CAND-010 |
| **Outputs** | Cross-program validation reports; updated FAEP-CAP-001 validation status; capability-based contract evolution recommendations; updated FAEP-CONTRACT-001 promotion recommendations |
| **Priority** | High |
| **Dependencies** | None — all inputs are documented in FAEP-CAP-001 |
| **Risk** | Low — no Foundation modifications; validation only |

### Future Plan Recommendations

| Plan | Focus | Trigger |
| --- | --- | --- |
| PLAN-022 | Capability Standard Pilot | After P1 capabilities validated by 2+ programs |
| PLAN-023 | IB Project Bootstrap (if not yet started) | After capability validation framework proven |

---

## 13. Preservation Statement

PLAN-020 did not modify:
- FAEP Foundation v1.0 frozen artifacts.
- FAEP Core Contracts (CC-*).
- FAEP Standards (FAEP-STD-000 through FAEP-STD-006).
- FAEP Specifications (FRKP-003, FRKP-004, FRKP-005).
- FAEP Governance documents (FAEP-000, FAEP-001, FAEP-002).
- FAEP ADR Registry (FAEP-ADR-000).
- FAEP Contract Governance (FAEP-CONTRACT-000, FAEP-CONTRACT-001).
- FAEP Validation Framework (FAEP-VALIDATION-000, FAEP-VALIDATION-001).
- FAEP Foundation Governance (FAEP-FOUNDATION-000, FAEP-FOUNDATION-001, FAEP-FOUNDATION-002).
- Bundle structure or repository layout.

PLAN-020 did not perform:
- Implementation.
- Code.
- Repository migration.
- Commits.
- Releases.

---

## 14. Verdict

**GO — Candidate Capabilities Discovered.**

35 Candidate Capabilities have been discovered across 4 domains from 3 Reference Implementations. No capabilities were invented. No Foundation artifacts were modified. The discovery process is governed by FAEP-CAP-000 (Capability Discovery Guide) and recorded in FAEP-CAP-001 (Candidate Capability Registry). Cross-program validation is recommended as PLAN-021.

---

## 15. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Capability Discovery Using Reference Implementations (PLAN-020) |
