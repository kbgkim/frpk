# FRKP-PROGRAM-003 — Publication Backlog

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PROGRAM-003 |
| Document Name | Financial Platform Publication Backlog |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance |
| Owner | FRKP Publishing Office |
| Plan | PLAN-022 |
| Related Documents | FRKP-PROGRAM-000; FRKP-PROGRAM-001; FRKP-PROGRAM-002; FRKP-PROGRAM-004; FRKP-PUB-000; FRKP-PUB-001; FRKP-PUB-002; FAEP-CAP-001; FRKP-DOC-100 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# 1. Purpose

This document registers all planned publications for the Financial Platform Handbook. It tracks the status, ownership, priority, dependencies, readiness estimation, and publication milestones for every volume.

The backlog is managed by the FRKP Publishing Office. Changes to the backlog require approval per FRKP-PROGRAM-000 decision authority rules.

---

# 2. Volume Summary

| Priority | Volume ID | Volume Name | Status | Owner | Chapters | Sections | Capabilities | Estimated Readiness |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | FP-VOL-005 | Knowledge Platform | Planned | TBD | 6 | 18+ | CAP-KNW-001 through CAP-KNW-008 | Ready — all inputs available |
| 2 | FP-VOL-001 | Platform Architecture | Planned | TBD | 6 | 18+ | CAP-EXE-008, CAP-GOV-002/003/004 | Ready — all inputs available |
| 3 | FP-VOL-002 | Formula Engine | Planned | TBD | 6 | 18+ | CAP-EXE-001/003/010/011 | Inputs available; IB dependency high |
| 4 | FP-VOL-003 | Risk Engine | Planned | TBD | 6 | 18+ | CAP-EXE-002/004/005/006/012/013/014 | Inputs available; depends on VOL-002 |
| 5 | FP-VOL-004 | Risk Solution | Planned | TBD | 6 | 18+ | (domain-specific) | Inputs available; depends on VOL-003 |
| 6 | FP-VOL-006 | Implementation Guide | Planned | TBD | 6 | 18+ | CAP-PUB-001/002/003/004, CAP-GOV-005 | Inputs available |
| 7 | FP-VOL-007 | Operations Guide | Planned | TBD | 6 | 18+ | CAP-PUB-005/006/007/008, CAP-EXE-007/009/015, CAP-GOV-001 | Inputs available |
| 8 | FP-VOL-008 | IB Integration Guide | Planned | TBD | 6 | 18+ | (cross-references all) | Depends on all prior volumes; IB Project bootstrap |

---

# 3. Individual Volume Records

## 3.1 FP-VOL-005 — Knowledge Platform

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-005 |
| Volume Name | Knowledge Platform |
| Status | Planned |
| Owner | TBD |
| Priority | 1 (Highest) |
| Dependencies | None |
| Chapters | CH-01: Knowledge OS Architecture; CH-02: Knowledge Architecture; CH-03: Knowledge Objects; CH-04: Ontology and Knowledge Graph; CH-05: Evidence Management; CH-06: Semantic Retrieval and AI |
| Capabilities | CAP-KNW-001 (Canonical Knowledge Model), CAP-KNW-002 (Evidence Lifecycle), CAP-KNW-003 (Terminology Management), CAP-KNW-004 (Domain Scoping), CAP-KNW-005 (Layer Architecture), CAP-KNW-006 (Cross-Reference Model), CAP-KNW-007 (Metadata Schema), CAP-KNW-008 (Version Strategy) |
| Key Source Documents | FRKP-005 (FRKC Knowledge OS); FAEP-CAP-001 (Knowledge Domain); FRKC repository |
| Estimated Duration | 4 weeks |
| Publication Milestone | Target: v1.0.0 — Q3 2026 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | GREEN | All 8 Knowledge Domain capabilities documented |
| Source evidence available | GREEN | FRKP-005 complete; FRKC repository active |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.5 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | GREEN | None |

---

## 3.2 FP-VOL-001 — Platform Architecture

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-001 |
| Volume Name | Platform Architecture |
| Status | Planned |
| Owner | TBD |
| Priority | 2 |
| Dependencies | FP-VOL-005 (Knowledge Platform) — provides knowledge model context |
| Chapters | CH-01: FAEP Master Architecture; CH-02: Platform Engine Model; CH-03: Core Platform Specification; CH-04: Integration Architecture; CH-05: Governance Integration; CH-06: Platform Evolution |
| Capabilities | CAP-EXE-008 (Architecture Enforcement), CAP-GOV-002 (ADR Framework), CAP-GOV-003 (Contract Lifecycle), CAP-GOV-004 (Foundation Governance) |
| Key Source Documents | FRKP-003 (FAEP Master Architecture); FRKP-004 (FAEP Core Platform Specification); FAEP-000/001/002 |
| Estimated Duration | 4 weeks |
| Publication Milestone | Target: v1.0.0 — Q3 2026 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | GREEN | Governance and Execution capabilities documented |
| Source evidence available | GREEN | FRKP-003, FRKP-004, FAEP-000/001/002 complete |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.1 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | GREEN | VOL-005 dependency is informational; no blocking dependency |

