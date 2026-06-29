# BUNDLE-007 - Operational Risk Review

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | BUNDLE-007                      |
| Document Name | Operational Risk Review         |
| Version       | 1.0.0                           |
| Status        | Completed                       |
| Category      | Bundle Review                   |
| Parent Bundle | [Bundle-007](BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../README.md) > [Home](../README.md) > [Bundle-007](BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Bundle Review](README.md) > [BUNDLE-007 - Operational Risk Review](BUNDLE-007_OPERATIONAL_RISK_REVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [BUNDLE-006](BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Bundle | [BUNDLE-007](BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Bundle Review](README.md) |
| ➡ Next | None |

### Related Documents

- [RL-170](../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-271](../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [KB-272](../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [AN-271](../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [MF-471](../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [FC-471](../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [IMP-471](../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
- [ARCH-771](../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Bundle-007 "Operational Risk"의 산출물을 종합 검토하고, FRKP Bundle Standard를 충족하는지 확인하기 위한 Review 문서이다.

본 문서는 Bundle-007의 공식 완료 기준을 제공하며, 이후 유지보수 및 확장 시 기준점으로 사용된다.

---

# 2. Bundle Objective

Bundle-007의 목표는 운영리스크를 다음 계층으로 체계화하는 것이다.

* Reference
* Knowledge
* Analysis
* Mathematical Foundation
* Formula
* Implementation
* Architecture

---

# 3. Deliverables

## 3.1 Reference Library

| Document |
| -------- |
| RL-170_OPERATIONAL_RISK_OVERVIEW |

## 3.2 Knowledge Base

| Document |
| -------- |
| KB-271_OPERATIONAL_RISK_FRAMEWORK |
| KB-272_STANDARDIZED_MEASUREMENT_APPROACH |

## 3.3 Analysis

| Document |
| -------- |
| AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED |

## 3.4 Mathematical Foundation

| Document |
| -------- |
| MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION |

## 3.5 Formula Catalog

| Document |
| -------- |
| FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA |

## 3.6 Implementation Guide

| Document |
| -------- |
| IMP-471_OPERATIONAL_RISK_IMPLEMENTATION |

## 3.7 Architecture Guide

| Document |
| -------- |
| ARCH-771_OPERATIONAL_RISK_ARCHITECTURE |

---

# 4. Knowledge Traceability

```text
RL-170
   |
   v
KB-271
   |
   v
KB-272
   |
   v
AN-271
   |
   v
MF-471
   |
   v
FC-471
   |
   v
IMP-471
   |
   v
ARCH-771
```

Bundle-007 preserves the layer order and traceability expected by FRKP.

Candidate traceability references are recorded in the source documents as remediation metadata. These references are candidate mappings only and do not promote any KO, CAP, or EVD item to governed status.

---

# 5. Coverage Assessment

| Area | Coverage |
| ---- | :------: |
| Operational Risk Definition | ✔ |
| Standardized Measurement Approach | ✔ |
| Capital Change Rationale | ✔ |
| Loss Distribution Foundation | ✔ |
| Capital Formula | ✔ |
| Implementation Guide | ✔ |
| Architecture Guide | ✔ |

---

# 6. Bundle Completeness

| Layer | Status |
| ----- | :----: |
| Reference | ✔ |
| Knowledge | ✔ |
| Analysis | ✔ |
| Mathematical Foundation | ✔ |
| Formula | ✔ |
| Implementation | ✔ |
| Architecture | ✔ |

---

# 7. FRKP Standard Compliance

Bundle-007 is aligned with the following standards.

| Standard | Status |
| -------- | :----: |
| FRKP-DOC-001 | ✔ |
| FRKP-BUNDLE-001 | ✔ |
| FRKP-FORM-001 | ✔ |
| FRKP-ID-001 | ✔ |

---

# 8. Architectural Assessment

Bundle-007 satisfies the following design principles.

* Layer separation
* Technology neutrality
* Deterministic calculation
* Traceability
* Reusability
* Governance alignment

---

# 9. Candidate Traceability Summary

| Document | Candidate KO | Candidate Evidence |
| -------- | ------------ | ------------------ |
| RL-170 | KO-OPR-170 | EVD-000340; EVD-000341; EVD-000342 |
| KB-271 | KO-OPR-271 | EVD-000340; EVD-000341; EVD-000347 |
| KB-272 | KO-OPR-272 | EVD-000342; EVD-000343; EVD-000344; EVD-000345; EVD-000346 |
| AN-271 | KO-OPR-271A | EVD-000341; EVD-000342; EVD-000347 |
| MF-471 | KO-OPR-471M | EVD-000345; EVD-000347 |
| FC-471 | KO-OPR-471F | EVD-000342; EVD-000343; EVD-000344; EVD-000345; EVD-000346 |
| IMP-471 | KO-OPR-471I | EVD-000343; EVD-000347; EVD-000348 |
| ARCH-771 | KO-OPR-771 | EVD-000348; EVD-000349 |

---

# 10. Final Verdict

| Item | Result |
| ---- | :----: |
| Bundle Structure | PASS |
| Layer Completeness | PASS |
| Traceability | PASS |
| Formula Consistency | PASS |
| Architecture Consistency | PASS |
| Governance Compliance | PASS |

**Overall Result: PASS**

Bundle-007 satisfies the FRKP Bundle Standard and is approved as a completed bundle.

---

# 11. Relationship with FRKP Roadmap

```text
Bundle-006
Market Risk Standardized Approach
        |
        v
Bundle-007
Operational Risk
```

Bundle-007 continues Version 1.1 knowledge expansion.

---

# 12. Revision History

| Version | Date       | Description |
| ------- | ---------- | ----------- |
| 1.0.0   | 2026-06-28 | Initial review and bundle closure |
| 1.0.1   | 2026-06-29 | Added candidate traceability summary and remediation metadata |
