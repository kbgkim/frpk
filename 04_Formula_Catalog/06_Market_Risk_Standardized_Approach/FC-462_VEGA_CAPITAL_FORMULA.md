# FC-462 — Vega Capital Formula

---

# Document Information

| Item             | Value                |
| ---------------- | -------------------- |
| Document ID      | FC-462               |
| Document Name    | Vega Capital Formula |
| Version          | 1.0.0                |
| Status           | Active               |
| Category         | Formula Catalog      |
| Parent Bundle    | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)           |
| Domain           | Market Risk          |
| Created          | 2026-06-27           |
| Last Updated     | 2026-06-27           |
| Formula Standard | FRKP-FORM-001        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Formula Catalog](../README.md) > [FC-462 — Vega Capital Formula](FC-462_VEGA_CAPITAL_FORMULA.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-461](FC-461_DELTA_CAPITAL_FORMULA.md) |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-463](FC-463_CURVATURE_CAPITAL_FORMULA.md) |

### Related Documents

- [FC-461](FC-461_DELTA_CAPITAL_FORMULA.md)
- [FC-463](FC-463_CURVATURE_CAPITAL_FORMULA.md)
- [FC-464](FC-464_CAPITAL_AGGREGATION.md)
- [IMP-461](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md)
- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB) Standardized Approach(SA)의 **Vega Capital Formula**를 정의한다.

Vega Capital Formula는 금융상품의 **변동성(Volatility) 변화에 대한 민감도(Vega Sensitivity)** 를 기반으로 시장위험 규제자본을 계산하기 위한 공식이다.

본 문서는 구현 기술과 독립적인 Formula Catalog 문서이며, Risk Engine과 Formula Engine의 계산 계약(Calculation Contract)을 정의한다.

---

# 2. Business Purpose

Vega Risk는 시장가격 자체의 변화가 아니라 **시장 변동성(Implied Volatility)** 의 변화가 금융상품 가치에 미치는 영향을 측정한다.

특히 다음 상품군에서 중요하다.

* 옵션(Options)
* 옵션 내재 파생상품
* Structured Products
* Volatility Products

Vega Capital의 목적은 이러한 변동성 위험을 규제자본으로 반영하는 것이다.

---

# 3. Regulatory Perspective

FRTB Standardized Approach에서 Vega Risk는 Sensitivity-based Method(SBM)의 두 번째 핵심 구성요소이다.

계산 흐름은 다음과 같다.

```text
Risk Factor
        │
        ▼
Vega Sensitivity
        │
        ▼
Risk Weight
        │
        ▼
Weighted Vega
        │
        ▼
Bucket Aggregation
        │
        ▼
Capital Aggregation
```

---

# 4. Mathematical Definition

## Step 1. Vega Sensitivity

각 Risk Factor에 대한 Vega Sensitivity를 계산한다.

[
VS_i
====

\frac{\partial V}{\partial \sigma_i}
]

여기서

| Symbol     | Description          |
| ---------- | -------------------- |
| (V)        | 금융상품 가치              |
| (\sigma_i) | i번째 Risk Factor의 변동성 |
| (VS_i)     | Vega Sensitivity     |

---

## Step 2. Weighted Vega

규제 Risk Weight를 적용한다.

[
WVS_i
=====

RW_i
\times
VS_i
]

| Symbol  | Description               |
| ------- | ------------------------- |
| (RW_i)  | Regulatory Risk Weight    |
| (WVS_i) | Weighted Vega Sensitivity |

---

## Step 3. Bucket Aggregation

동일 Bucket 내 Weighted Vega를 상관관계를 고려하여 집계한다.

[
K_b
===

\sqrt{
\sum_i\sum_j
\rho_{ij}
WVS_i
WVS_j
}
]

| Symbol      | Description               |
| ----------- | ------------------------- |
| (K_b)       | Bucket Vega Capital       |
| (\rho_{ij}) | Within-Bucket Correlation |

---

## Step 4. Capital Aggregation

Bucket Capital을 전체 포트폴리오 수준으로 집계한다.

[
K
=

\sqrt{
\sum_b\sum_c
\gamma_{bc}
K_b
K_c
}
]

| Symbol        | Description              |
| ------------- | ------------------------ |
| (K)           | Total Vega Capital       |
| (\gamma_{bc}) | Cross-Bucket Correlation |

---

# 5. Formula Interpretation

Vega Capital Formula는 다음 네 단계의 논리적 계산으로 구성된다.

```text
Vega Sensitivity
        │
        ▼
Weighted Vega
        │
        ▼
Bucket Vega Capital
        │
        ▼
Total Vega Capital
```