---

## 3.3 FP-VOL-002 — Formula Engine

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-002 |
| Volume Name | Formula Engine |
| Status | Planned |
| Owner | TBD |
| Priority | 3 |
| Dependencies | FP-VOL-001 (Platform Architecture) — provides architectural context |
| Chapters | CH-01: Formula Language; CH-02: Lexical and Syntactic Analysis; CH-03: Compiler Pipeline; CH-04: Compiler Optimization; CH-05: Canonical Plan Generation; CH-06: Formula Governance |
| Capabilities | CAP-EXE-001 (DSL Compilation Pipeline), CAP-EXE-003 (Formula Lifecycle), CAP-EXE-010 (Promotion Workflow), CAP-EXE-011 (Dependency Analysis) |
| Key Source Documents | Risk Platform compiler (Lexer, Parser, AST, Optimizer, Canonical Plan); FAEP-CAND-001 (Compiler Pipeline Contract); FAEP-CAND-002 (Execution Plan Contract) |
| Estimated Duration | 6 weeks |
| Publication Milestone | Target: v1.0.0 — Q4 2026 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | AMBER | Compiler capabilities available; detailed formula semantics require extraction |
| Source evidence available | GREEN | Risk Platform compiler source accessible |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.2 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | AMBER | VOL-001 must be published first |

---

## 3.4 FP-VOL-003 — Risk Engine

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-003 |
| Volume Name | Risk Engine |
| Status | Planned |
| Owner | TBD |
| Priority | 4 |
| Dependencies | FP-VOL-001 (Platform Architecture); FP-VOL-002 (Formula Engine) — provides formula and compilation context |
| Chapters | CH-01: Runtime Architecture; CH-02: Deterministic Execution; CH-03: Execution Plans; CH-04: Execution Modes; CH-05: Numeric Precision; CH-06: Variable System |
| Capabilities | CAP-EXE-002 (Determinism Model), CAP-EXE-004 (Execution Plans), CAP-EXE-005 (Execution Mode Taxonomy), CAP-EXE-006 (Governance Guards), CAP-EXE-012 (Variable Resolution), CAP-EXE-013 (Variable Codec), CAP-EXE-014 (Numeric Precision) |
| Key Source Documents | Risk Platform runtime (RuntimeCompiledPlan, CalculationContext, VariableResolver); FAEP-CAND-003 (Determinism Modes); FAEP-CAND-007 (Execution Mode) |
| Estimated Duration | 6 weeks |
| Publication Milestone | Target: v1.0.0 — Q4 2026 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | AMBER | Runtime capabilities available; execution details require extraction |
| Source evidence available | GREEN | Risk Platform runtime source accessible |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.3 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | AMBER | VOL-001 and VOL-002 must be published first |

---

## 3.5 FP-VOL-004 — Risk Solution

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-004 |
| Volume Name | Risk Solution |
| Status | Planned |
| Owner | TBD |
| Priority | 5 |
| Dependencies | FP-VOL-003 (Risk Engine) — provides runtime execution context |
| Chapters | CH-01: Market Risk; CH-02: Credit Risk; CH-03: Operational Risk; CH-04: Liquidity Risk; CH-05: ICAAP; CH-06: Stress Testing |
| Capabilities | (domain-specific; cross-refers to execution capabilities) |
| Key Source Documents | FRKP Bundles 1-7; Risk Platform calculator implementations; Regulatory texts (Basel III, IFRS 9, etc.) |
| Estimated Duration | 8 weeks |
| Publication Milestone | Target: v1.0.0 — Q1 2027 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | AMBER | Domain knowledge available in FRKP bundles; requires synthesis |
| Source evidence available | GREEN | FRKP bundles 1-7 available; Risk Platform calculators accessible |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.4 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | RED | Depends on VOL-003 which depends on VOL-002 which depends on VOL-001 |

---

## 3.6 FP-VOL-006 — Implementation Guide

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-006 |
| Volume Name | Implementation Guide |
| Status | Planned |
| Owner | TBD |
| Priority | 6 |
| Dependencies | FP-VOL-001 (Platform Architecture) — provides methodology context |
| Chapters | CH-01: Platform Bootstrap; CH-02: Reference Implementation; CH-03: Bundle Lifecycle; CH-04: Document Authoring; CH-05: Evidence-Driven Publishing; CH-06: Quality Assurance |
| Capabilities | CAP-PUB-001 (Evidence-Driven Publishing), CAP-PUB-002 (Bundle Lifecycle), CAP-PUB-003 (Authoring Process), CAP-PUB-004 (Navigation Structure), CAP-GOV-005 (Validation Framework) |
| Key Source Documents | FRKP-FRKC-001 (Evidence-Driven Publishing Workflow); FAEP-VALIDATION-000/001; Bundle-007 lifecycle; FRKP bundle execution records |
| Estimated Duration | 4 weeks |
| Publication Milestone | Target: v1.0.0 — Q1 2027 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | GREEN | Publishing and Governance capabilities well documented |
| Source evidence available | GREEN | FRKP execution patterns available; Bundle-007 records accessible |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.6 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | GREEN | Informational dependency on VOL-001 |

