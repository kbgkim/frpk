# KB-263 — Risk Factor Categories

---

# Document Information

| Item          | Value                  |
| ------------- | ---------------------- |
| Document ID   | KB-263                 |
| Document Name | Risk Factor Categories |
| Version       | 1.0.0                  |
| Status        | Active                 |
| Category      | Knowledge Base         |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)             |
| Domain        | Market Risk            |
| Created       | 2026-06-27             |
| Last Updated  | 2026-06-27             |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Knowledge Base](../README.md) > [KB-263 — Risk Factor Categories](KB-263_RISK_FACTOR_CATEGORIES.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [KB-262](KB-262_SENSITIVITY_BASED_METHOD.md) |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-261](KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](KB-262_SENSITIVITY_BASED_METHOD.md)
- [AN-261](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)
- [MF-461](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB) Standardized Approach에서 사용하는 **Risk Factor Categories**를 정의한다.

Risk Factor Category는 시장위험을 구성하는 기본 단위이며, Sensitivity-based Method(SBM), Risk Weight, Bucket Aggregation 및 Capital Aggregation의 공통 기준이 된다.

본 문서는 Bundle-006 Formula Catalog의 도메인 모델(Domain Knowledge Model) 역할을 수행한다.

---

# 2. Background

시장위험은 하나의 단일 위험이 아니라 다양한 시장 변수(Market Variables)의 변동으로부터 발생한다.

FRTB는 이러한 시장 변수를 **Risk Factor**로 정의하고, 성격이 유사한 Risk Factor를 **Risk Class**로 분류하여 표준화된 자본 산출 체계를 제공한다.

---

# 3. Objectives

Risk Factor Category의 목적은 다음과 같다.

* 시장위험의 체계적 분류
* 위험 민감도의 일관된 계산
* Risk Weight 적용 기준 제공
* Bucket 구조 정의
* Capital Aggregation의 기반 제공

---

# 4. Concept of Risk Factor

Risk Factor는 금융상품의 가치에 영향을 미치는 시장 변수이다.

```text id="yupqqt"
Market Variable
        │
        ▼
Risk Factor
        │
        ▼
Sensitivity
        │
        ▼
Capital
```

대표적인 Risk Factor는 금리, 환율, 신용스프레드, 주가, 상품가격 등이 있다.

---

# 5. Risk Factor Categories

FRTB-SA는 다음 다섯 개의 주요 Risk Class를 정의한다.

| Risk Class                        | Description | Typical Risk Factors    |
| --------------------------------- | ----------- | ----------------------- |
| General Interest Rate Risk (GIRR) | 일반 금리위험     | 금리곡선, Basis, Inflation  |
| Credit Spread Risk (CSR)          | 신용스프레드 위험   | Bond Spread, CDS Spread |
| Equity Risk                       | 주식가격 위험     | 개별주식, 주가지수              |
| Foreign Exchange Risk (FX)        | 환율 위험       | 통화환율                    |
| Commodity Risk                    | 상품가격 위험     | 원유, 금속, 농산물 등           |

각 Risk Class는 고유한 Risk Weight와 Bucket 체계를 가진다.

---

# 6. Risk Factor Hierarchy

Risk Factor는 계층적으로 구성된다.

```text id="5hqk4k"
Market Risk
      │
      ▼
Risk Class
      │
      ▼
Bucket
      │
      ▼
Risk Factor
      │
      ▼
Sensitivity
```

Risk Class는 최상위 분류이며, Bucket은 동일한 특성을 가진 Risk Factor의 집합이다.

---

# 7. Bucket Structure

Bucket은 유사한 위험 특성을 가진 Risk Factor를 그룹화한다.

```text id="y7m6m6"
Risk Class
      │
      ▼
Bucket
      │
      ├──── Risk Factor A
      ├──── Risk Factor B
      ├──── Risk Factor C
      └──── Risk Factor D
```

Bucket 내부에서는 상관관계를 고려하여 위험을 집계한다.

---

# 8. Relationship with Sensitivity