가격 자체가 아니라 **변동성의 변화**를 규제자본으로 변환하는 과정이다.

---

# 6. Input Contract

| Input                     | Required | Description         |
| ------------------------- | :------: | ------------------- |
| Risk Factors              |     ✔    | 변동성 위험요인            |
| Vega Sensitivities        |     ✔    | Vega 민감도            |
| Regulatory Risk Weights   |     ✔    | 감독기관 지정 Risk Weight |
| Bucket Definition         |     ✔    | Bucket 분류           |
| Within-Bucket Correlation |     ✔    | Bucket 내부 상관관계      |
| Cross-Bucket Correlation  |     ✔    | Bucket 간 상관관계       |

---

# 7. Computation Contract

계산 절차는 다음 순서를 따른다.

```text
Collect Vega Sensitivities
        │
        ▼
Validate Inputs
        │
        ▼
Apply Risk Weights
        │
        ▼
Aggregate Within Bucket
        │
        ▼
Aggregate Across Buckets
        │
        ▼
Return Vega Capital
```

모든 계산은 결정론적이어야 하며 동일 입력에 대해 동일 결과를 반환해야 한다.

---

# 8. Output Contract

| Output              | Description           |
| ------------------- | --------------------- |
| Weighted Vega       | Risk Weight 적용 후 Vega |
| Bucket Vega Capital | Bucket 수준 Vega 자본     |
| Total Vega Capital  | 최종 Vega 규제자본          |

---

# 9. Formula Engine Model

```text
Vega Collector
        │
        ▼
Risk Weight Calculator
        │
        ▼
Bucket Aggregator
        │
        ▼
Cross-Bucket Aggregator
        │
        ▼
Capital Builder
```

Formula Engine은 구현 방식이 아니라 계산 책임의 논리적 분리를 나타낸다.

---

# 10. Relationship with Mathematical Foundation

```text
MF-461
Covariance Matrix
        │
        ▼
MF-462
Principal Component Analysis
        │
        ▼
MF-463
Eigenvalue & Eigenvector
        │
        ▼
FC-462
Vega Capital Formula
```

공분산 구조와 상관관계는 Vega Risk Aggregation의 수학적 기반을 제공한다.

---

# 11. Relationship with FRKP

```text
Reference
      │
      ▼
Knowledge
      │
      ▼
Analysis
      │
      ▼
Mathematical Foundation
      │
      ▼
Formula
      │
      ▼
Implementation
      │
      ▼
Architecture
```

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) Formula Catalog의 두 번째 핵심 Formula이다.

---

# 12. Non-functional Requirements

본 Formula는 다음 특성을 만족해야 한다.

* Deterministic
* Technology Neutral
* Traceable
* Testable
* Reproducible
* Immutable Definition
* Composable

---

# 13. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-261_MARKET_RISK_STANDARDIZED_APPROACH](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)          |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)                   |
| Knowledge               | [KB-263_RISK_FACTOR_CATEGORIES](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)                     |
| Analysis                | [AN-261_WHY_FRTB_REPLACED_VAR](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)                      |
| Mathematical Foundation | [MF-461_COVARIANCE_MATRIX](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md)                          |
| Mathematical Foundation | [MF-462_PRINCIPAL_COMPONENT_ANALYSIS](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md)               |
| Mathematical Foundation | [MF-463_EIGENVALUE_AND_EIGENVECTOR](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-463_EIGENVALUE_AND_EIGENVECTOR.md)                 |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](FC-461_DELTA_CAPITAL_FORMULA.md)                      |
| Formula                 | [FC-463_CURVATURE_CAPITAL_FORMULA](FC-463_CURVATURE_CAPITAL_FORMULA.md) *(Planned)*      |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |
| Implementation          | [IMP-461_FRTB_SA_IMPLEMENTATION](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md) *(Planned)*        |
| Architecture            | [ARCH-761_MARKET_RISK_SA_ARCHITECTURE](../../07_Architecture/06_Market_Risk_Standardized_Approach/ARCH-761_MARKET_RISK_SA_ARCHITECTURE.md) *(Planned)*  |

---

# 14. Summary

Vega Capital Formula는 FRTB Standardized Approach에서 금융상품의 변동성 민감도를 규제자본으로 변환하는 핵심 계산 계약이다.

계산은 Vega Sensitivity 산출, Risk Weight 적용, Bucket Aggregation 및 Cross-Bucket Aggregation의 네 단계로 구성된다.

본 Formula는 옵션 및 기타 비선형 금융상품의 변동성 위험을 일관된 방식으로 측정하기 위한 규제 표준이며, Curvature Capital Formula와 함께 비선형 위험 측정 체계를 완성한다.

---

# 15. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