---

## 3.7 FP-VOL-007 — Operations Guide

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-007 |
| Volume Name | Operations Guide |
| Status | Planned |
| Owner | TBD |
| Priority | 7 |
| Dependencies | FP-VOL-001 (Platform Architecture) — provides operational context |
| Chapters | CH-01: Platform Governance; CH-02: Release Management; CH-03: Freeze Certification; CH-04: AI Agent Operations; CH-05: Session Management; CH-06: Continuous Improvement |
| Capabilities | CAP-PUB-005 (AI Agent Framework), CAP-PUB-006 (Session Lifecycle), CAP-PUB-007 (Freeze Certification), CAP-PUB-008 (Archive Strategy), CAP-EXE-007 (PLAN Execution), CAP-EXE-009 (Snapshot Strategy), CAP-EXE-015 (Governance Metrics), CAP-GOV-001 (PLAN Governance) |
| Key Source Documents | FRKP-002 (AI Operating Model); FAEP-STD-006 (Release and Freeze); PLAN lifecycle records; FRKP-FREEZE-001 |
| Estimated Duration | 4 weeks |
| Publication Milestone | Target: v1.0.0 — Q1 2027 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | GREEN | Publishing and Execution capabilities documented |
| Source evidence available | GREEN | FRKP governance records available; freeze certificates accessible |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.7 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | GREEN | Informational dependency on VOL-001 |

---

## 3.8 FP-VOL-008 — IB Integration Guide

| Field | Value |
| --- | --- |
| Volume ID | FP-VOL-008 |
| Volume Name | IB Integration Guide |
| Status | Planned |
| Owner | TBD |
| Priority | 8 |
| Dependencies | All prior volumes (FP-VOL-001 through FP-VOL-007) |
| Chapters | CH-01: IB Project Overview; CH-02: Knowledge Integration; CH-03: Formula and Engine Integration; CH-04: Risk Analytics Integration; CH-05: Governance Integration; CH-06: IB Reference Materials |
| Capabilities | (cross-references all capabilities; IB-specific mappings to be defined) |
| Key Source Documents | IB Project requirements (anticipated); FAEP-000/001; PLAN-016 validation findings |
| Estimated Duration | 4 weeks |
| Publication Milestone | Target: v1.0.0 — Q2 2027 |

### Readiness Assessment

| Criteria | Status | Notes |
| --- | --- | --- |
| Knowledge Objects available | RED | Requires IB Project bootstrap to define IB-specific knowledge |
| Source evidence available | RED | IB Project requirements not yet available |
| Volume structure defined | GREEN | FRKP-PUB-002 Section 3.8 complete |
| Owner assigned | RED | Volume Owner TBD |
| Dependencies | RED | Depends on all 7 prior volumes and IB Project bootstrap |

---

# 4. Backlog Status Summary

## 4.1 Status Distribution

| Status | Count | Volumes |
| --- | --- | --- |
| Planned | 8 | All volumes |
| Extraction | 0 | — |
| Drafting | 0 | — |
| Review | 0 | — |
| Freezing | 0 | — |
| Published | 0 | — |
| Deprecated | 0 | — |

## 4.2 Priority Distribution

| Priority | Count | Volumes |
| --- | --- | --- |
| 1 (Highest) | 1 | FP-VOL-005 |
| 2 | 1 | FP-VOL-001 |
| 3 | 1 | FP-VOL-002 |
| 4 | 1 | FP-VOL-003 |
| 5 | 1 | FP-VOL-004 |
| 6 | 1 | FP-VOL-006 |
| 7 | 1 | FP-VOL-007 |
| 8 | 1 | FP-VOL-008 |

## 4.3 Dependency Chain

```
FP-VOL-005 (no dependencies)
     |
     v
FP-VOL-001 (informational: VOL-005)
     |
     +---> FP-VOL-006 (informational: VOL-001)
     |
     +---> FP-VOL-007 (informational: VOL-001)
     |
     v
FP-VOL-002 (architectural: VOL-001)
     |
     v
FP-VOL-003 (architectural: VOL-001, VOL-002)
     |
     v
FP-VOL-004 (architectural: VOL-003)
     |
     v
FP-VOL-008 (architectural: all prior volumes)
```

---

# 5. Backlog Management

## 5.1 Adding Volumes

New volumes may be added to the backlog by the FRKP Publishing Office with approval from the FAEP Program Board. Each new volume must include:

- Volume ID and Name
- Justification
- Structure (chapters and sections)
- Capability mappings
- Dependency assessment
- Estimated duration

## 5.2 Priority Changes

Priority may be changed by the FRKP Publishing Office based on IB Project readiness, source availability, or program priorities.

## 5.3 Status Transitions

Volume status follows the workflow states defined in FRKP-PROGRAM-001 Section 5.

## 5.4 Backlog Review Cadence

The backlog shall be reviewed at least quarterly by the FRKP Publishing Office.

---

# 6. Preservation Commitment

This document does not modify any FAEP Foundation, Core Contract, Standard, Specification, Governance, frozen bundle, or Version 1.0.0 artifact.

---

# 7. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Publication Backlog (PLAN-022) |
