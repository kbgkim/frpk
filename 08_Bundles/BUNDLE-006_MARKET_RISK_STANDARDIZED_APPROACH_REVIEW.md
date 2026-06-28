# BUNDLE-006 — Market Risk Standardized Approach Review

---

# Document Information

| Item          | Value                                    |
| ------------- | ---------------------------------------- |
| Document ID   | BUNDLE-006                               |
| Document Name | Market Risk Standardized Approach Review |
| Version       | 1.0.0                                    |
| Status        | Completed                                |
| Category      | Bundle Review                            |
| Parent Bundle | [Bundle-006](BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                               |
| Domain        | Market Risk                              |
| Created       | 2026-06-27                               |
| Last Updated  | 2026-06-27                               |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../README.md) > [Home](../README.md) > [Bundle-006](BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Bundle Review](README.md) > [BUNDLE-006 — Market Risk Standardized Approach Review](BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Bundle Review](README.md) |
| ➡ Next | None |

### Related Documents

- [RL-160](../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-261](../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)
- [KB-263](../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)
- [AN-261](../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Bundle-006 "Market Risk Standardized Approach"의 산출물을 종합적으로 검토하고, FRKP(Bundle Standard)에 정의된 구조와 품질 기준을 충족하는지 확인하기 위한 최종 Review 문서이다.

본 문서는 Bundle 종료(Closure) 문서이며, Bundle-006의 공식 완료 여부를 판단하는 기준으로 사용된다.

---

# 2. Bundle Objective

Bundle-006의 목표는 Basel III FRTB Standardized Approach의 시장위험(Standardized Approach)을 다음 계층으로 체계화하는 것이었다.

* Reference
* Knowledge
* Analysis
* Mathematical Foundation
* Formula
* Implementation
* Architecture

이를 통해 규제, 금융공학, 수학 및 시스템 구현을 하나의 일관된 지식 체계로 통합하였다.

---

# 3. Deliverables

## 3.1 Reference Library

| Document                                          |
| ------------------------------------------------- |
| RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW |

---

## 3.2 Knowledge Base

| Document                                 |
| ---------------------------------------- |
| KB-261_MARKET_RISK_STANDARDIZED_APPROACH |
| KB-262_SENSITIVITY_BASED_METHOD          |
| KB-263_RISK_FACTOR_CATEGORIES            |

---

## 3.3 Analysis

| Document                     |
| ---------------------------- |
| AN-261_WHY_FRTB_REPLACED_VAR |

---

## 3.4 Mathematical Foundation

| Document                            |
| ----------------------------------- |
| MF-461_COVARIANCE_MATRIX            |
| MF-462_PRINCIPAL_COMPONENT_ANALYSIS |
| MF-463_EIGENVALUE_AND_EIGENVECTOR   |

---

## 3.5 Formula Catalog

| Document                         |
| -------------------------------- |
| FC-461_DELTA_CAPITAL_FORMULA     |
| FC-462_VEGA_CAPITAL_FORMULA      |
| FC-463_CURVATURE_CAPITAL_FORMULA |
| FC-464_CAPITAL_AGGREGATION       |

---

## 3.6 Implementation Guide

| Document                       |
| ------------------------------ |
| IMP-461_FRTB_SA_IMPLEMENTATION |

---

## 3.7 Architecture Guide

| Document                             |
| ------------------------------------ |
| ARCH-761_MARKET_RISK_SA_ARCHITECTURE |

---

# 4. Knowledge Traceability

Bundle-006은 다음과 같은 계층적 추적성을 유지한다.

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
```

모든 하위 계층은 상위 계층의 내용을 구체화하며, 상위 계층으로 역추적이 가능하도록 구성되었다.

---

# 5. Coverage Assessment

| Area                     | Coverage |
| ------------------------ | :------: |
| Regulatory Background    |     ✔    |
| Business Concept         |     ✔    |
| Market Risk Framework    |     ✔    |
| Sensitivity-based Method |     ✔    |
| Mathematical Foundation  |     ✔    |
| Formula Definition       |     ✔    |
| Implementation Guide     |     ✔    |
| Architecture Guide       |     ✔    |

Bundle-006의 목표 범위는 모두 충족되었다.

---

# 6. Bundle Completeness

| Layer                   | Status |
| ----------------------- | :----: |
| Reference               |    ✔   |
| Knowledge               |    ✔   |
| Analysis                |    ✔   |
| Mathematical Foundation |    ✔   |
| Formula                 |    ✔   |
| Implementation          |    ✔   |
| Architecture            |    ✔   |

모든 필수 계층이 작성되었으며 누락된 계층은 없다.

---

# 7. FRKP Standard Compliance

Bundle-006은 다음 표준을 준수한다.

| Standard        | Status |
| --------------- | :----: |
| FRKP-DOC-001    |    ✔   |
| FRKP-BUNDLE-001 |    ✔   |
| FRKP-FORM-001   |    ✔   |
| FRKP-ID-001     |    ✔   |
| FRKP-TPL-001    |    ✔   |

문서 구조, 식별자, 계층 및 상호 참조는 FRKP Governance 표준을 따른다.

---

# 8. Architectural Assessment

본 Bundle는 다음 설계 원칙을 만족한다.

* Layer Separation
* Technology Neutrality
* Deterministic Calculation
* Formula Independence
* Traceability
* Reusability
* Extensibility

Implementation과 Architecture는 Formula Catalog에 의존하지만, Formula 자체는 구현 기술과 독립적으로 유지된다.

---

# 9. Knowledge Graph

```text
RL-160
   │
   ▼
KB-261
   │
   ├──────────────┐
   ▼              ▼
KB-262        KB-263
   │              │
   └──────┬───────┘
          ▼
AN-261
   │
   ▼
MF-461
   │
   ▼
MF-462
   │
   ▼
MF-463
   │
   ▼
FC-461
   │
   ▼
FC-462
   │
   ▼
FC-463
   │
   ▼
FC-464
   │
   ▼
IMP-461
   │
   ▼
ARCH-761
```

Knowledge Graph는 Bundle 내부의 개념적 의존성과 문서 간 관계를 나타낸다.

---

# 10. Quality Assessment

| Quality Attribute     | Result |
| --------------------- | :----: |
| Consistency           |    ✔   |
| Completeness          |    ✔   |
| Traceability          |    ✔   |
| Technology Neutrality |    ✔   |
| Regulatory Alignment  |    ✔   |
| Reusability           |    ✔   |
| Maintainability       |    ✔   |

Bundle-006은 FRKP Knowledge Production Strategy에서 정의한 품질 목표를 충족한다.

---

# 11. Future Extensions

향후 다음 영역으로 확장 가능하다.

* Internal Models Approach (IMA)
* Expected Shortfall (ES)
* Default Risk Charge (DRC)
* Residual Risk Add-On (RRAO)
* Liquidity Horizon
* Model Validation
* Stress Testing Integration

이러한 확장은 Bundle-006의 구조를 유지한 채 독립적으로 추가될 수 있다.

---

# 12. Lessons Learned

Bundle-006에서 확인된 주요 사항은 다음과 같다.

* Mathematical Foundation 계층은 Formula 이해도를 크게 향상시킨다.
* Formula와 Implementation을 명확히 분리하면 기술 독립성을 유지할 수 있다.
* 계층 간 Traceability는 문서 유지보수성과 재사용성을 높인다.
* FRTB와 같은 복잡한 규제는 Bundle 단위로 구성하는 것이 효과적이다.

---

# 13. Final Verdict

| Item                     | Result |
| ------------------------ | :----: |
| Bundle Structure         |  PASS  |
| Layer Completeness       |  PASS  |
| Traceability             |  PASS  |
| Formula Consistency      |  PASS  |
| Architecture Consistency |  PASS  |
| Governance Compliance    |  PASS  |

**Overall Result: PASS**

Bundle-006은 FRKP Bundle Standard를 충족하며, 공식적으로 완료(Completed) 상태로 승인한다.

---

# 14. Relationship with FRKP Roadmap

[Bundle-006](BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)은 FRKP Roadmap에서 다음 위치를 차지한다.

```text
Bundle-001
Basel III
        │
        ▼
Bundle-002
FRTB
        │
        ▼
Bundle-003
IFRS 9
        │
        ▼
Bundle-004
SA-CCR
        │
        ▼
Bundle-005
Credit Valuation Adjustment
        │
        ▼
Bundle-006
Market Risk Standardized Approach
        │
        ▼
Bundle-007
Operational Risk
```

[Bundle-006](BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)은 Bundle-007의 기반이 되는 시장위험 표준 접근법을 완성하였다.

---

# 15. Revision History

| Version | Date       | Description                       |
| ------- | ---------- | --------------------------------- |
| 1.0.0   | 2026-06-27 | Initial review and bundle closure |
