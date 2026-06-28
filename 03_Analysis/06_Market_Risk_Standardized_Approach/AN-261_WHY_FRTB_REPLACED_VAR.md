# AN-261 — Why FRTB Replaced VaR

---

# Document Information

| Item          | Value                 |
| ------------- | --------------------- |
| Document ID   | AN-261                |
| Document Name | Why FRTB Replaced VaR |
| Version       | 1.0.0                 |
| Status        | Active                |
| Category      | Analysis              |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)            |
| Domain        | Market Risk           |
| Created       | 2026-06-27            |
| Last Updated  | 2026-06-27            |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Analysis](../README.md) > [AN-261 — Why FRTB Replaced VaR](AN-261_WHY_FRTB_REPLACED_VAR.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Analysis](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-261](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)
- [KB-263](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)
- [MF-461](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel Committee가 기존 Value at Risk(VaR) 기반 시장위험 규제체계를 폐기하고, Fundamental Review of the Trading Book(FRTB)을 도입하게 된 배경과 이유를 분석한다.

본 문서는 규제 변화의 역사적 배경, 기존 체계의 한계, 새로운 접근법의 설계 철학 및 금융기관에 미치는 영향을 분석하며, Bundle-006 Formula 및 Architecture의 설계 근거를 제공한다.

---

# 2. Background

1996년 Basel Market Risk Amendment 이후 시장위험 규제는 오랫동안 VaR(Value at Risk)를 중심으로 운영되었다.

그러나 2007~2008년 글로벌 금융위기 동안 많은 금융기관이 규제상 충분한 자본을 보유하고 있었음에도 실제 손실은 VaR 예측 범위를 크게 초과하였다.

이 경험은 VaR 중심 규제체계의 구조적 한계를 드러냈으며, Basel Committee는 시장위험 규제 전반을 재검토하였다.

그 결과 도입된 규제가 **Fundamental Review of the Trading Book(FRTB)** 이다.

---

# 3. Evolution of Market Risk Regulation

```text
1996
Market Risk Amendment
        │
        ▼
VaR-based Regulation
        │
        ▼
2008 Global Financial Crisis
        │
        ▼
Regulatory Review
        │
        ▼
Fundamental Review of the Trading Book
        │
        ▼
FRTB Standardized Approach
FRTB Internal Models Approach
```

FRTB는 기존 체계를 부분 수정한 것이 아니라, 시장위험 규제의 기본 철학을 재설계한 프레임워크이다.

---

# 4. Limitations of Value at Risk

## 4.1 Tail Risk Underestimation

VaR는 특정 신뢰수준(예: 99%)에서의 손실 한계만 제시하며, 그 한계를 초과하는 극단적 손실(Tail Loss)의 규모는 반영하지 않는다.

따라서 금융위기와 같은 극단적 상황에서는 실제 위험을 과소평가할 수 있다.

---

## 4.2 Lack of Risk Factor Transparency

VaR는 포트폴리오 전체의 손실을 하나의 수치로 표현하지만,

* 어떤 Risk Factor가 위험을 발생시켰는지,
* 어느 자산군이 자본을 증가시켰는지,

를 직접 설명하지 못한다.

---

## 4.3 Weak Regulatory Comparability

내부모형 기반 VaR는 금융기관마다 모델, 데이터, 가정이 달라 동일한 포트폴리오라도 서로 다른 자본 결과를 산출할 수 있다.

이는 감독기관의 비교 가능성과 일관성을 저하시켰다.

---

## 4.4 Trading Book Boundary Problems

기존 규제에서는 Trading Book과 Banking Book의 구분 기준이 명확하지 않아 규제 차익(Regulatory Arbitrage)이 발생할 수 있었다.

FRTB는 Trading Book의 정의와 이전(Transfer) 규칙을 보다 엄격하게 정립하였다.

---

## 4.5 Liquidity Risk

VaR는 자산의 유동성 차이를 충분히 고려하지 않았다.

그러나 실제 시장에서는 동일한 손실이라도 유동성이 낮은 자산은 청산에 더 긴 시간이 필요하며, 위험이 크게 증가한다.

FRTB는 위험요인별 유동성 기간(Liquidity Horizon)을 고려하는 방향으로 발전하였다.

---

# 5. Why Sensitivity-Based Method?

FRTB Standardized Approach는 VaR 대신 **Sensitivity-based Method(SBM)** 를 채택하였다.

그 이유는 다음과 같다.

| VaR      | Sensitivity-based Method |
| -------- | ------------------------ |
| 포트폴리오 중심 | 위험요인 중심                  |
| 결과 중심    | 원인 중심                    |
| 설명력 제한   | 높은 설명 가능성                |
| 내부모형 의존  | 표준화된 계산                  |
| 비교 어려움   | 기관 간 비교 용이               |

SBM은 위험이 발생하는 원인을 직접 측정하므로 규제의 투명성과 설명 가능성을 높인다.

---

# 6. Expected Shortfall and FRTB

FRTB는 Internal Models Approach에서 VaR 대신 Expected Shortfall(ES)을 사용한다.

이는 극단적 손실의 평균을 반영하여 Tail Risk를 보다 현실적으로 측정하기 위함이다.

Standardized Approach는 ES를 직접 계산하지 않지만, 위험 민감도 기반 구조를 통해 시장위험을 보다 세분화하여 측정한다.

---

# 7. Impact on Financial Institutions

FRTB 도입으로 금융기관은 다음과 같은 변화를 경험하였다.

| Area                | Impact                   |
| ------------------- | ------------------------ |
| Data Management     | Risk Factor 데이터 품질 향상 요구 |
| Risk Engine         | 민감도 계산 엔진 구축 필요          |
| Capital Calculation | 자본 산출 방식 복잡도 증가          |
| Governance          | 모델 및 데이터 거버넌스 강화         |
| Reporting           | 규제 보고 체계 고도화             |

---

# 8. Architectural Implications

FRTB는 시스템 아키텍처에도 큰 영향을 미쳤다.

```text
Market Data
      │
      ▼
Risk Factor Engine
      │
      ▼
Sensitivity Engine
      │
      ▼
Risk Weight Engine
      │
      ▼
Aggregation Engine
      │
      ▼
Capital Engine
```

기존 VaR 중심의 단일 계산 엔진과 달리, FRTB는 여러 전문 컴포넌트의 협업 구조를 요구한다.

---

# 9. Relationship with Bundle-006

본 분석은 Bundle-006의 핵심 설계 근거를 제공한다.

```text
RL-160
      │
      ▼
KB-261
      │
      ▼
KB-262
      │
      ▼
KB-263
      │
      ▼
AN-261
      │
      ▼
MF-461 ~ MF-463
      │
      ▼
FC-461 ~ FC-464
      │
      ▼
IMP-461
      │
      ▼
ARCH-761
```

Analysis는 이후 Mathematical Foundation과 Formula Catalog가 필요한 이유를 설명하는 연결 계층이다.

---

# 10. Key Insights

FRTB는 단순히 새로운 자본 산식을 도입한 것이 아니라, 시장위험을 바라보는 관점을 변화시켰다.

기존에는 **"얼마나 손실이 발생할 수 있는가?"**를 중심으로 위험을 측정했다면, FRTB는 **"어떤 위험요인이 얼마나 자본에 기여하는가?"**를 중심으로 위험을 분석한다.

이는 시장위험 관리의 초점을 **결과(Result)** 에서 **원인(Driver)** 으로 이동시킨 중요한 변화이다.

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

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)의 Analysis Layer를 구성하며, 이후 Mathematical Foundation과 Formula 설계의 배경을 제공한다.

