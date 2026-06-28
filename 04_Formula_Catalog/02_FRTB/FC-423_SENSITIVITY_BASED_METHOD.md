# FC-423 — Sensitivity-Based Method (SBM)

---

# Document Information

| Item            | Value                    |
| --------------- | ------------------------ |
| Document ID     | FC-423                   |
| Document Name   | Sensitivity-Based Method |
| Version         | 1.0.0                    |
| Status          | Draft                    |
| Owner           | Project Lead             |
| Category        | Formula Catalog          |
| Parent Document | KB-222                   |
| Created         | 2026-06-26               |
| Last Updated    | 2026-06-26               |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Formula Catalog](../README.md) > [FC-423 — Sensitivity-Based Method (SBM)](FC-423_SENSITIVITY_BASED_METHOD.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-422](FC-422_LIQUIDITY_HORIZON.md) |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-424](FC-424_DELTA_RISK_CHARGE.md) |

### Related Documents

- [FC-421](FC-421_EXPECTED_SHORTFALL.md)
- [FC-422](FC-422_LIQUIDITY_HORIZON.md)
- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III FRTB Standardised Approach(SA)의 핵심 계산 체계인 **Sensitivity-Based Method(SBM)** 를 설명한다.

SBM은 금융상품 가격이 시장 위험요인(Risk Factor)에 얼마나 민감하게 반응하는지를 기반으로 시장위험 자본을 계산하는 방법이다.

FRKP에서는 SBM을 **민감도(Sensitivity) → Bucket Aggregation → Capital Requirement**로 이어지는 계산 프레임워크로 정의한다.

---

# 2. Business Purpose

시장위험은 가격 자체보다 **가격이 얼마나 변하는가**가 더 중요하다.

예를 들어,

* 금리가 1bp 상승할 때 채권 가격은 얼마나 변하는가?
* 변동성이 1% 상승할 때 옵션 가격은 얼마나 변하는가?
* 주가가 1% 하락할 때 포트폴리오 손실은 얼마나 되는가?

이러한 반응 정도를 **Sensitivity**라고 한다.

SBM은 이 민감도를 이용하여 자본요구액을 계산한다.

---

# 3. Why Sensitivity?

기존 Standard Method는 위험을 단순 분류하였다.

FRTB는

> **"가격이 실제로 얼마나 움직이는가?"**

를 직접 측정하도록 변경하였다.

즉,

```text
Risk Factor

↓

Sensitivity

↓

Capital
```

로 계산한다.

---

# 4. SBM Framework

```text
Market Data
      │
      ▼
Risk Factor
      │
      ▼
Sensitivity
      │
      ▼
Bucket Aggregation
      │
      ▼
Risk Class Aggregation
      │
      ▼
Capital Requirement
```

---

# 5. Three Sensitivity Types

SBM은 세 가지 민감도를 사용한다.

| Type      | Description |
| --------- | ----------- |
| Delta     | 1차 가격 민감도   |
| Vega      | 변동성 민감도     |
| Curvature | 2차 가격 민감도   |

각 민감도는 독립적으로 계산된 후 통합된다.

---

# 6. Delta Sensitivity

Delta는 Risk Factor가 작은 폭으로 변할 때 금융상품 가격이 얼마나 변하는지를 나타낸다.

수학적으로는

[
\Delta
======

\frac{\partial V}{\partial x}
]

여기서

* (V) : 금융상품 가치
* (x) : Risk Factor

---

# 7. Vega Sensitivity

Vega는 변동성 변화에 대한 민감도이다.

[
Vega
====

\frac{\partial V}
{\partial \sigma}
]

여기서

* (\sigma) : Volatility

---

# 8. Curvature Sensitivity

Curvature는 Delta만으로 설명되지 않는 비선형 효과를 측정한다.

일반적으로

[
Curvature
=========

\frac{\partial^2V}
{\partial x^2}
]

로 표현된다.

옵션과 같이 비선형 상품에서 매우 중요하다.

