# FC-463 — Curvature Capital Formula

---

# Document Information

| Item             | Value                     |
| ---------------- | ------------------------- |
| Document ID      | FC-463                    |
| Document Name    | Curvature Capital Formula |
| Version          | 1.0.0                     |
| Status           | Active                    |
| Category         | Formula Catalog           |
| Parent Bundle    | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                |
| Domain           | Market Risk               |
| Created          | 2026-06-27                |
| Last Updated     | 2026-06-27                |
| Formula Standard | FRKP-FORM-001             |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Formula Catalog](../README.md) > [FC-463 — Curvature Capital Formula](FC-463_CURVATURE_CAPITAL_FORMULA.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-462](FC-462_VEGA_CAPITAL_FORMULA.md) |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-464](FC-464_CAPITAL_AGGREGATION.md) |

### Related Documents

- [FC-461](FC-461_DELTA_CAPITAL_FORMULA.md)
- [FC-462](FC-462_VEGA_CAPITAL_FORMULA.md)
- [FC-464](FC-464_CAPITAL_AGGREGATION.md)
- [IMP-461](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md)
- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB) Standardized Approach(SA)의 **Curvature Capital Formula**를 정의한다.

Curvature Capital Formula는 금융상품의 **비선형 가격 변화(Second-order Price Sensitivity)** 를 기반으로 시장위험 규제자본을 계산하기 위한 공식이다.

본 문서는 구현 기술과 독립적인 Formula Catalog 문서이며, Curvature Risk 계산에 대한 표준 Calculation Contract를 제공한다.

---

# 2. Business Purpose

Delta Risk는 작은 가격 변화에 대한 선형 반응을 측정하고, Vega Risk는 변동성 변화에 대한 민감도를 측정한다.

그러나 옵션과 같은 비선형 상품은 시장가격이 크게 움직일 경우 Delta만으로는 실제 위험을 충분히 설명할 수 없다.

Curvature Capital의 목적은 다음과 같다.

* 비선형 가격효과 반영
* Gamma 효과의 규제자본 반영
* 큰 시장충격에 대한 손실 측정
* 옵션 포트폴리오 위험의 현실적 평가

---

# 3. Regulatory Perspective

FRTB Standardized Approach에서 Curvature Risk는 Sensitivity-based Method(SBM)의 세 번째 핵심 구성요소이다.

계산 흐름은 다음과 같다.

```text
Risk Factor Shock
        │
        ▼
Full Revaluation
        │
        ▼
Curvature Sensitivity
        │
        ▼
Risk Weight
        │
        ▼
Bucket Aggregation
        │
        ▼
Capital Aggregation
```

Curvature Risk는 단순 미분값이 아니라 규제에서 정의한 충격(Shock) 시나리오를 적용한 결과를 기반으로 계산된다.

---

# 4. Mathematical Definition

## Step 1. Apply Regulatory Shock

각 Risk Factor에 대해 감독기관이 정의한 상·하방 충격을 적용한다.

[
RF_i^{+},; RF_i^{-}
]

---

## Step 2. Full Revaluation

충격 적용 후 금융상품의 가치를 다시 계산한다.

[
V^{+},;
V^{-}
]

---

## Step 3. Curvature Risk

Curvature Effect는 Delta 효과를 제거한 후 계산한다.

[
CV_i
====

## V^{shock}

## V^{base}

\Delta_i
]

여기서

| Symbol      | Description      |
| ----------- | ---------------- |
| (V^{base})  | 충격 이전 가치         |
| (V^{shock}) | 충격 이후 가치         |
| (\Delta_i)  | Delta Effect     |
| (CV_i)      | Curvature Effect |

---

## Step 4. Weighted Curvature

Risk Weight를 적용한다.

[
WCV_i
=====

RW_i
\times
CV_i
]

---

## Step 5. Bucket Aggregation

동일 Bucket 내 Curvature Risk를 상관관계를 이용하여 집계한다.

