# FC-421 — Expected Shortfall (ES)

---

# Document Information

| Item            | Value              |
| --------------- | ------------------ |
| Document ID     | FC-421             |
| Document Name   | Expected Shortfall |
| Version         | 1.0.0              |
| Status          | Draft              |
| Owner           | Project Lead       |
| Category        | Formula Catalog    |
| Parent Document | KB-222             |
| Created         | 2026-06-26         |
| Last Updated    | 2026-06-26         |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Formula Catalog](../README.md) > [FC-421 — Expected Shortfall (ES)](FC-421_EXPECTED_SHORTFALL.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-422](FC-422_LIQUIDITY_HORIZON.md) |

### Related Documents

- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
- [FC-422](FC-422_LIQUIDITY_HORIZON.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III FRTB에서 사용하는 **Expected Shortfall(ES)** 의 정의, 수학적 의미, 계산 방법, 데이터 모델 및 시스템 구현 관점을 설명한다.

Expected Shortfall는 FRTB 시장위험 규제의 핵심 위험지표이며, 기존 Value at Risk(VaR)를 대체하는 대표적인 Tail Risk 측정 방법이다.

---

# 2. Business Purpose

금융기관이 실제로 알고 싶은 것은

> **"최악의 시장 상황에서 평균적으로 얼마나 손실이 발생하는가?"**

이다.

VaR는 손실의 경계값만 알려주지만,

Expected Shortfall는 **경계값을 초과하는 손실의 평균 규모**를 제공한다.

따라서 금융위기와 같은 극단적인 시장 상황을 더 현실적으로 반영할 수 있다.

---

# 3. Regulatory Perspective

Basel III FRTB는 시장위험 규제에서 VaR 대신 Expected Shortfall를 사용한다.

주요 이유는 다음과 같다.

* Tail Risk 반영
* 극단적 손실의 평균 제공
* 보다 일관된 위험 측정
* 포트폴리오 분산효과를 합리적으로 반영
* 위험지표의 수학적 일관성(Coherence)

---

# 4. Mathematical Definition

확률수준 (\alpha)에서 Expected Shortfall는 다음과 같이 정의된다.

[
ES_{\alpha}
===========

E[L \mid L > VaR_{\alpha}]
]

여기서

* (L) : 손실(Loss)
* (VaR_{\alpha}) : 신뢰수준 (\alpha)의 Value at Risk
* (E[\cdot]) : 기대값(Expected Value)

즉,

> **VaR를 초과하는 손실들의 평균**

이다.

---

# 5. Formula Interpretation

```text
Loss Distribution

                 Tail

                   │

                   ▼

──────────────┬─────────────────────►

             VaR

             ▲

             ES는

             Tail 전체 평균
```

VaR는 하나의 **점(Point)** 을 계산한다.

Expected Shortfall는 하나의 **영역(Area)** 을 계산한다.

---

# 6. Variables

| Variable | Description        |
| -------- | ------------------ |
| L        | Loss               |
| α        | Confidence Level   |
| VaR      | Value at Risk      |
| ES       | Expected Shortfall |
| N        | Scenario Count     |

---

# 7. Example

100개의 시나리오를 생성했다고 가정한다.

99% 신뢰수준이면

최악의 1% 시나리오를 선택한다.

예를 들어

```text
Loss

100

120

130

150

300
```

VaR

```text
100
```

Expected Shortfall

```text
(100+120+130+150+300)

/5

=

160
```

즉

VaR는 100을 반환하지만,

Expected Shortfall는 160을 반환한다.

---

# 8. Calculation Methods

Expected Shortfall는 다양한 방법으로 계산할 수 있다.

| Method                 | Description |
| ---------------------- | ----------- |
| Historical Simulation  | 과거 데이터 기반   |
| Monte Carlo Simulation | 확률 시뮬레이션    |
| Parametric Method      | 분포 가정 기반    |

FRKP Formula Engine은 계산 방법과 관계없이 동일한 ES 계약(Contract)을 사용한다.

---

# 9. Algorithm

일반적인 계산 순서는 다음과 같다.

```text
Scenario Generation
        │
        ▼
Profit & Loss
        │
        ▼
Sorting
        │
        ▼
VaR Position
        │
        ▼
Tail Selection
        │
        ▼
Average Tail Loss
        │
        ▼
Expected Shortfall
```

---

# 10. Input Data Model

| Field             | Description |
| ----------------- | ----------- |
| Scenario P&L      | 시나리오별 손익    |
| Confidence Level  | 신뢰수준        |
| Liquidity Horizon | 청산기간        |
| Risk Factor       | 위험요인        |

---

# 11. Output Data Model

| Field              | Description |
| ------------------ | ----------- |
| Expected Shortfall |             |
| Tail Count         |             |
| Tail Average       |             |
| Confidence Level   |             |

---

# 12. Formula Engine Model

```text
ScenarioSet
      │
      ▼
LossDistribution
      │
      ▼
TailSelector
      │
      ▼
TailAggregator
      │
      ▼
ExpectedShortfall
```

Formula Engine은 ES 계산만 수행하며, 자본 계산은 수행하지 않는다.

---

# 13. Relationship with Liquidity Horizon

FRTB에서는 Risk Factor마다 Liquidity Horizon을 적용한다.

```text
Expected Shortfall

+

Liquidity Horizon

↓

Adjusted Expected Shortfall
```

즉,

ES는 Liquidity Horizon과 결합되어 최종 시장위험 자본 계산에 사용된다.

---

# 14. Implementation Considerations

Risk Engine 구현 시 고려사항

* Tail Selection은 안정적으로 정렬되어야 한다.
* 대용량 Scenario 계산을 지원해야 한다.
* 병렬 계산이 가능해야 한다.
* Liquidity Horizon을 Risk Factor 단위로 적용해야 한다.
* 계산 방식(Historical, Monte Carlo 등)을 Strategy 패턴으로 분리한다.

---

# 15. Relationship with FRKP

| Layer          | Document       |
| -------------- | -------------- |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)         |
| Knowledge      | [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md), [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md) |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)         |
| Formula        | [FC-421](FC-421_EXPECTED_SHORTFALL.md)         |
| Implementation | IMP-421        |
| Architecture   | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)       |

---

# 16. Knowledge Graph

```text
Market Risk
      │
      ▼
Risk Factor
      │
      ▼
Scenario
      │
      ▼
Loss Distribution
      │
      ▼
Value at Risk
      │
      ▼
Expected Shortfall
      │
      ▼
Liquidity Horizon
      │
      ▼
Market Capital
```

---

# 17. Learning Path

```text
AN-221 Why VaR Failed
        │
        ▼
KB-222 FRTB Framework
        │
        ▼
FC-421 Expected Shortfall
        │
        ▼
FC-422 Liquidity Horizon
        │
        ▼
IMP-421 Expected Shortfall Implementation
        │
        ▼
ARCH-721 FRTB Calculation Architecture
```

---

# 18. Summary

Expected Shortfall는 Basel III FRTB에서 사용하는 핵심 시장위험 측정 지표이다.

VaR가 손실의 경계값을 제공하는 반면, Expected Shortfall는 그 경계값을 초과하는 손실의 평균을 계산하여 Tail Risk를 보다 현실적으로 반영한다.

FRKP에서는 Expected Shortfall를 단순한 수식이 아니라 **Scenario Generation → Loss Distribution → Tail Selection → Tail Aggregation**으로 이어지는 Formula Engine의 핵심 계산 계약(Contract)으로 정의한다.

이 결과는 Liquidity Horizon과 결합되어 Market Capital Requirement 및 Market RWA 계산의 기초가 된다.

---

# 19. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