각 Risk Factor는 세 가지 민감도로 측정될 수 있다.

| Sensitivity | Description |
| ----------- | ----------- |
| Delta       | 1차 가격 민감도   |
| Vega        | 변동성 민감도     |
| Curvature   | 비선형(2차) 민감도 |

동일한 Risk Factor에 대해 세 민감도가 독립적으로 계산될 수 있다.

---

# 9. Risk Weight

각 Risk Factor는 감독기관이 정의한 Risk Weight를 가진다.

```text id="trm9wg"
Risk Factor
      │
      ▼
Sensitivity
      │
      ▼
Risk Weight
      │
      ▼
Weighted Sensitivity
```

Risk Weight는 Risk Class 및 Bucket에 따라 달라질 수 있다.

---

# 10. Correlation

FRTB는 위험요인 간 상관관계를 고려한다.

상관관계는 다음 두 수준에서 적용된다.

* Within-Bucket Correlation
* Across-Bucket Correlation

이를 통해 단순 합산이 아닌 위험 분산효과(Diversification Effect)를 반영한다.

---

# 11. Aggregation Framework

Risk Factor는 다음 절차를 거쳐 최종 자본으로 집계된다.

```text id="mmbfmm"
Risk Factor
      │
      ▼
Sensitivity
      │
      ▼
Weighted Sensitivity
      │
      ▼
Bucket Aggregation
      │
      ▼
Cross-Bucket Aggregation
      │
      ▼
Market Risk Capital
```

---

# 12. Relationship with Mathematical Foundation

Risk Factor Aggregation은 다음 수학 개념을 기반으로 한다.

| Mathematical Foundation      | Purpose            |
| ---------------------------- | ------------------ |
| Covariance Matrix            | 상관관계 표현            |
| Correlation Matrix           | Bucket Aggregation |
| Principal Component Analysis | 위험요인 구조 분석         |
| Eigenvalue                   | 위험 기여도 분석          |
| Eigenvector                  | 주요 위험 방향 분석        |

---

# 13. Relationship with Formula Catalog

Risk Factor Categories는 다음 Formula의 입력이 된다.

```text id="tz5ewd"
Risk Factor Categories
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

---

# 14. Relationship with FRKP

```text id="v4ut0q"
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

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) Formula Catalog의 도메인 지식을 정의한다.

---

# 15. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-261_MARKET_RISK_STANDARDIZED_APPROACH](KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)          |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](KB-262_SENSITIVITY_BASED_METHOD.md)                   |
| Analysis                | [AN-261_WHY_FRTB_REPLACED_VAR](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md) *(Planned)*          |
| Mathematical Foundation | [MF-461_COVARIANCE_MATRIX](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md) *(Planned)*              |
| Mathematical Foundation | [MF-462_PRINCIPAL_COMPONENT_ANALYSIS](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md) *(Planned)*   |
| Mathematical Foundation | [MF-463_EIGENVALUE_AND_EIGENVECTOR](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-463_EIGENVALUE_AND_EIGENVECTOR.md) *(Planned)*     |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md) *(Planned)*          |
| Formula                 | [FC-462_VEGA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-462_VEGA_CAPITAL_FORMULA.md) *(Planned)*           |
| Formula                 | [FC-463_CURVATURE_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-463_CURVATURE_CAPITAL_FORMULA.md) *(Planned)*      |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |

---

# 16. Summary

Risk Factor Categories는 FRTB Standardized Approach에서 시장위험을 구성하는 핵심 도메인 모델이다.

Risk Factor는 Risk Class와 Bucket으로 체계적으로 분류되며, Delta, Vega 및 Curvature 민감도의 계산 대상이 된다.

각 Risk Factor에는 Risk Weight가 적용되고, Bucket 및 Cross-Bucket 상관관계를 통해 최종 Market Risk Capital이 계산된다.

본 문서는 Bundle-006의 Mathematical Foundation과 Formula Catalog를 연결하는 핵심 Knowledge Asset이다.

---

# 17. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
