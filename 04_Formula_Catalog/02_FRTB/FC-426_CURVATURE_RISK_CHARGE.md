# FC-426 — Curvature Risk Charge

---

# Document Information

| Item            | Value                 |
| --------------- | --------------------- |
| Document ID     | FC-426                |
| Document Name   | Curvature Risk Charge |
| Version         | 1.0.0                 |
| Status          | Draft                 |
| Category        | Formula Catalog       |
| Parent Document | FC-423                |
| Created         | 2026-06-26            |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Formula Catalog](../README.md) > [FC-426 — Curvature Risk Charge](FC-426_CURVATURE_RISK_CHARGE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-425](FC-425_VEGA_RISK_CHARGE.md) |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | None |

### Related Documents

- [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md)
- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III FRTB Standardised Approach(SA)의 Sensitivity-Based Method(SBM)에서 사용하는 **Curvature Risk Charge**의 개념, 수학적 정의, 계산 절차 및 구현 관점을 설명한다.

Curvature Risk Charge는 **시장가격의 큰 변동으로 인해 Delta만으로 설명할 수 없는 비선형 위험**을 측정하는 요소이며, 옵션과 같은 비선형 금융상품의 시장위험 자본 계산에 필수적인 구성 요소이다.

---

# 2. Business Purpose

Delta는 가격이 조금 변할 때의 위험을 설명한다.

그러나 실제 시장에서는 다음과 같은 상황이 자주 발생한다.

* 금리가 급격히 상승
* 주가가 급락
* 환율이 급등
* 변동성이 급증

이러한 상황에서는 가격 변화가 더 이상 직선적으로 움직이지 않는다.

Curvature는 이러한 **비선형 가격 변화**를 측정하기 위해 사용된다.

---

# 3. Why Curvature?

Delta는 다음과 같은 선형 근사를 사용한다.

```text
가격 변화

───────────────

직선(Line)
```

하지만 옵션 가격은 실제로

```text
가격 변화

)

)

)

곡선(Curve)
```

과 같이 움직인다.

Delta는 곡선을 직선으로 근사한다.

Curvature는 이 근사 오차를 위험으로 측정한다.

---

# 4. Regulatory Perspective

FRTB는 옵션과 같은 비선형 상품의 위험을 정확하게 반영하기 위해 Curvature Risk Charge를 별도로 계산한다.

계산 흐름은 다음과 같다.

```text
Risk Factor
      │
      ▼
Large Shock
      │
      ▼
Revaluation
      │
      ▼
Curvature Measure
      │
      ▼
Bucket Aggregation
```

Curvature는 단순한 Gamma 계산이 아니라 **규제에서 정의한 충격(Shock)에 대한 재평가 결과**를 기반으로 산출된다.

---

# 5. Mathematical Perspective

Curvature는 금융상품 가치 (V)의 2차 변화율과 관련된다.

[
\Gamma
======

\frac{\partial^2V}{\partial x^2}
]

여기서

* (V): 금융상품 가치
* (x): Risk Factor

Gamma는 Curvature를 이해하는 기초 개념이지만, **FRTB Curvature Risk Charge 자체와 동일한 것은 아니다.**

FRTB에서는 규정된 상향·하향 충격 후의 재평가 결과를 이용하여 Curvature Risk를 계산한다.

---

# 6. Formula Interpretation

Delta는

```text
Risk Factor

↓

Slope
```

를 본다.

Curvature는

```text
Risk Factor

↓

Slope 변화

↓

Curve
```

를 본다.

즉,

**"기울기가 얼마나 빨리 변하는가?"**

를 측정한다.

---

# 7. Business Example

콜옵션을 보유하고 있다고 가정한다.

주가가

```text
100

↓

101
```

로 상승하면

Delta는 비교적 정확한 가격 변화를 예측한다.

그러나

```text
100

↓

130
```

처럼 큰 폭으로 상승하면

Delta만으로는 실제 옵션 가격을 설명하지 못한다.

이 차이가 Curvature Risk이다.

---

# 8. Calculation Flow

