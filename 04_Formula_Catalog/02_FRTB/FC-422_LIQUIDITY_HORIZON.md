# FC-422 — Liquidity Horizon (LH)

---

# Document Information

| Item            | Value             |
| --------------- | ----------------- |
| Document ID     | FC-422            |
| Document Name   | Liquidity Horizon |
| Version         | 1.0.0             |
| Status          | Draft             |
| Owner           | Project Lead      |
| Category        | Formula Catalog   |
| Parent Document | FC-421            |
| Created         | 2026-06-26        |
| Last Updated    | 2026-06-26        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Formula Catalog](../README.md) > [FC-422 — Liquidity Horizon (LH)](FC-422_LIQUIDITY_HORIZON.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-421](FC-421_EXPECTED_SHORTFALL.md) |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md) |

### Related Documents

- [FC-421](FC-421_EXPECTED_SHORTFALL.md)
- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III FRTB에서 사용하는 **Liquidity Horizon(LH)** 의 개념, 수학적 의미, 계산 방법 및 시스템 구현 관점을 설명한다.

Liquidity Horizon은 Expected Shortfall 계산 결과를 실제 시장의 유동성을 반영하도록 조정하기 위한 핵심 요소이다.

---

# 2. Business Purpose

금융위기 상황에서는 자산을 즉시 매도할 수 없다.

평상시에는 하루 만에 처분 가능한 자산이라도 위기 시에는 수 주 또는 수개월이 걸릴 수 있다.

따라서 동일한 손실이라도 **청산에 걸리는 시간이 길수록 더 큰 위험**으로 평가해야 한다.

Liquidity Horizon은 이러한 현실을 규제자본 계산에 반영하기 위해 도입되었다.

---

# 3. Why Liquidity Horizon?

VaR와 단순 ES는 다음과 같은 가정을 한다.

> 모든 포지션은 동일한 기간 내에 청산할 수 있다.

실제 시장에서는 그렇지 않다.

예를 들어

| Instrument | 현실적인 청산 시간 |
| ---------- | ---------- |
| 국채         | 매우 짧음      |
| 대형주        | 짧음         |
| 회사채        | 중간         |
| 구조화채권      | 김          |
| 장외파생상품     | 매우 김       |

즉,

**상품마다 위험을 제거하는 시간이 서로 다르다.**

---

# 4. Liquidity Horizon Concept

```text
Risk Factor

      │

      ▼

Expected Shortfall

      │

      ▼

Liquidity Horizon Adjustment

      │

      ▼

Adjusted Expected Shortfall
```

Expected Shortfall를 계산한 후 Liquidity Horizon을 적용하여 최종 위험을 산출한다.

---

# 5. Standard Liquidity Horizons

FRTB는 대표적으로 다음 다섯 개의 Liquidity Horizon을 사용한다.

| Liquidity Horizon | Typical Application |
| ----------------: | ------------------- |
|           10 Days | 매우 유동적인 위험요인        |
|           20 Days | 일반적인 위험요인           |
|           40 Days | 중간 수준 유동성           |
|           60 Days | 낮은 유동성              |
|          120 Days | 매우 낮은 유동성           |

각 Risk Factor는 규정에 따라 적절한 Horizon에 배정된다.

---

# 6. Mathematical Interpretation

Liquidity Horizon은 시간에 따른 위험 증가를 반영한다.

FRTB에서는 일반적으로 다음과 같은 시간 스케일링을 사용한다.

[
ES_{LH}
=======

ES_{10}
\times
\sqrt{\frac{LH}{10}}
]

여기서

* (ES_{10}) : 10일 기준 Expected Shortfall
* (LH) : Liquidity Horizon(일)

이는 위험이 시간의 제곱근에 비례하여 증가한다는 가정(√T Rule)을 기반으로 한다.

---

# 7. Example

10일 Expected Shortfall가

```text
100
```

이고

Liquidity Horizon이

```text
40일
```

이라면

[
ES_{40}
=======

100
\times
\sqrt{\frac{40}{10}}
====================

100
\times
2
=

200
]

즉,

동일한 포지션이라도 청산 시간이 길어질수록 위험은 증가한다.

---

# 8. Risk Factor Mapping

```text
Risk Factor
      │
      ├── Interest Rate
      ├── FX
      ├── Equity
      ├── Credit Spread
      ├── Commodity
      └── Volatility
               │
               ▼
      Liquidity Horizon
```

Liquidity Horizon은 **포지션이 아니라 Risk Factor 단위**로 적용된다.

---

# 9. Input Contract

| Input              | Description |
| ------------------ | ----------- |
| Expected Shortfall | 기본 ES       |
| Risk Factor        | 위험요인        |
| Liquidity Horizon  | 적용 기간       |
| Confidence Level   | 신뢰수준        |

---

# 10. Computation Contract

계산 절차

```text
Expected Shortfall
        │
        ▼
Risk Factor Lookup
        │
        ▼
Liquidity Horizon
        │
        ▼
Scaling
        │
        ▼
Adjusted Expected Shortfall
```

Formula Engine은 Liquidity Horizon 계산만 수행한다.

---

# 11. Output Contract

| Output            | Description            |
| ----------------- | ---------------------- |
| Adjusted ES       | 조정된 Expected Shortfall |
| Scaling Factor    | 시간 보정계수                |
| Liquidity Horizon | 적용된 기간                 |

---

# 12. Formula Engine Model

```text
ExpectedShortfall
        │
        ▼
LiquidityHorizonResolver
        │
        ▼
ScalingCalculator
        │
        ▼
AdjustedExpectedShortfall
```

---

# 13. Implementation Considerations

Risk Engine 구현 시 고려사항

* Liquidity Horizon은 설정(Configuration)으로 관리한다.
* Risk Factor와 Liquidity Horizon의 매핑을 분리한다.
* 시간 스케일링 규칙을 독립 모듈로 구현한다.
* Risk Factor 추가 시 Horizon을 쉽게 확장할 수 있도록 설계한다.
* Formula Engine은 계산만 수행하고 규칙은 Configuration에서 관리한다.

---

# 14. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)           |
| Knowledge      | [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)           |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)           |
| Formula        | [FC-421](FC-421_EXPECTED_SHORTFALL.md), [FC-422](FC-422_LIQUIDITY_HORIZON.md)   |
| Implementation | IMP-421          |
| Architecture   | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)         |

---

# 15. Knowledge Graph

```text
Risk Factor
        │
        ▼
Expected Shortfall
        │
        ▼
Liquidity Horizon
        │
        ▼
Scaling
        │
        ▼
Adjusted ES
        │
        ▼
Market Capital
```

---

# 16. Learning Path

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

# 17. Summary

Liquidity Horizon은 FRTB에서 Expected Shortfall를 실제 시장의 유동성을 반영하도록 조정하는 핵심 요소이다.

이는 단순히 "보유 기간"을 의미하는 것이 아니라 **위험요인을 정상적으로 청산하기 위해 필요한 시간**을 모델링하는 개념이다.

FRKP에서는 Liquidity Horizon을 **Expected Shortfall 이후 적용되는 시간 기반 위험 조정(Time-based Risk Adjustment)** 으로 정의하며, Risk Factor별 설정(Configuration)과 Formula Engine의 계산 계약을 분리하는 구조를 채택한다.

---

# 18. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
