# MF-461 — Covariance Matrix

---

# Document Information

| Item          | Value                   |
| ------------- | ----------------------- |
| Document ID   | MF-461                  |
| Document Name | Covariance Matrix       |
| Version       | 1.0.0                   |
| Status        | Active                  |
| Category      | Mathematical Foundation |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)              |
| Domain        | Market Risk             |
| Created       | 2026-06-27              |
| Last Updated  | 2026-06-27              |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Mathematical Foundation](../README.md) > [MF-461 — Covariance Matrix](MF-461_COVARIANCE_MATRIX.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Mathematical Foundation](../README.md) |
| ➡ Next | [MF-462](MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md) |

### Related Documents

- [FC-461](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md)
- [FC-464](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md)
- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-261](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Covariance Matrix(공분산 행렬)의 수학적 개념과 금융 리스크 관리에서의 의미를 정의한다.

특히 Basel III FRTB Standardized Approach에서 Risk Factor 간의 공동 변동성을 이해하고, Sensitivity Aggregation 및 Capital Aggregation의 수학적 기반을 제공하는 것을 목적으로 한다.

본 문서는 Bundle-006 Formula Catalog의 핵심 Mathematical Foundation이다.

---

# 2. Why Covariance Matrix?

FRTB는 위험요인을 단순히 합산하지 않는다.

금리, 환율, 주가, 신용스프레드와 같은 Risk Factor는 서로 영향을 주고받으며 동시에 움직이는 경우가 많다.

따라서 전체 위험을 정확히 계산하려면 **개별 위험의 크기뿐 아니라 함께 움직이는 정도**를 고려해야 한다.

Covariance Matrix는 이러한 공동 변동성을 정량적으로 표현하는 도구이다.

---

# 3. Concept of Covariance

공분산(Covariance)은 두 확률변수가 평균을 기준으로 함께 어떻게 변하는지를 나타낸다.

* 양(+)의 공분산: 함께 증가하거나 함께 감소하는 경향
* 음(-)의 공분산: 한쪽이 증가할 때 다른 쪽은 감소하는 경향
* 0에 가까운 공분산: 선형적인 공동 움직임이 거의 없음

공분산은 방향성과 크기를 함께 표현하지만, 변수의 단위에 영향을 받는다.

---

# 4. Mathematical Definition

공분산은 다음과 같이 정의된다.

[
\operatorname{Cov}(X,Y)
=======================

E[(X-\mu_X)(Y-\mu_Y)]
]

여기서

| Symbol         | Description      |
| -------------- | ---------------- |
| (X, Y)         | 두 확률변수           |
| (\mu_X, \mu_Y) | 각 변수의 평균         |
| (E[\cdot])     | 기댓값(Expectation) |

---

# 5. Covariance Matrix

여러 Risk Factor가 존재하면 공분산을 행렬 형태로 표현한다.

[
\Sigma
======

\begin{bmatrix}
\sigma_{11} & \sigma_{12} & \cdots & \sigma_{1n}\
\sigma_{21} & \sigma_{22} & \cdots & \sigma_{2n}\
\vdots & \vdots & \ddots & \vdots\
\sigma_{n1} & \sigma_{n2} & \cdots & \sigma_{nn}
\end{bmatrix}
]

대각 원소는 각 Risk Factor의 분산(Variance)이며, 비대각 원소는 서로 다른 Risk Factor 간 공분산이다.

---

# 6. Interpretation

공분산 행렬은 위험요인 간의 상호 관계를 하나의 구조로 표현한다.

```text
Risk Factor
      │
      ▼
Covariance
      │
      ▼
Covariance Matrix
      │
      ▼
Risk Aggregation
```

행렬 전체는 개별 위험이 아니라 **위험 시스템(System of Risks)** 을 표현한다.

---

# 7. Relationship with Correlation Matrix

공분산과 상관계수는 밀접한 관계를 가진다.

[
\rho_{ij}
=========

\frac{\operatorname{Cov}(X_i,X_j)}
{\sigma_i\sigma_j}
]

공분산은 단위에 영향을 받지만, 상관계수는 -1에서 +1 사이의 무차원 값으로 정규화된다.

FRTB는 감독기관이 정의한 상관계수를 사용하여 위험을 집계하며, 공분산 행렬은 그 수학적 기반이 된다.

---

# 8. Role in FRTB

FRTB Standardized Approach에서 Covariance Matrix는 다음 계산의 기반이 된다.

```text
Risk Factors
        │
        ▼
Sensitivity
        │
        ▼
Weighted Sensitivity
        │
        ▼
Covariance Structure
        │
        ▼
Bucket Aggregation
        │
        ▼
Capital Aggregation
```

즉 위험요인 간 분산효과(Diversification Effect)를 정량적으로 반영하는 핵심 수학 구조이다.

---

# 9. Portfolio Risk

여러 위험요인을 동시에 고려하는 포트폴리오의 분산은 공분산 행렬을 이용하여 계산한다.

[
\sigma_p^2
==========

\mathbf{w}^{T}
\Sigma
\mathbf{w}
]

여기서

| Symbol       | Description          |
| ------------ | -------------------- |
| (\mathbf{w}) | 위험요인 또는 포트폴리오 가중치 벡터 |
| (\Sigma)     | 공분산 행렬               |

이 식은 개별 위험뿐 아니라 위험요인 간 상호작용을 함께 반영한다.

---

# 10. Properties

Covariance Matrix는 다음 특성을 가진다.

| Property               | Description                   |
| ---------------------- | ----------------------------- |
| Square Matrix          | 정사각행렬                         |
| Symmetric              | 대칭행렬                          |
| Positive Semi-definite | 준양의 정부호                       |
| Real-valued            | 실수 행렬                         |
| Dimension              | Risk Factor 수 × Risk Factor 수 |

이러한 성질은 이후 PCA와 고유값 분해의 기반이 된다.

---

# 11. Relationship with Other Mathematical Foundations

```text
Covariance Matrix
        │
        ▼
Correlation Matrix
        │
        ▼
Principal Component Analysis
        │
        ▼
Eigenvalue
        │
        ▼
Eigenvector
```

공분산 행렬은 Bundle-006 Mathematical Foundation의 출발점이다.

---

# 12. Relationship with Formula Catalog

Covariance Matrix는 다음 Formula에서 사용된다.

| Formula | Purpose             |
| ------- | ------------------- |
| FC-461  | Delta Capital       |
| FC-462  | Vega Capital        |
| FC-463  | Curvature Capital   |
| FC-464  | Capital Aggregation |

---

# 13. Relationship with FRKP

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
MF-461
      │
      ▼
MF-462
      │
      ▼
MF-463
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

[MF-461](MF-461_COVARIANCE_MATRIX.md)은 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) Mathematical Foundation의 첫 번째 문서이며, 이후 PCA와 Eigenvalue/Eigenvector 문서의 기반이 된다.

