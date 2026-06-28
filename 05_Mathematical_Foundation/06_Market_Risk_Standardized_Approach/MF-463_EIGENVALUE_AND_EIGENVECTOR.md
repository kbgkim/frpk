# MF-463 — Eigenvalue and Eigenvector

---

# Document Information

| Item          | Value                      |
| ------------- | -------------------------- |
| Document ID   | MF-463                     |
| Document Name | Eigenvalue and Eigenvector |
| Version       | 1.0.0                      |
| Status        | Active                     |
| Category      | Mathematical Foundation    |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                 |
| Domain        | Market Risk                |
| Created       | 2026-06-27                 |
| Last Updated  | 2026-06-27                 |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Mathematical Foundation](../README.md) > [MF-463 — Eigenvalue and Eigenvector](MF-463_EIGENVALUE_AND_EIGENVECTOR.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [MF-462](MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md) |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Mathematical Foundation](../README.md) |
| ➡ Next | None |

### Related Documents

- [FC-461](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md)
- [FC-462](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-462_VEGA_CAPITAL_FORMULA.md)
- [FC-463](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-463_CURVATURE_CAPITAL_FORMULA.md)
- [FC-464](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md)
- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Eigenvalue(고유값)와 Eigenvector(고유벡터)의 수학적 개념과 금융 리스크 관리에서의 의미를 정의한다.

특히 Basel III Fundamental Review of the Trading Book(FRTB) 환경에서 Risk Factor의 구조를 분석하고 Principal Component Analysis(PCA)를 수행하기 위한 핵심 Mathematical Foundation을 제공한다.

본 문서는 Bundle-006 Formula Catalog와 Risk Engine Architecture의 수학적 기반을 구성한다.

---

# 2. Why Eigenvalue and Eigenvector?

공분산 행렬은 Risk Factor 간의 관계를 표현하지만, 행렬 자체만으로는 어떤 위험요인이 가장 중요한지 쉽게 알 수 없다.

고유값 분해(Eigenvalue Decomposition)는 공분산 행렬을 분석하여

* 주요 위험 방향
* 위험의 크기
* 위험의 구조

를 추출할 수 있도록 한다.

---

# 3. Concept

행렬 (A)가 벡터의 방향을 유지하면서 크기만 변경시키는 경우가 있다.

이때

* 방향이 변하지 않는 벡터를 **Eigenvector**
* 확대 또는 축소 비율을 **Eigenvalue**

라고 한다.

```text
Linear Transformation
        │
        ▼
Special Direction
        │
        ▼
Eigenvector
        │
        ▼
Scaling Factor
        │
        ▼
Eigenvalue
```

---

# 4. Mathematical Definition

고유값 문제는 다음과 같이 정의된다.

[
A\mathbf{v}
===========

\lambda\mathbf{v}
]

여기서

| Symbol       | Description   |
| ------------ | ------------- |
| (A)          | Square Matrix |
| (\mathbf{v}) | Eigenvector   |
| (\lambda)    | Eigenvalue    |

이는 행렬 변환 이후에도 벡터의 방향은 유지되고 크기만 (\lambda)배 변화함을 의미한다.

---

# 5. Geometric Interpretation

일반적인 행렬은 벡터의 방향과 크기를 모두 변경한다.

그러나 고유벡터는 변환 후에도 동일한 직선 위에 존재한다.

```text
Matrix Transformation

↓

Most Vectors
Direction + Magnitude Change

↓

Eigenvector
Magnitude Change Only
```

따라서 고유벡터는 행렬이 가진 **고유한 방향(Intrinsic Direction)** 을 나타낸다.

---

# 6. Relationship with Covariance Matrix

공분산 행렬에 고유값 분해를 적용하면 다음을 얻을 수 있다.

```text
Covariance Matrix
        │
        ▼
Eigenvalue Decomposition
        │
        ├── Eigenvalues
        └── Eigenvectors
```

* 고유벡터 → 새로운 위험 축
* 고유값 → 해당 축이 설명하는 분산의 크기

---

# 7. Relationship with Principal Component Analysis

PCA는 공분산 행렬의 고유값 분해를 기반으로 수행된다.

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

각 Principal Component는 하나의 고유벡터에 대응한다.

---

# 8. Financial Interpretation

금리곡선을 예로 들면

```text
Yield Curve

↓

Eigenvector 1

↓

Parallel Shift

↓

Eigenvector 2

↓

Slope Change

↓

Eigenvector 3

↓

Curvature Change
```

