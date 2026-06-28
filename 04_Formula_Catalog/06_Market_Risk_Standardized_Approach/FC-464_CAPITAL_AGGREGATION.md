# FC-464 — Capital Aggregation

---

# Document Information

| Item             | Value               |
| ---------------- | ------------------- |
| Document ID      | FC-464              |
| Document Name    | Capital Aggregation |
| Version          | 1.0.0               |
| Status           | Active              |
| Category         | Formula Catalog     |
| Parent Bundle    | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)          |
| Domain           | Market Risk         |
| Created          | 2026-06-27          |
| Last Updated     | 2026-06-27          |
| Formula Standard | FRKP-FORM-001       |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Formula Catalog](../README.md) > [FC-464 — Capital Aggregation](FC-464_CAPITAL_AGGREGATION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-463](FC-463_CURVATURE_CAPITAL_FORMULA.md) |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | None |

### Related Documents

- [FC-461](FC-461_DELTA_CAPITAL_FORMULA.md)
- [FC-462](FC-462_VEGA_CAPITAL_FORMULA.md)
- [FC-463](FC-463_CURVATURE_CAPITAL_FORMULA.md)
- [IMP-461](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md)
- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB) Standardized Approach(SA)의 **Capital Aggregation Formula**를 정의한다.

Capital Aggregation Formula는 Delta Capital, Vega Capital 및 Curvature Capital을 하나의 최종 Market Risk Capital로 통합하기 위한 규제 계산 계약(Calculation Contract)을 제공한다.

본 문서는 구현 기술과 독립적인 Formula Catalog 문서이며, FRTB Standardized Approach의 최상위 Formula를 정의한다.

---

# 2. Business Purpose

시장위험은 하나의 위험으로 구성되지 않는다.

규제 목적에서는 다음 세 가지 위험을 모두 고려해야 한다.

* Delta Risk
* Vega Risk
* Curvature Risk

Capital Aggregation은 이 세 위험을 통합하여 금융기관이 보유해야 하는 최종 규제자본을 산출한다.

---

# 3. Regulatory Perspective

FRTB Standardized Approach에서는 각 위험 유형을 독립적으로 계산한 후 최종 규제자본으로 집계한다.

```text
Delta Capital
        │
        ▼
Vega Capital
        │
        ▼
Curvature Capital
        │
        ▼
Market Risk Capital
```

Capital Aggregation은 Standardized Approach의 최종 계산 단계이다.

---

# 4. Mathematical Definition

Capital Aggregation은 다음 계산 절차를 따른다.

## Step 1. Delta Capital

[
K_{\Delta}
]

---

## Step 2. Vega Capital

[
K_{Vega}
]

---

## Step 3. Curvature Capital

[
K_{Curvature}
]

---

## Step 4. Final Market Risk Capital

논리적으로 최종 자본은 세 구성요소를 기반으로 산출된다.

[
K_{MR}
======

f
(
K_{\Delta},
K_{Vega},
K_{Curvature}
)
]

여기서

| Symbol          | Description               |
| --------------- | ------------------------- |
| (K_{MR})        | Final Market Risk Capital |
| (K_{\Delta})    | Delta Capital             |
| (K_{Vega})      | Vega Capital              |
| (K_{Curvature}) | Curvature Capital         |

> **설계 원칙:** 본 문서는 계산 계약을 정의하는 Formula Catalog이므로, 실제 감독규정에서 위험 유형별 집계 방식이나 추가 규제 요소가 변경될 수 있음을 고려하여 최종 집계 함수는 기술 중립적인 형태로 정의한다. 구체적인 구현은 Implementation Guide에서 규제 버전에 맞추어 적용한다.

---

# 5. Formula Interpretation

Capital Aggregation은 다음 논리적 흐름으로 수행된다.

```text
Delta Capital
        │
        ├────────────┐
        │            │
Vega Capital   Curvature Capital
        │            │
        └─────┬──────┘
              ▼
     Capital Aggregation
              │
              ▼
 Final Market Risk Capital
```

각 구성요소는 독립적으로 계산되며, 최종 단계에서 통합된다.

---

# 6. Input Contract

| Input                        | Required | Description |
| ---------------------------- | :------: | ----------- |
| Delta Capital                |     ✔    | FC-461 결과   |
| Vega Capital                 |     ✔    | FC-462 결과   |
| Curvature Capital            |     ✔    | FC-463 결과   |
| Regulatory Aggregation Rules |     ✔    | 감독기관 집계 규칙  |

---

# 7. Computation Contract

```text
Receive Delta Capital
        │
        ▼
Receive Vega Capital
        │
        ▼
Receive Curvature Capital
        │
        ▼
Validate Inputs
        │
        ▼
Apply Regulatory Aggregation
        │
        ▼
Return Market Risk Capital
```

계산은 항상 동일 입력에 대해 동일 결과를 반환해야 한다.

---

# 8. Output Contract

| Output              | Description                 |
| ------------------- | --------------------------- |
| Market Risk Capital | 최종 시장위험 규제자본                |
| Capital Components  | Delta, Vega, Curvature 구성요소 |
| Aggregation Result  | 집계 결과                       |

---

# 9. Formula Engine Model

```text
Delta Provider
        │
        ▼
Vega Provider
        │
        ▼
Curvature Provider
        │
        ▼
Aggregation Engine
        │
        ▼
Market Risk Capital Builder
```

Formula Engine은 계산 책임의 논리적 분리를 나타내며 특정 구현 구조를 의미하지 않는다.

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
FC-461
Delta Capital
        │
        ▼
FC-462
Vega Capital
        │
        ▼
FC-463
Curvature Capital
        │
        ▼
FC-464
Capital Aggregation
```

Mathematical Foundation은 개별 위험 계산과 위험 집계의 수학적 기반을 제공한다.

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

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) Formula Catalog의 최종 Formula이며, 이후 Implementation Guide와 Architecture Guide의 직접적인 입력이 된다.

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
| Formula                 | [FC-463_CURVATURE_CAPITAL_FORMULA](FC-463_CURVATURE_CAPITAL_FORMULA.md)                  |
| Implementation          | [IMP-461_FRTB_SA_IMPLEMENTATION](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md) *(Planned)*        |
| Architecture            | [ARCH-761_MARKET_RISK_SA_ARCHITECTURE](../../07_Architecture/06_Market_Risk_Standardized_Approach/ARCH-761_MARKET_RISK_SA_ARCHITECTURE.md) *(Planned)*  |

---

# 14. Summary

Capital Aggregation Formula는 FRTB Standardized Approach에서 Delta, Vega 및 Curvature 위험을 최종 Market Risk Capital로 통합하는 최상위 계산 계약이다.

개별 위험은 각각 독립적으로 계산된 후 규제 집계 규칙에 따라 하나의 규제자본으로 통합된다.

본 문서는 Bundle-006 Formula Catalog의 최종 문서이며, 이후 Risk Engine 구현과 시스템 아키텍처 설계의 기준이 된다.

---

# 15. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
