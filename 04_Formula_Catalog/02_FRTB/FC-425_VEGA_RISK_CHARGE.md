# FC-425 — Vega Risk Charge

---

# Document Information

| Item            | Value            |
| --------------- | ---------------- |
| Document ID     | FC-425           |
| Document Name   | Vega Risk Charge |
| Version         | 1.0.0            |
| Status          | Draft            |
| Category        | Formula Catalog  |
| Parent Document | FC-423           |
| Created         | 2026-06-26       |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Formula Catalog](../README.md) > [FC-425 — Vega Risk Charge](FC-425_VEGA_RISK_CHARGE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-424](FC-424_DELTA_RISK_CHARGE.md) |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-426](FC-426_CURVATURE_RISK_CHARGE.md) |

### Related Documents

- [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md)
- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III FRTB Standardised Approach(SA)의 Sensitivity-Based Method(SBM)에서 사용하는 **Vega Risk Charge**의 개념, 수학적 정의, 계산 절차 및 구현 관점을 설명한다.

Vega Risk Charge는 **시장 변동성(Volatility)의 변화가 금융상품 가치에 미치는 영향**을 측정하는 위험 요소이며, 옵션과 같은 비선형 금융상품의 시장위험 자본 계산에서 중요한 역할을 한다.

---

# 2. Business Purpose

시장위험은 기초자산 가격만 변해서 발생하는 것이 아니다.

옵션과 같은 파생상품은

* 가격
* 변동성
* 시간
* 금리

등 다양한 변수에 의해 가치가 변한다.

특히 시장의 불확실성이 커질수록 변동성이 증가하며, 옵션의 가치는 크게 변할 수 있다.

Vega는 이러한 **변동성 변화에 대한 민감도**를 측정한다.

---

# 3. Regulatory Perspective

FRTB는 Delta만으로 옵션의 위험을 충분히 설명할 수 없다고 본다.

따라서 옵션 및 변동성에 민감한 금융상품에 대해서는 Vega Risk Charge를 별도로 계산한다.

계산 흐름은 다음과 같다.

```text
Risk Factor
      │
      ▼
Volatility
      │
      ▼
Vega Sensitivity
      │
      ▼
Risk Weight
      │
      ▼
Bucket Aggregation
```

---

# 4. Mathematical Definition

Vega는 금융상품 가치 (V)를 변동성 (\sigma)에 대해 편미분한 값으로 정의된다.

[
Vega=\frac{\partial V}{\partial \sigma}
]

여기서

* (V): 금융상품 가치
* (\sigma): 내재변동성(Implied Volatility)

Vega는 변동성이 작은 폭으로 변화할 때 금융상품 가치가 얼마나 변하는지를 나타낸다.

---

# 5. Formula Interpretation

Delta가 **가격 변화의 기울기**라면,

Vega는 **변동성 변화의 기울기**이다.

일반적으로

* 변동성 증가 → 옵션 가치 증가
* 변동성 감소 → 옵션 가치 감소

의 관계를 가진다.

단, 옵션 유형(Call/Put), 만기, 행사가 등에 따라 민감도는 달라질 수 있다.

---

# 6. Business Example

콜옵션의 Vega가

```text
850 KRW / 1% Volatility
```

라고 가정한다.

내재변동성이

```text
20% → 23%
```

로 상승하면

예상 가치 변화는

```text
850 × 3

=

2,550 KRW
```

이다.

이는 다른 조건이 동일하다는 가정하에서의 1차 근사값이다.

---

# 7. Calculation Flow

```text
Market Data
      │
      ▼
Volatility Surface
      │
      ▼
Pricing Model
      │
      ▼
Vega Calculation
      │
      ▼
Risk Weight
      │
      ▼
Weighted Vega
```

---

# 8. Risk Weight Application

계산된 Vega는 규제에서 정의한 Risk Weight와 결합된다.

일반적인 계산 흐름은 다음과 같다.

[
WV = RW \times Vega
]

