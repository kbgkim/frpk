# KB-261 — Market Risk Standardized Approach

---

# Document Information

| Item          | Value                             |
| ------------- | --------------------------------- |
| Document ID   | KB-261                            |
| Document Name | Market Risk Standardized Approach |
| Version       | 1.0.0                             |
| Status        | Active                            |
| Category      | Knowledge Base                    |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                        |
| Domain        | Market Risk                       |
| Created       | 2026-06-27                        |
| Last Updated  | 2026-06-27                        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Knowledge Base](../README.md) > [KB-261 — Market Risk Standardized Approach](KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | [KB-262](KB-262_SENSITIVITY_BASED_METHOD.md) |

### Related Documents

- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-262](KB-262_SENSITIVITY_BASED_METHOD.md)
- [KB-263](KB-263_RISK_FACTOR_CATEGORIES.md)
- [AN-261](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)
- [MF-461](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB)의 **Market Risk Standardized Approach (SA)** 에 대한 핵심 개념과 구조를 설명한다.

Market Risk Standardized Approach는 Trading Book에서 발생하는 시장위험을 규제자본으로 산출하기 위한 표준 접근법이며, 민감도(Sensitivity) 기반 위험 측정 체계를 중심으로 설계되어 있다.

본 문서는 Bundle-006의 핵심 Knowledge Base 문서로서 이후 Analysis, Mathematical Foundation, Formula Catalog 및 Implementation Guide의 기반을 제공한다.

---

# 2. Background

기존 Basel 2.5 시장위험 규제는 주로 Value at Risk(VaR)를 기반으로 하였으나 다음과 같은 한계를 가지고 있었다.

* 극단적 시장상황(Tail Risk)을 충분히 반영하지 못함
* Trading Book과 Banking Book 간 규제 차이
* 위험 민감도 부족
* 실제 헤지 효과 반영 한계
* 금융기관 간 모델 비교 어려움

FRTB는 이러한 문제를 해결하기 위해 시장위험 규제를 전면 개편하였다.

---

# 3. Objectives

Market Risk Standardized Approach의 목적은 다음과 같다.

* Trading Book 시장위험의 일관된 측정
* 위험 민감도 기반 규제자본 산출
* 금융기관 간 비교 가능성 확보
* 내부모형 접근법(IMA)의 기준(Benchmark) 제공
* 시장충격에 대한 자본 적정성 확보

---

# 4. Core Concepts

Market Risk Standardized Approach는 다음 다섯 가지 핵심 개념으로 구성된다.

| Concept             | Description          |
| ------------------- | -------------------- |
| Trading Book        | 단기 매매 및 헤지 목적 자산     |
| Risk Factor         | 시장가격 변동 요인           |
| Sensitivity         | 위험요인 변화에 대한 가치 민감도   |
| Capital Requirement | 규제자본 요구량             |
| Aggregation         | 개별 위험을 종합하여 최종 자본 산출 |

---

# 5. Overall Framework

전체 구조는 다음과 같다.

```text
Trading Book
        │
        ▼
Risk Factors
        │
        ▼
Sensitivity Calculation
        │
        ├── Delta
        ├── Vega
        └── Curvature
        │
        ▼
Default Risk Charge
        │
        ▼
Residual Risk Add-on
        │
        ▼
Capital Aggregation
        │
        ▼
Market Risk Capital
```

---

# 6. Risk Classes

FRTB-SA는 위험요인에 따라 다음 다섯 개의 Risk Class를 정의한다.

| Risk Class                | Description |
| ------------------------- | ----------- |
| Interest Rate Risk (GIRR) | 일반 금리위험     |
| Credit Spread Risk (CSR)  | 신용스프레드 위험   |
| Equity Risk               | 주식 위험       |
| Foreign Exchange Risk     | 환율 위험       |
| Commodity Risk            | 상품가격 위험     |

각 Risk Class는 서로 다른 Risk Factor와 Risk Weight 체계를 가진다.

---

# 7. Sensitivity-Based Method

Market Risk Standardized Approach의 핵심은 Sensitivity-based Method(SBM)이다.

SBM은 시장요인의 변화에 대한 금융상품의 민감도를 계산하여 위험을 측정한다.

세 가지 민감도를 사용한다.

```text
Sensitivity

↓

Delta

↓

Vega

↓

Curvature
```

각 민감도는 별도의 Formula와 Risk Weight 체계를 가진다.

---

# 8. Capital Components

최종 Market Risk Capital은 다음 구성요소를 합산하여 계산한다.

```text
Sensitivity-based Method
        │
        ▼
Default Risk Charge
        │
        ▼
Residual Risk Add-on
        │
        ▼
Total Market Risk Capital
```

각 구성요소는 독립적으로 계산된 후 규제 기준에 따라 집계된다.

---

# 9. Comparison with Previous Framework

| Basel 2.5       | FRTB-SA        |
| --------------- | -------------- |
| VaR 중심          | Sensitivity 중심 |
| 위험 민감도 제한       | Risk Factor 기반 |
| Tail Risk 반영 부족 | 보다 높은 위험 민감도   |
| 내부모형 의존         | 표준화된 계산체계      |
| 비교 어려움          | 금융기관 간 비교 용이   |

---

# 10. Relationship with Other Bundles

```text
Bundle-001
Basel III
        │
        ▼
Bundle-002
FRTB
        │
        ▼
Bundle-006
Market Risk Standardized Approach
```

Bundle-006은 이후 ICAAP, Stress Testing 및 Model Risk Management와도 연계된다.

---

# 11. Relationship with FRKP

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

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)의 핵심 Knowledge Base 문서이다.

---

# 12. Related Knowledge

Bundle-006은 다음 세부 주제로 확장된다.

| Knowledge                | Document           |
| ------------------------ | ------------------ |
| Sensitivity-based Method | KB-262             |
| Risk Factor Categories   | KB-263             |
| Risk Weights             | KB-264 *(Planned)* |
| Correlation Structure    | KB-265 *(Planned)* |
| Bucket Framework         | KB-266 *(Planned)* |

---

# 13. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](KB-262_SENSITIVITY_BASED_METHOD.md) *(Planned)*       |
| Knowledge               | [KB-263_RISK_FACTOR_CATEGORIES](KB-263_RISK_FACTOR_CATEGORIES.md) *(Planned)*         |
| Analysis                | [AN-261_WHY_FRTB_REPLACED_VAR](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md) *(Planned)*          |
| Mathematical Foundation | [MF-461_COVARIANCE_MATRIX](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md) *(Planned)*              |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md) *(Planned)*          |
| Implementation          | [IMP-461_FRTB_SA_IMPLEMENTATION](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md) *(Planned)*        |
| Architecture            | [ARCH-761_MARKET_RISK_SA_ARCHITECTURE](../../07_Architecture/06_Market_Risk_Standardized_Approach/ARCH-761_MARKET_RISK_SA_ARCHITECTURE.md) *(Planned)*  |

---

# 14. Summary

Market Risk Standardized Approach는 Basel III FRTB에서 Trading Book의 시장위험을 측정하기 위한 표준 규제체계이다.

기존 VaR 중심 접근법과 달리, 위험요인에 대한 민감도(Delta, Vega, Curvature)를 기반으로 위험을 측정하며, Default Risk Charge 및 Residual Risk Add-on과 함께 최종 규제자본을 산출한다.

본 문서는 Bundle-006의 핵심 Knowledge Base로서 이후 Analysis, Mathematical Foundation, Formula Catalog 및 Implementation Guide의 공통 기반을 제공한다.

---

# 15. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
