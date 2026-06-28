# FC-461 — Delta Capital Formula

---

# Document Information

| Item             | Value                 |
| ---------------- | --------------------- |
| Document ID      | FC-461                |
| Document Name    | Delta Capital Formula |
| Version          | 1.0.0                 |
| Status           | Active                |
| Category         | Formula Catalog       |
| Parent Bundle    | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)            |
| Domain           | Market Risk           |
| Created          | 2026-06-27            |
| Last Updated     | 2026-06-27            |
| Formula Standard | FRKP-FORM-001         |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Formula Catalog](../README.md) > [FC-461 — Delta Capital Formula](FC-461_DELTA_CAPITAL_FORMULA.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-462](FC-462_VEGA_CAPITAL_FORMULA.md) |

### Related Documents

- [FC-462](FC-462_VEGA_CAPITAL_FORMULA.md)
- [FC-463](FC-463_CURVATURE_CAPITAL_FORMULA.md)
- [FC-464](FC-464_CAPITAL_AGGREGATION.md)
- [IMP-461](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md)
- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB) Standardized Approach(SA)에서 사용하는 **Delta Capital Formula**를 정의한다.

Delta Capital Formula는 Risk Factor의 **1차 가격 민감도(First-order Sensitivity)** 를 기반으로 시장위험 규제자본을 계산하기 위한 공식이며, FRTB Standardized Approach의 핵심 계산 계약(Calculation Contract)을 제공한다.

본 문서는 구현 기술과 무관한 Formula 정의 문서이며, Formula Engine, Risk Engine 및 Implementation Guide의 입력 계약 역할을 수행한다.

---

# 2. Business Purpose

Delta Risk는 시장가격이 작은 폭으로 변할 때 금융상품 가치가 얼마나 변하는지를 측정한다.

규제 목적은 다음과 같다.

* 시장위험의 선형 민감도 측정
* 위험요인별 자본 요구량 산정
* 포트폴리오 위험의 표준화된 계산
* 금융기관 간 자본 비교 가능성 확보

---

# 3. Regulatory Perspective

Basel III FRTB는 Delta Risk를 Sensitivity-based Method(SBM)의 첫 번째 구성요소로 정의한다.

Delta Capital은 다음 절차에 따라 계산된다.

```text
Risk Factor
        │
        ▼
Delta Sensitivity
        │
        ▼
Risk Weight
        │
        ▼
Weighted Sensitivity
        │
        ▼
Bucket Aggregation
        │
        ▼
Capital Aggregation
```

---

# 4. Mathematical Definition

Delta Capital 계산은 다음 논리적 단계로 구성된다.

## Step 1. Delta Sensitivity

각 Risk Factor에 대한 Delta Sensitivity를 계산한다.

[
S_i
===

\frac{\partial V}{\partial RF_i}
]

여기서

| Symbol | Description       |
| ------ | ----------------- |
| (V)    | 금융상품 가치           |
| (RF_i) | i번째 Risk Factor   |
| (S_i)  | Delta Sensitivity |

---

## Step 2. Weighted Sensitivity

Risk Weight를 적용한다.

[
WS_i
====

RW_i
\times
S_i
]

| Symbol | Description            |
| ------ | ---------------------- |
| (RW_i) | Regulatory Risk Weight |
| (WS_i) | Weighted Sensitivity   |

---

## Step 3. Bucket Aggregation

동일 Bucket 내 Weighted Sensitivity를 상관관계를 반영하여 집계한다.

[
K_b
===

\sqrt{
\sum_i\sum_j
\rho_{ij}
WS_i
WS_j
}
]

여기서

| Symbol      | Description        |
| ----------- | ------------------ |
| (K_b)       | Bucket Capital     |
| (\rho_{ij}) | Bucket Correlation |

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
| (K)           | Total Delta Capital      |
| (\gamma_{bc}) | Cross-Bucket Correlation |

---

# 5. Formula Interpretation

Delta Capital Formula는 다음 네 단계의 논리적 계산으로 구성된다.

```text
Delta Sensitivity
        │
        ▼
Weighted Sensitivity
        │
        ▼
Bucket Capital
        │
        ▼
Total Delta Capital
```

이는 개별 Risk Factor를 포트폴리오 수준의 규제자본으로 변환하는 과정이다.

---

# 6. Input Contract

| Input                     | Required | Description         |
| ------------------------- | :------: | ------------------- |
| Risk Factors              |     ✔    | 대상 위험요인             |
| Delta Sensitivities       |     ✔    | 위험요인별 Delta         |
| Risk Weights              |     ✔    | 감독기관 지정 Risk Weight |
| Bucket Definition         |     ✔    | Bucket 분류           |
| Within-Bucket Correlation |     ✔    | Bucket 내부 상관관계      |
| Cross-Bucket Correlation  |     ✔    | Bucket 간 상관관계       |

---

# 7. Computation Contract

계산 절차는 다음 순서를 따른다.

```text
Collect Sensitivities
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
Return Delta Capital
```

모든 계산은 결정론적(Deterministic)이어야 하며 동일 입력에 대해 동일 결과를 반환해야 한다.

---

# 8. Output Contract

| Output               | Description          |
| -------------------- | -------------------- |
| Weighted Sensitivity | Risk Weight가 적용된 민감도 |
| Bucket Capital       | Bucket 수준 자본         |
| Total Delta Capital  | 최종 Delta 규제자본        |

---

# 9. Formula Engine Model

Formula Engine의 논리적 모델은 다음과 같다.

```text
Sensitivity Collector
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

이 모델은 구현 구조가 아니라 계산 책임의 논리적 분리를 의미한다.

---

# 10. Relationship with Mathematical Foundation

Delta Capital Formula는 다음 Mathematical Foundation을 기반으로 한다.

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
FC-461
Delta Capital Formula
```

공분산과 상관관계는 Bucket Aggregation의 수학적 기반을 제공한다.

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

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) Formula Catalog의 첫 번째 계산 계약이다.

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
| Formula                 | [FC-462_VEGA_CAPITAL_FORMULA](FC-462_VEGA_CAPITAL_FORMULA.md) *(Planned)*           |
| Formula                 | [FC-463_CURVATURE_CAPITAL_FORMULA](FC-463_CURVATURE_CAPITAL_FORMULA.md) *(Planned)*      |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |
| Implementation          | [IMP-461_FRTB_SA_IMPLEMENTATION](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md) *(Planned)*        |
| Architecture            | [ARCH-761_MARKET_RISK_SA_ARCHITECTURE](../../07_Architecture/06_Market_Risk_Standardized_Approach/ARCH-761_MARKET_RISK_SA_ARCHITECTURE.md) *(Planned)*  |

---

# 14. Summary

Delta Capital Formula는 FRTB Standardized Approach에서 시장위험의 선형 민감도를 규제자본으로 변환하는 핵심 계산 계약이다.

계산은 Delta Sensitivity 산출, Risk Weight 적용, Bucket Aggregation 및 Cross-Bucket Aggregation의 네 단계로 이루어지며, Formula는 구현 기술과 독립적으로 정의된다.

본 문서는 Bundle-006 Formula Catalog의 출발점이며 Vega, Curvature 및 Capital Aggregation Formula의 기반이 된다.

---

# 15. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