여기서

* (WV): Weighted Vega
* (RW): Risk Weight
* (Vega): Vega Sensitivity

Weighted Vega는 Bucket Aggregation의 입력값으로 사용된다.

---

# 9. Bucket Aggregation

동일 Bucket에 속하는 Weighted Vega는 상관관계를 고려하여 집계된다.

```text
Weighted Vega
        │
        ▼
Bucket
        │
        ▼
Correlation
        │
        ▼
Bucket Capital
```

---

# 10. Input Contract

| Input              | Description |
| ------------------ | ----------- |
| Risk Factor        | 위험요인        |
| Volatility Surface | 변동성 곡면      |
| Vega Sensitivity   | Vega 값      |
| Risk Weight        | 위험가중치       |
| Bucket             | 위험 버킷       |

---

# 11. Computation Contract

```text
Volatility
      │
      ▼
Vega Calculation
      │
      ▼
Risk Weight
      │
      ▼
Weighted Vega
      │
      ▼
Bucket Aggregation
```

---

# 12. Output Contract

| Output             | Description |
| ------------------ | ----------- |
| Weighted Vega      | 위험가중 Vega   |
| Bucket Capital     | 버킷별 자본      |
| Risk Class Capital | 위험군 자본      |

---

# 13. Formula Engine Model

```text
VolatilitySurfaceProvider
        │
        ▼
VegaCalculator
        │
        ▼
RiskWeightApplier
        │
        ▼
WeightedVega
```

Formula Engine은 Vega 계산과 Risk Weight 적용까지 담당하며, Bucket 및 Risk Class 집계는 Risk Engine에서 수행한다.

---

# 14. Implementation Considerations

구현 시 고려사항

* Volatility Surface를 독립 모델로 관리한다.
* Pricing Model과 Vega 계산을 분리한다.
* Risk Weight는 Configuration으로 관리한다.
* Vega 계산은 Strategy Pattern으로 확장 가능하게 설계한다.
* Surface Interpolation(보간) 정책을 분리하여 구현한다.

---

# 15. Performance Considerations

성능 최적화 포인트

* Volatility Surface 캐싱
* 병렬 Vega 계산
* Surface 보간 최적화
* 동일 Surface 재사용
* 벡터 기반 민감도 계산

---

# 16. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)           |
| Knowledge      | [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)           |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)           |
| Formula        | [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md), [FC-425](FC-425_VEGA_RISK_CHARGE.md)   |
| Implementation | IMP-421          |
| Architecture   | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)         |

---

# 17. Knowledge Graph

```text
Volatility
      │
      ▼
Vega
      │
      ▼
Risk Weight
      │
      ▼
Weighted Vega
      │
      ▼
Bucket Capital
      │
      ▼
Risk Class Capital
```

---

# 18. Learning Path

```text
KB-222 FRTB Framework
        │
        ▼
FC-423 Sensitivity-Based Method
        │
        ▼
FC-424 Delta Risk Charge
        │
        ▼
FC-425 Vega Risk Charge
        │
        ▼
FC-426 Curvature Risk Charge
        │
        ▼
ARCH-721 FRTB Calculation Architecture
```

---

# 19. Summary

Vega Risk Charge는 FRTB Standardised Approach에서 **시장 변동성 변화에 따른 위험**을 측정하는 핵심 구성 요소이다.

Delta가 기초자산 가격 변화에 대한 민감도를 측정하는 반면, Vega는 내재변동성 변화에 대한 민감도를 측정하며, 특히 옵션과 같은 비선형 금융상품에서 중요한 의미를 가진다.

FRKP에서는 Vega Risk Charge를 **Volatility Surface → Vega → Weighted Vega → Bucket Aggregation**으로 이어지는 독립적인 계산 계약으로 정의하며, Formula Engine은 Vega 계산을 담당하고 Risk Engine은 집계와 자본 산정을 담당하도록 역할을 분리한다.

---

# 20. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