---

# 12. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-261_MARKET_RISK_STANDARDIZED_APPROACH](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)          |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)                   |
| Knowledge               | [KB-263_RISK_FACTOR_CATEGORIES](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)                     |
| Mathematical Foundation | [MF-461_COVARIANCE_MATRIX](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md) *(Planned)*              |
| Mathematical Foundation | [MF-462_PRINCIPAL_COMPONENT_ANALYSIS](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md) *(Planned)*   |
| Mathematical Foundation | [MF-463_EIGENVALUE_AND_EIGENVECTOR](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-463_EIGENVALUE_AND_EIGENVECTOR.md) *(Planned)*     |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md) *(Planned)*          |
| Formula                 | [FC-462_VEGA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-462_VEGA_CAPITAL_FORMULA.md) *(Planned)*           |
| Formula                 | [FC-463_CURVATURE_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-463_CURVATURE_CAPITAL_FORMULA.md) *(Planned)*      |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md) *(Planned)*            |

---

# 13. Summary

FRTB는 글로벌 금융위기를 계기로 드러난 VaR 기반 시장위험 규제의 한계를 보완하기 위해 도입되었다.

기존 VaR가 포트폴리오 손실의 결과를 중심으로 위험을 측정했다면, FRTB는 Risk Factor와 Sensitivity를 중심으로 위험의 원인을 분석하고 규제자본을 산출한다.

이러한 변화는 시장위험 측정의 투명성, 비교 가능성 및 설명 가능성을 높였으며, 현대 금융기관의 Risk Engine과 데이터 거버넌스 설계에도 큰 영향을 미쳤다.

---

# 14. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
