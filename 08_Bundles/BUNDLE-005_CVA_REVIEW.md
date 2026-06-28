# BUNDLE-005 — CVA Bundle Review

---

# Document Information

| Item          | Value                             |
| ------------- | --------------------------------- |
| Document ID   | BUNDLE-005                        |
| Document Name | CVA Bundle Review                 |
| Version       | 1.0.0                             |
| Status        | Frozen Candidate                  |
| Category      | Bundle Review                     |
| Bundle        | Bundle-005                        |
| Domain        | Credit Valuation Adjustment (CVA) |
| Created       | 2026-06-27                        |
| Last Updated  | 2026-06-27                        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../README.md) > [Home](../README.md) > [Bundle-005](BUNDLE-005_CVA_REVIEW.md) > [Bundle Review](README.md) > [BUNDLE-005 — CVA Bundle Review](BUNDLE-005_CVA_REVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Bundle Review](README.md) |
| ➡ Next | None |

### Related Documents

- [RL-150](../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
- [KB-252](../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)
- [AN-251](../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)
- [MF-451](../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Bundle-005(Credit Valuation Adjustment)의 전체 산출물을 검토하고, Bundle의 완성도, 일관성 및 추적성을 평가하기 위한 공식 Bundle Review 문서이다.

본 문서는 Bundle Freeze 여부를 판단하는 기준 문서이며, Bundle-006 이후 Bundle 개발의 참조 모델로 사용된다.

---

# 2. Bundle Scope

Bundle-005는 Basel III의 Credit Valuation Adjustment(CVA)를 하나의 End-to-End Knowledge Bundle로 구성한다.

포함 범위는 다음과 같다.

* CVA 개요
* CVA Framework
* 도입 배경
* Hazard Rate
* Survival Function
* Discount Factor
* Default Probability
* Expected Exposure
* Credit Valuation Adjustment
* CVA Capital Charge
* Implementation Guide
* Architecture Guide

---

# 3. Bundle Structure Review

```text
Reference Library
        │
        ▼
Knowledge Base
        │
        ▼
Analysis
        │
        ▼
Mathematical Foundation
        │
        ▼
Formula Catalog
        │
        ▼
Implementation Guide
        │
        ▼
Architecture Guide
        │
        ▼
Bundle Review
```

Bundle는 FRKP의 표준 Knowledge Lifecycle을 완전히 따른다.

---

# 4. Deliverable Review

## 4.1 Reference Library

| Document            | Status |
| ------------------- | :----: |
| RL-150_CVA_OVERVIEW |    ✔   |

---

## 4.2 Knowledge Base

| Document                           | Status |
| ---------------------------------- | :----: |
| KB-251_CREDIT_VALUATION_ADJUSTMENT |    ✔   |
| KB-252_CVA_FRAMEWORK               |    ✔   |

---

## 4.3 Analysis

| Document                      | Status |
| ----------------------------- | :----: |
| AN-251_WHY_CVA_WAS_INTRODUCED |    ✔   |

---

## 4.4 Mathematical Foundation

| Document                 | Status |
| ------------------------ | :----: |
| MF-451_HAZARD_RATE       |    ✔   |
| MF-452_SURVIVAL_FUNCTION |    ✔   |
| MF-453_DISCOUNT_FACTOR   |    ✔   |

---

## 4.5 Formula Catalog

| Document                                  | Status |
| ----------------------------------------- | :----: |
| FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE |    ✔   |
| FC-452_EXPECTED_EXPOSURE                  |    ✔   |
| FC-453_CREDIT_VALUATION_ADJUSTMENT        |    ✔   |
| FC-454_CVA_CAPITAL_CHARGE                 |    ✔   |

---

## 4.6 Implementation Guide

| Document                   | Status |
| -------------------------- | :----: |
| IMP-451_CVA_IMPLEMENTATION |    ✔   |

---

## 4.7 Architecture Guide

| Document                  | Status |
| ------------------------- | :----: |
| ARCH-751_CVA_ARCHITECTURE |    ✔   |

---

# 5. Traceability Review

각 계층은 상위 계층과 하위 계층으로 연결된다.

```text
RL-150
      │
      ▼
KB-251
KB-252
      │
      ▼
AN-251
      │
      ▼
MF-451
MF-452
MF-453
      │
      ▼
FC-451
FC-452
FC-453
FC-454
      │
      ▼
IMP-451
      │
      ▼
ARCH-751
```

Traceability는 단절 없이 유지된다.

---

# 6. Formula Coverage Review

Bundle에서 정의된 Formula는 다음을 모두 포함한다.

| Formula Area                | Status |
| --------------------------- | :----: |
| Default Probability         |    ✔   |
| Expected Exposure           |    ✔   |
| Credit Valuation Adjustment |    ✔   |
| Capital Charge              |    ✔   |

Coverage는 Bundle 목표를 충족한다.

---

# 7. Mathematical Consistency Review

수학적 기반은 다음 문서로 구성된다.

| Mathematical Foundation | Status |
| ----------------------- | :----: |
| Hazard Rate             |    ✔   |
| Survival Function       |    ✔   |
| Discount Factor         |    ✔   |

Formula Catalog는 Mathematical Foundation과 일관성을 유지한다.

---

# 8. Architecture Consistency Review

Architecture는 다음 원칙을 만족한다.

| Item                     | Result |
| ------------------------ | :----: |
| Layer Separation         |    ✔   |
| Formula Independence     |    ✔   |
| Technology Neutral       |    ✔   |
| Component Responsibility |    ✔   |
| Stateless Processing     |    ✔   |
| Scalability              |    ✔   |

---

# 9. Governance Compliance Review

Bundle는 FRKP Governance를 준수한다.

| Standard        | Result |
| --------------- | :----: |
| FRKP-DOC-001    |    ✔   |
| FRKP-FORM-001   |    ✔   |
| FRKP-IMP-001    |    ✔   |
| FRKP-ARCH-001   |    ✔   |
| FRKP-BUNDLE-001 |    ✔   |
| FRKP-ID-001     |    ✔   |

---

# 10. Quality Assessment

| Area            | Result |
| --------------- | :----: |
| Completeness    |    ✔   |
| Consistency     |    ✔   |
| Traceability    |    ✔   |
| Reusability     |    ✔   |
| Maintainability |    ✔   |
| Extensibility   |    ✔   |

---

# 11. Bundle Metrics

| Metric                            |  Value |
| --------------------------------- | -----: |
| Reference Documents               |      1 |
| Knowledge Documents               |      2 |
| Analysis Documents                |      1 |
| Mathematical Foundation Documents |      3 |
| Formula Documents                 |      4 |
| Implementation Documents          |      1 |
| Architecture Documents            |      1 |
| Review Documents                  |      1 |
| **Total Documents**               | **14** |

---

# 12. Lessons Learned

Bundle-005를 통해 다음 사항을 확인하였다.

* Bundle 중심 개발 방식은 지식의 추적성과 일관성을 높인다.
* Mathematical Foundation 계층은 Formula의 이해와 재사용성을 향상시킨다.
* Formula Catalog와 Implementation Guide를 분리함으로써 기술 독립성을 확보할 수 있다.
* Architecture Guide는 Formula와 구현의 연결 관계를 명확히 표현한다.

---

# 13. Recommendations

다음 Bundle에서는 다음 사항을 유지한다.

* 동일한 Bundle Lifecycle 적용
* Mathematical Foundation 우선 정의
* Formula Asset 표준 준수
* Traceability 유지
* Governance 문서 지속 적용

Bundle-006(FRTB)에서는 Formula Dependency Graph와 Formula Classification을 보다 적극적으로 활용한다.

---

# 14. Final Assessment

| Evaluation Item          | Result |
| ------------------------ | :----: |
| Bundle Structure         |  PASS  |
| Knowledge Completeness   |  PASS  |
| Mathematical Consistency |  PASS  |
| Formula Consistency      |  PASS  |
| Implementation Readiness |  PASS  |
| Architecture Readiness   |  PASS  |
| Governance Compliance    |  PASS  |

---

# 15. Final Verdict

**Verdict: GO (Frozen Candidate)**

Bundle-005는 FRKP의 표준 Bundle 구조(RL → KB → AN → MF → FC → IMP → ARCH → REVIEW)를 모두 충족하였다.

모든 산출물은 상호 추적 가능하며, Formula와 Implementation, Architecture 간의 일관성이 확보되었다.

본 Bundle은 Bundle-006 이후 모든 Domain Bundle의 기준 모델(Reference Bundle)로 사용할 수 있다.

---

# 16. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Reference               | [RL-150_CVA_OVERVIEW](../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)                       |
| Knowledge               | [KB-251_CREDIT_VALUATION_ADJUSTMENT](../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Knowledge               | [KB-252_CVA_FRAMEWORK](../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Analysis                | [AN-251_WHY_CVA_WAS_INTRODUCED](../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)             |
| Mathematical Foundation | [MF-451_HAZARD_RATE](../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)                        |
| Mathematical Foundation | [MF-452_SURVIVAL_FUNCTION](../05_Mathematical_Foundation/05_CVA/MF-452_SURVIVAL_FUNCTION.md)                  |
| Mathematical Foundation | [MF-453_DISCOUNT_FACTOR](../05_Mathematical_Foundation/05_CVA/MF-453_DISCOUNT_FACTOR.md)                    |
| Formula                 | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula                 | [FC-452_EXPECTED_EXPOSURE](../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)                  |
| Formula                 | [FC-453_CREDIT_VALUATION_ADJUSTMENT](../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Formula                 | [FC-454_CVA_CAPITAL_CHARGE](../04_Formula_Catalog/05_CVA/FC-454_CVA_CAPITAL_CHARGE.md)                 |
| Implementation          | [IMP-451_CVA_IMPLEMENTATION](../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)                |
| Architecture            | [ARCH-751_CVA_ARCHITECTURE](../07_Architecture/05_CVA/ARCH-751_CVA_ARCHITECTURE.md)                 |

---

# 17. Revision History

| Version | Date       | Description                                           |
| ------- | ---------- | ----------------------------------------------------- |
| 1.0.0   | 2026-06-27 | Initial Bundle Review and Frozen Candidate Assessment |