[
K_b
===

\sqrt{
\sum_i\sum_j
\rho_{ij}
WCV_i
WCV_j
}
]

---

## Step 6. Capital Aggregation

Bucket Capital을 포트폴리오 수준으로 집계한다.

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

---

# 5. Formula Interpretation

Curvature Capital Formula는 다음 절차를 따른다.

```text
Apply Regulatory Shock
        │
        ▼
Full Revaluation
        │
        ▼
Remove Delta Effect
        │
        ▼
Weighted Curvature
        │
        ▼
Bucket Capital
        │
        ▼
Total Curvature Capital
```

Curvature Risk는 **충격 이후 실제 가격 변화에서 선형 효과를 제거한 잔여 비선형 효과**를 측정한다.

---

# 6. Input Contract

| Input                  | Required | Description         |
| ---------------------- | :------: | ------------------- |
| Risk Factors           |     ✔    | 대상 위험요인             |
| Base Market Value      |     ✔    | 충격 이전 가치            |
| Shocked Market Value   |     ✔    | 충격 이후 가치            |
| Delta Sensitivity      |     ✔    | Delta 효과 제거용        |
| Risk Weight            |     ✔    | 감독기관 지정 Risk Weight |
| Bucket Definition      |     ✔    | Bucket 분류           |
| Correlation Parameters |     ✔    | 상관관계                |

---

# 7. Computation Contract

```text
Collect Market Values
        │
        ▼
Apply Regulatory Shock
        │
        ▼
Full Revaluation
        │
        ▼
Subtract Delta Effect
        │
        ▼
Apply Risk Weight
        │
        ▼
Aggregate Within Bucket
        │
        ▼
Aggregate Across Buckets
        │
        ▼
Return Curvature Capital
```

모든 계산은 동일 입력에 대해 동일 결과를 반환해야 한다.

---

# 8. Output Contract

| Output                   | Description       |
| ------------------------ | ----------------- |
| Curvature Effect         | 비선형 가격효과          |
| Weighted Curvature       | Risk Weight 적용 결과 |
| Bucket Curvature Capital | Bucket 수준 자본      |
| Total Curvature Capital  | 최종 Curvature 규제자본 |

---

# 9. Formula Engine Model

```text
Shock Generator
        │
        ▼
Revaluation Engine
        │
        ▼
Delta Adjustment
        │
        ▼
Risk Weight Calculator
        │
        ▼
Bucket Aggregator
        │
        ▼
Capital Builder
```

Formula Engine은 논리적 계산 책임을 정의하며 특정 구현을 의미하지 않는다.

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
FC-463
Curvature Capital Formula
```

Curvature Risk Aggregation은 공분산 구조와 상관관계를 기반으로 수행된다.

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

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) Formula Catalog의 세 번째 핵심 Formula이다.

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
| Formula                 | [FC-462_VEGA_CAPITAL_FORMULA](FC-462_VEGA_CAPITAL_FORMULA.md)                       |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |
| Implementation          | [IMP-461_FRTB_SA_IMPLEMENTATION](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md) *(Planned)*        |
| Architecture            | [ARCH-761_MARKET_RISK_SA_ARCHITECTURE](../../07_Architecture/06_Market_Risk_Standardized_Approach/ARCH-761_MARKET_RISK_SA_ARCHITECTURE.md) *(Planned)*  |

---

# 14. Summary

Curvature Capital Formula는 FRTB Standardized Approach에서 비선형 가격 변화를 규제자본으로 변환하는 계산 계약이다.

계산은 규제 충격 적용, Full Revaluation, Delta 효과 제거, Risk Weight 적용 및 Bucket·Cross-Bucket Aggregation의 순서로 수행된다.

본 Formula는 Delta와 Vega Formula를 보완하여 옵션 및 기타 비선형 금융상품의 위험을 보다 현실적으로 반영하며, 이후 Capital Aggregation Formula의 입력으로 사용된다.

---

# 15. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