즉 고유벡터는 시장이 실제로 움직이는 대표적인 방향을 나타낸다.

---

# 9. Interpretation of Eigenvalues

고유값은 각 고유벡터가 설명하는 위험의 크기를 나타낸다.

예를 들어

| Component | Explained Variance |
| --------- | -----------------: |
| PC1       |                82% |
| PC2       |                12% |
| PC3       |                 4% |
| Others    |                 2% |

위와 같은 결과는 첫 번째 주성분이 전체 위험의 대부분을 설명한다는 의미이다.

---

# 10. Role in Market Risk

Eigenvalue와 Eigenvector는 다음 업무에 활용된다.

| Area                    | Purpose       |
| ----------------------- | ------------- |
| Yield Curve Analysis    | 금리구조 분석       |
| Risk Factor Compression | 위험요인 축소       |
| Stress Scenario Design  | 스트레스 시나리오 설계  |
| Model Validation        | 모델 검증         |
| Factor Modeling         | 요인모형 구축       |
| Portfolio Analysis      | 포트폴리오 위험구조 분석 |

---

# 11. Mathematical Properties

| Property                      | Description               |
| ----------------------------- | ------------------------- |
| Eigenvectors                  | 서로 독립적인 방향(대칭행렬에서는 직교 가능) |
| Eigenvalues                   | 분산 또는 에너지의 크기             |
| Ordering                      | 일반적으로 큰 고유값부터 정렬          |
| Positive Semi-definite Matrix | 공분산 행렬의 고유값은 음수가 될 수 없음   |

---

# 12. Relationship with Formula Catalog

Eigenvalue와 Eigenvector는 직접 규제 산식에 등장하지는 않지만, Formula의 배경이 되는 위험 구조를 설명한다.

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
        │
        ▼
FC-462
Vega Capital Formula
        │
        ▼
FC-463
Curvature Capital Formula
        │
        ▼
FC-464
Capital Aggregation
```

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

[MF-463](MF-463_EIGENVALUE_AND_EIGENVECTOR.md)은 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) Mathematical Foundation의 마지막 문서이며, Formula Catalog로 연결되는 핵심 수학적 기반이다.

---

# 14. Key Insights

* 고유벡터는 행렬이 가진 본질적인 방향을 나타낸다.
* 고유값은 해당 방향이 설명하는 위험의 크기를 나타낸다.
* PCA는 공분산 행렬의 고유값 분해를 기반으로 수행된다.
* 금융시장에서는 금리곡선, 신용스프레드, 포트폴리오 위험 구조 분석 등에 널리 활용된다.
* FRTB의 Risk Engine에서는 위험요인 분석과 시나리오 구성의 중요한 수학적 도구이다.

---

# 15. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-261_MARKET_RISK_STANDARDIZED_APPROACH](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)          |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)                   |
| Knowledge               | [KB-263_RISK_FACTOR_CATEGORIES](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)                     |
| Analysis                | [AN-261_WHY_FRTB_REPLACED_VAR](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)                      |
| Mathematical Foundation | [MF-461_COVARIANCE_MATRIX](MF-461_COVARIANCE_MATRIX.md)                          |
| Mathematical Foundation | [MF-462_PRINCIPAL_COMPONENT_ANALYSIS](MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md)               |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md) *(Planned)*          |
| Formula                 | [FC-462_VEGA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-462_VEGA_CAPITAL_FORMULA.md) *(Planned)*           |
| Formula                 | [FC-463_CURVATURE_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-463_CURVATURE_CAPITAL_FORMULA.md) *(Planned)*      |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |

---

# 16. Summary

Eigenvalue와 Eigenvector는 공분산 행렬을 해석하고 Risk Factor의 구조를 분석하기 위한 핵심 수학 개념이다.

고유벡터는 위험이 가장 크게 변화하는 방향을 정의하고, 고유값은 각 방향이 설명하는 위험의 크기를 나타낸다.

이러한 개념은 Principal Component Analysis의 기반이 되며, 금융 리스크 관리에서는 금리곡선 분석, 위험요인 축소, 포트폴리오 위험 구조 분석 및 Risk Engine 설계에 폭넓게 활용된다.

본 문서는 Bundle-006 Mathematical Foundation을 완성하며, 이후 Formula Catalog(FC-461~FC-464)의 수학적 토대를 제공한다.

---

# 17. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