---

# 14. Key Insights

* 공분산은 두 위험요인의 공동 변동성을 측정한다.
* 공분산 행렬은 여러 Risk Factor의 관계를 하나의 구조로 표현한다.
* FRTB의 Risk Aggregation은 공분산 구조를 기반으로 위험을 집계한다.
* Portfolio Risk는 공분산 행렬 없이는 정확하게 계산할 수 없다.
* PCA, Eigenvalue 및 Eigenvector는 모두 공분산 행렬에서 출발한다.

---

# 15. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-261_MARKET_RISK_STANDARDIZED_APPROACH](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)          |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)                   |
| Knowledge               | [KB-263_RISK_FACTOR_CATEGORIES](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)                     |
| Analysis                | [AN-261_WHY_FRTB_REPLACED_VAR](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)                      |
| Mathematical Foundation | [MF-462_PRINCIPAL_COMPONENT_ANALYSIS](MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md) *(Planned)*   |
| Mathematical Foundation | [MF-463_EIGENVALUE_AND_EIGENVECTOR](MF-463_EIGENVALUE_AND_EIGENVECTOR.md) *(Planned)*     |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md) *(Planned)*          |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |

---

# 16. Summary

Covariance Matrix는 여러 Risk Factor의 공동 변동성을 표현하는 핵심 수학 구조이며, FRTB Standardized Approach의 Risk Aggregation을 이해하기 위한 가장 중요한 Mathematical Foundation 중 하나이다.

공분산 행렬은 개별 위험을 단순히 합산하는 것이 아니라 위험요인 간의 상호관계를 반영하여 포트폴리오 전체 위험을 계산할 수 있게 한다.

또한 Principal Component Analysis(PCA), Eigenvalue 및 Eigenvector와 같은 고급 수학 기법의 출발점이 되며, Bundle-006 Formula Catalog의 수학적 기반을 제공한다.

---

# 17. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
