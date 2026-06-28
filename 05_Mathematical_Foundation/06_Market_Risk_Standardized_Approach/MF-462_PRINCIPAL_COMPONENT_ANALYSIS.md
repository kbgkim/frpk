# MF-462 — Principal Component Analysis

---

# Document Information

| Item          | Value                        |
| ------------- | ---------------------------- |
| Document ID   | MF-462                       |
| Document Name | Principal Component Analysis |
| Version       | 1.0.0                        |
| Status        | Active                       |
| Category      | Mathematical Foundation      |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                   |
| Domain        | Market Risk                  |
| Created       | 2026-06-27                   |
| Last Updated  | 2026-06-27                   |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Mathematical Foundation](../README.md) > [MF-462 — Principal Component Analysis](MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [MF-461](MF-461_COVARIANCE_MATRIX.md) |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Mathematical Foundation](../README.md) |
| ➡ Next | [MF-463](MF-463_EIGENVALUE_AND_EIGENVECTOR.md) |

### Related Documents

- [FC-461](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md)
- [FC-464](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md)
- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-261](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Principal Component Analysis(PCA)의 수학적 개념과 금융 리스크 관리에서의 활용을 정의한다.

특히 Basel III FRTB 환경에서 다수의 Risk Factor를 보다 적은 수의 독립적인 위험요인으로 변환하는 원리와, Risk Aggregation 및 Risk Factor Analysis의 수학적 기반을 제공하는 것을 목적으로 한다.

본 문서는 Bundle-006 Formula Catalog와 Risk Engine Architecture의 핵심 Mathematical Foundation이다.

---

# 2. Why Principal Component Analysis?

현대 금융시장은 수많은 Risk Factor로 구성된다.

예를 들어 금리위험만 고려하더라도 다음과 같은 금리곡선이 존재할 수 있다.

* 1개월
* 3개월
* 6개월
* 1년
* 2년
* 3년
* 5년
* 7년
* 10년
* 20년
* 30년

이 모든 금리는 서로 독립적으로 움직이지 않는다.

PCA는 이러한 높은 차원의 데이터를 몇 개의 대표적인 독립 요인(Principal Components)으로 재표현하여 위험 구조를 이해하기 쉽게 만든다.

---

# 3. Concept of PCA

Principal Component Analysis는 서로 상관된 여러 변수를 **분산(Variance)이 가장 큰 새로운 직교 축(Orthogonal Axes)** 으로 변환하는 선형 변환 기법이다.

```text
Correlated Risk Factors
          │
          ▼
Covariance Matrix
          │
          ▼
Eigen Decomposition
          │
          ▼
Principal Components
          │
          ▼
Independent Risk Factors
```

PCA는 정보를 가능한 한 유지하면서 데이터의 차원을 축소한다.

---

# 4. Mathematical Foundation

PCA는 공분산 행렬을 기반으로 한다.

공분산 행렬

[
\Sigma
]

에 대해 다음 고유값 문제를 푼다.

[
\Sigma v_i
==========

\lambda_i v_i
]

여기서

| Symbol      | Description                   |
| ----------- | ----------------------------- |
| (\Sigma)    | Covariance Matrix             |
| (v_i)       | i번째 Principal Component(고유벡터) |
| (\lambda_i) | 해당 Component의 분산(고유값)         |

---

# 5. Interpretation

PCA는 기존 좌표계를 새로운 좌표계로 회전시키는 과정으로 이해할 수 있다.

```text
Original Risk Factors
        │
        ▼
Coordinate Rotation
        │
        ▼
Principal Components
```

새로운 축은 다음 조건을 만족한다.

* 서로 직교(Orthogonal)
* 최대 분산 순으로 정렬
* 서로 독립적인 정보 제공

---

# 6. Principal Components in Interest Rate Risk

금리곡선 분석에서는 일반적으로 다음 세 가지 주성분이 전체 변동의 대부분을 설명한다.

| Principal Component | Financial Interpretation       |
| ------------------- | ------------------------------ |
| PC1                 | Parallel Shift (전체 금리 수준 변화)   |
| PC2                 | Slope Change (장단기 금리 기울기 변화)   |
| PC3                 | Curvature Change (중간 만기 굴곡 변화) |

실무에서는 이 세 요인이 금리 변동의 대부분을 설명하는 경우가 많다.

---

# 7. Relationship with Covariance Matrix

PCA는 공분산 행렬 없이는 수행될 수 없다.

```text
Risk Factors
        │
        ▼
Covariance Matrix
        │
        ▼
Eigenvalue Decomposition
        │
        ▼
Principal Components
```

공분산 행렬은 PCA의 입력이며, PCA는 공분산 구조를 새로운 좌표계로 변환한다.

---

# 8. Dimensionality Reduction

PCA는 전체 정보를 유지하면서 차원을 축소할 수 있다.

예를 들어

```text
11 Interest Rate Factors

↓

PCA

↓

3 Principal Components

↓

95% Variance Explained
```

이와 같이 적은 수의 요인으로 대부분의 위험을 설명할 수 있다.

---

# 9. Role in Market Risk

PCA는 다음과 같은 목적에 활용된다.

| Purpose               | Description  |
| --------------------- | ------------ |
| Risk Factor Analysis  | 위험 구조 분석     |
| Yield Curve Analysis  | 금리곡선 분석      |
| Scenario Construction | 스트레스 시나리오 구성 |
| Factor Modeling       | 요인모형 구축      |
| Model Validation      | 위험모형 검증      |

FRTB Standardized Approach의 규제 산식 자체는 PCA를 직접 요구하지 않지만, 내부 분석과 Risk Engine 설계에서는 매우 중요한 기법이다.

---

# 10. Relationship with Eigenvalue and Eigenvector

PCA는 고유값 분해를 기반으로 한다.

```text
Covariance Matrix
        │
        ▼
Eigenvalue
        │
        ▼
Eigenvector
        │
        ▼
Principal Components
```

고유벡터는 새로운 축을 정의하고, 고유값은 각 축이 설명하는 분산의 크기를 나타낸다.

---

# 11. Relationship with Formula Catalog

PCA는 다음 Formula를 직접 지원한다.

| Formula | Purpose                 |
| ------- | ----------------------- |
| FC-461  | Delta Risk Analysis     |
| FC-462  | Vega Risk Analysis      |
| FC-463  | Curvature Risk Analysis |
| FC-464  | Capital Aggregation     |

또한 향후 Internal Models Approach(IMA) 및 Stress Testing에서도 재사용된다.

---

# 12. Relationship with FRKP

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

PCA는 Covariance Matrix와 Eigenvalue/Eigenvector 사이를 연결하는 핵심 Mathematical Foundation이다.

---

# 13. Key Insights

* PCA는 차원 축소 알고리즘이면서 동시에 위험 구조 분석 도구이다.
* PCA는 상관된 Risk Factor를 서로 독립적인 Principal Component로 변환한다.
* 공분산 행렬이 PCA의 입력이다.
* 고유벡터는 새로운 위험 축을 정의한다.
* 고유값은 각 축이 설명하는 위험의 크기를 나타낸다.
* 금리곡선 분석에서는 Parallel Shift, Slope, Curvature가 대표적인 주성분이다.

---

# 14. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-261_MARKET_RISK_STANDARDIZED_APPROACH](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)          |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)                   |
| Knowledge               | [KB-263_RISK_FACTOR_CATEGORIES](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)                     |
| Analysis                | [AN-261_WHY_FRTB_REPLACED_VAR](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)                      |
| Mathematical Foundation | [MF-461_COVARIANCE_MATRIX](MF-461_COVARIANCE_MATRIX.md)                          |
| Mathematical Foundation | [MF-463_EIGENVALUE_AND_EIGENVECTOR](MF-463_EIGENVALUE_AND_EIGENVECTOR.md) *(Planned)*     |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md) *(Planned)*          |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |

---

# 15. Summary

Principal Component Analysis는 공분산 행렬을 기반으로 다수의 상관된 Risk Factor를 소수의 독립적인 Principal Component로 변환하는 핵심 수학 기법이다.

금융 리스크 관리에서는 금리곡선, 신용스프레드, 포트폴리오 위험구조 분석 등에 널리 활용되며, FRTB Risk Engine의 위험요인 분석과 시나리오 구성에도 중요한 기반을 제공한다.

본 문서는 Bundle-006의 Covariance Matrix와 Eigenvalue/Eigenvector를 연결하는 핵심 Mathematical Foundation이며, Formula Catalog와 Risk Engine Architecture의 수학적 토대를 제공한다.

---

# 16. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