```text
Market Data
      │
      ▼
Risk Factor Shock
      │
      ▼
Portfolio Revaluation
      │
      ▼
Delta Approximation
      │
      ▼
Residual Non-linear Effect
      │
      ▼
Curvature Risk
```

---

# 9. Input Contract

| Input              | Description |
| ------------------ | ----------- |
| Risk Factor        | 위험요인        |
| Shock Size         | 규정된 충격 크기   |
| Portfolio Value    | 충격 전 가치     |
| Revalued Portfolio | 충격 후 가치     |
| Delta Sensitivity  | Delta 값     |

---

# 10. Computation Contract

```text
Risk Factor Shock
        │
        ▼
Portfolio Revaluation
        │
        ▼
Delta Estimate
        │
        ▼
Residual Difference
        │
        ▼
Curvature Risk
```

핵심은 **재평가 결과와 Delta 근사값의 차이**를 계산하는 것이다.

---

# 11. Output Contract

| Output             | Description    |
| ------------------ | -------------- |
| Curvature Risk     | 비선형 위험         |
| Weighted Curvature | 위험가중 Curvature |
| Bucket Capital     | 버킷 자본          |

---

# 12. Formula Engine Model

```text
ShockGenerator
        │
        ▼
PortfolioRevaluator
        │
        ▼
DeltaEstimator
        │
        ▼
CurvatureCalculator
        │
        ▼
WeightedCurvature
```

Formula Engine은 Curvature 계산까지 수행하고, Bucket 및 Risk Class 집계는 Risk Engine에서 담당한다.

---

# 13. Implementation Considerations

구현 시 고려사항

* Shock Generator를 독립 모듈로 분리한다.
* Pricing Engine은 재평가를 지원해야 한다.
* Delta 계산과 Curvature 계산을 분리한다.
* Shock 규칙은 Configuration으로 관리한다.
* 동일한 Pricing Model을 재사용하여 계산 일관성을 유지한다.

---

# 14. Performance Considerations

Curvature 계산은 Delta보다 계산 비용이 크다.

최적화 전략

* 재평가 결과 캐싱
* 병렬 Shock 계산
* Pricing Engine 재사용
* 벡터 기반 연산
* 중복 재평가 제거

---

# 15. Relationship with FRKP

| Layer          | Related Document               |
| -------------- | ------------------------------ |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)                         |
| Knowledge      | [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)                         |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)                         |
| Formula        | [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md), [FC-424](FC-424_DELTA_RISK_CHARGE.md), [FC-425](FC-425_VEGA_RISK_CHARGE.md), [FC-426](FC-426_CURVATURE_RISK_CHARGE.md) |
| Implementation | IMP-421                        |
| Architecture   | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)                       |

---

# 16. Knowledge Graph

```text
Risk Factor
      │
      ▼
Delta
      │
      ▼
Large Shock
      │
      ▼
Portfolio Revaluation
      │
      ▼
Curvature
      │
      ▼
Bucket Capital
```

---

# 17. Learning Path

```text
KB-222 FRTB Framework
        │
        ▼
FC-423 Sensitivity-Based Method
        │
        ├── FC-424 Delta Risk Charge
        ├── FC-425 Vega Risk Charge
        └── FC-426 Curvature Risk Charge
                 │
                 ▼
ARCH-721 FRTB Calculation Architecture
```

---

# 18. Summary

Curvature Risk Charge는 FRTB Standardised Approach에서 **비선형 시장위험**을 측정하기 위한 핵심 구성 요소이다.

Delta가 작은 시장 변동에 대한 1차 민감도를 제공하는 반면, Curvature는 큰 시장 충격에서 발생하는 비선형 가격 변화를 반영한다.

FRKP에서는 Curvature Risk Charge를 **Risk Factor Shock → Portfolio Revaluation → Delta Approximation → Residual Non-linear Effect**로 이어지는 계산 계약으로 정의하며, Formula Engine은 재평가와 Curvature 계산을 담당하고 Risk Engine은 Bucket 및 Risk Class 집계를 담당한다.

---

# 19. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