---

# 9. Bucket Aggregation

동일한 Risk Bucket에 속하는 민감도는 상관관계를 고려하여 집계한다.

```text
Sensitivity

↓

Risk Bucket

↓

Correlation

↓

Bucket Capital
```

---

# 10. Risk Class Aggregation

각 Bucket 결과를 다시 Risk Class 수준으로 집계한다.

예)

```text
Interest Rate

↓

Bucket

↓

Interest Rate Capital
```

동일한 방식이

* FX
* Equity
* Commodity
* Credit Spread

에도 적용된다.

---

# 11. Input Contract

| Input              | Description          |
| ------------------ | -------------------- |
| Risk Factor        | 위험요인                 |
| Sensitivity        | Delta/Vega/Curvature |
| Bucket             | 위험 버킷                |
| Correlation Matrix | 상관계수                 |
| Risk Weight        | 위험가중치                |

---

# 12. Computation Contract

```text
Risk Factor
      │
      ▼
Sensitivity
      │
      ▼
Risk Weight
      │
      ▼
Bucket Aggregation
      │
      ▼
Risk Class Aggregation
      │
      ▼
Capital Requirement
```

---

# 13. Output Contract

| Output             | Description |
| ------------------ | ----------- |
| Bucket Capital     | 버킷별 자본      |
| Risk Class Capital | 위험군 자본      |
| Total SBM Capital  | SBM 자본요구액   |

---

# 14. Formula Engine Model

```text
SensitivityCalculator
        │
        ▼
RiskWeightApplier
        │
        ▼
BucketAggregator
        │
        ▼
RiskClassAggregator
        │
        ▼
SBMCapital
```

---

# 15. Implementation Considerations

Risk Engine 구현 시 고려사항

* Delta, Vega, Curvature를 독립 모듈로 구현한다.
* Correlation Matrix는 설정(Configuration)으로 관리한다.
* Bucket 계산과 Risk Class 계산을 분리한다.
* 병렬 집계를 지원한다.
* 새로운 Risk Class 추가가 가능하도록 확장성을 확보한다.

---

# 16. Relationship with FRKP

| Layer          | Related Document       |
| -------------- | ---------------------- |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)                 |
| Knowledge      | [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md), [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)         |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)                 |
| Formula        | [FC-421](FC-421_EXPECTED_SHORTFALL.md), [FC-422](FC-422_LIQUIDITY_HORIZON.md), [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md) |
| Implementation | IMP-421                |
| Architecture   | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)               |

---

# 17. Knowledge Graph

```text
Risk Factor
      │
      ▼
Sensitivity
      │
      ├── Delta
      ├── Vega
      └── Curvature
              │
              ▼
Bucket
              │
              ▼
Risk Class
              │
              ▼
SBM Capital
```

---

# 18. Learning Path

```text
KB-222 FRTB Framework
        │
        ▼
FC-421 Expected Shortfall
        │
        ▼
FC-422 Liquidity Horizon
        │
        ▼
FC-423 Sensitivity-Based Method
        │
        ▼
IMP-421 Expected Shortfall Implementation
        │
        ▼
ARCH-721 FRTB Calculation Architecture
```

---

# 19. Summary

Sensitivity-Based Method는 FRTB Standardised Approach의 핵심 계산 체계이다.

시장가격 자체가 아니라 **Risk Factor에 대한 민감도**를 기반으로 위험을 계산하며, Delta, Vega, Curvature를 각각 산출한 후 Bucket 및 Risk Class 수준으로 집계하여 최종 시장위험 자본요구액을 산출한다.

FRKP에서는 SBM을 **민감도 계산 계약(Sensitivity Contract)** 과 **집계 계약(Aggregation Contract)** 을 결합한 Formula Framework로 정의하며, Formula Engine은 개별 민감도 계산을 담당하고 Risk Engine은 상관관계를 적용한 집계를 수행하도록 역할을 분리한다.

---

# 20. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
