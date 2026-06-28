# KB-222 — FRTB Framework

---

# Document Information

| Item            | Value          |
| --------------- | -------------- |
| Document ID     | KB-222         |
| Document Name   | FRTB Framework |
| Version         | 1.0.0          |
| Status          | Draft          |
| Owner           | Project Lead   |
| Category        | Knowledge Base |
| Parent Document | RL-120         |
| Created         | 2026-06-26     |
| Last Updated    | 2026-06-26     |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Knowledge Base](../README.md) > [KB-222 — FRTB Framework](KB-222_FRTB_FRAMEWORK.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [KB-221](KB-221_MARKET_RISK_OVERVIEW.md) |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](KB-221_MARKET_RISK_OVERVIEW.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
- [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)
- [FC-422](../../04_Formula_Catalog/02_FRTB/FC-422_LIQUIDITY_HORIZON.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III 시장위험 규제인 **FRTB(Fundamental Review of the Trading Book)** 의 전체 구조를 설명한다.

FRTB를 구성하는 Standardised Approach(SA), Internal Models Approach(IMA), Risk Factor, Liquidity Horizon, Modellability, Capital Calculation의 관계를 이해하는 것을 목적으로 한다.

---

# 2. Why FRTB?

Basel II.5에서는 대부분의 시장위험을 VaR(Value at Risk) 기반으로 측정하였다.

그러나 금융위기 이후 다음과 같은 문제가 발견되었다.

* Tail Risk 과소평가
* Liquidity 미반영
* Risk Factor 관리 부족
* Trading Book 경계 불명확
* Internal Model 품질 차이

FRTB는 이러한 문제를 해결하기 위해 설계되었다.

---

# 3. Overall Architecture

```text
Basel III
      │
      ▼
Market Risk
      │
      ▼
FRTB
      │
      ├───────────────┐
      ▼               ▼
Standardised      Internal Models
Approach (SA)     Approach (IMA)
```

FRTB는 두 개의 계산 체계를 제공한다.

* Standardised Approach
* Internal Models Approach

---

# 4. Standardised Approach (SA)

SA는 감독기관이 정의한 공통 계산 방법이다.

구성 요소는 다음과 같다.

```text
Sensitivity-Based Method (SBM)

+

Default Risk Charge (DRC)

+

Residual Risk Add-On (RRAO)
```

### 목적

* 모든 금융기관 적용 가능
* 모델 승인 불필요
* 최소 규제자본 산출

---

# 5. Internal Models Approach (IMA)

IMA는 감독기관의 승인을 받은 금융기관이 사용하는 내부모형이다.

핵심 요소

* Expected Shortfall
* Liquidity Horizon
* Modellability
* Backtesting
* P&L Attribution

IMA는 SA보다 위험을 정교하게 측정하지만 높은 검증 수준을 요구한다.

---

# 6. Risk Factor Framework

FRTB는 금융상품이 아니라 **Risk Factor** 중심으로 위험을 측정한다.

```text
Market Data
      │
      ▼
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
Sensitivity
```

Risk Factor 변화가 금융상품 가치 변동의 원인이다.

---

# 7. Sensitivity-Based Method

SA에서는 먼저 민감도를 계산한다.

대표적인 민감도

| Sensitivity | Description |
| ----------- | ----------- |
| Delta       | 1차 가격 민감도   |
| Vega        | 변동성 민감도     |
| Curvature   | 2차 가격 민감도   |

민감도는 이후 Bucket Aggregation 과정을 거쳐 자본요구액으로 변환된다.

---

# 8. Liquidity Horizon

FRTB는 위험요인마다 서로 다른 청산기간을 적용한다.

대표적인 기간

| Risk Factor | Horizon |
| ----------- | ------- |
| 매우 유동적      | 10일     |
| 일반          | 20일     |
| 중간          | 40일     |
| 낮음          | 60일     |
| 매우 낮음       | 120일    |

Liquidity Horizon은 Expected Shortfall 계산에 직접 반영된다.

---

# 9. Modellability

모든 Risk Factor가 내부모형으로 계산 가능한 것은 아니다.

FRTB는 Risk Factor Eligibility Test(RFET)를 통해

* Modellable Risk Factor (MRF)
* Non-Modellable Risk Factor (NMRF)

를 구분한다.

NMRF는 별도의 자본요구액이 추가된다.

---

# 10. Model Validation

IMA를 사용하기 위해서는 다음 검증을 통과해야 한다.

* Backtesting
* P&L Attribution Test
* RFET
* Supervisory Approval

검증 실패 시 SA를 적용해야 한다.

---

# 11. Capital Calculation Flow

```text
Trading Book
      │
      ▼
Market Data
      │
      ▼
Risk Factor Mapping
      │
      ▼
Sensitivity
      │
      ▼
Expected Shortfall
      │
      ▼
Market Capital
      │
      ▼
Market RWA
```

최종 Market RWA는 Credit RWA 및 Operational RWA와 합산되어 Total RWA를 구성한다.

---

# 12. Relationship with FRKP

| FRKP Layer     | Related Document       |
| -------------- | ---------------------- |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)                 |
| Knowledge      | [KB-221](KB-221_MARKET_RISK_OVERVIEW.md), [KB-222](KB-222_FRTB_FRAMEWORK.md)         |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)                 |
| Formula        | [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md), [FC-422](../../04_Formula_Catalog/02_FRTB/FC-422_LIQUIDITY_HORIZON.md), [FC-423](../../04_Formula_Catalog/02_FRTB/FC-423_SENSITIVITY_BASED_METHOD.md) |
| Implementation | IMP-421                |
| Architecture   | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)               |

---

# 13. Knowledge Graph

```text
FRTB
 │
 ├── Trading Book
 │
 ├── Standardised Approach
 │      │
 │      ├── Delta
 │      ├── Vega
 │      ├── Curvature
 │      ├── DRC
 │      └── RRAO
 │
 └── Internal Models
        │
        ├── Expected Shortfall
        ├── Liquidity Horizon
        ├── RFET
        ├── Backtesting
        └── P&L Attribution
```

---

# 14. Learning Path

```text
RL-120 FRTB Overview
        │
        ▼
KB-221 Market Risk Overview
        │
        ▼
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
FC-423 Sensitivity-Based Method
        │
        ▼
ARCH-721 FRTB Calculation Architecture
```

---

# 15. Summary

FRTB는 Basel III의 시장위험 규제 프레임워크이며, 기존 VaR 기반 접근을 Expected Shortfall 기반 접근으로 전환하였다.

또한 Risk Factor 중심의 위험 측정, Liquidity Horizon, Modellability, Sensitivity-Based Method를 도입하여 시장위험을 보다 현실적으로 반영한다.

FRKP에서는 FRTB를 단순한 규제가 아니라 **Risk Factor → Sensitivity → Expected Shortfall → Capital Requirement → Market RWA**로 이어지는 통합 위험 측정 프레임워크로 정의한다.

---

# 16. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
