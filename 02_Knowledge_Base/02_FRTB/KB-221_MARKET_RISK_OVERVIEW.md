# KB-221 — Market Risk Overview

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Knowledge Base](../README.md) > [KB-221 — Market Risk Overview](KB-221_MARKET_RISK_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | [KB-222](KB-222_FRTB_FRAMEWORK.md) |

### Related Documents

- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-222](KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
- [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)
- [FC-422](../../04_Formula_Catalog/02_FRTB/FC-422_LIQUIDITY_HORIZON.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item            | Value                |
| --------------- | -------------------- |
| Document ID     | KB-221               |
| Document Name   | Market Risk Overview |
| Version         | 1.0.0                |
| Status          | Draft                |
| Owner           | Project Lead         |
| Category        | Knowledge Base       |
| Parent Document | KB-201               |
| Created         | 2026-06-26           |
| Last Updated    | 2026-06-26           |

---

# 1. Purpose

본 문서는 금융기관이 직면하는 **시장위험(Market Risk)** 의 개념과 구조를 설명하는 Knowledge Base 문서이다.

시장위험의 정의, 발생 원인, 주요 위험요인(Risk Factor), 측정 방법 및 Basel III/FRTB와의 관계를 설명하며, 이후 Formula Catalog와 Architecture Guide의 기반 지식을 제공한다.

---

# 2. What is Market Risk?

시장위험(Market Risk)은 **시장 가격(Market Price)의 변동으로 인해 금융기관 또는 투자자의 자산 가치가 변동하여 손실이 발생할 가능성**을 의미한다.

시장위험은 투자 의사결정과 관계없이 시장환경이 변하면 발생하는 **외생적(External) 위험**이다.

시장위험 관리의 목적은 위험을 제거하는 것이 아니라 **측정(Measure), 모니터링(Monitor), 통제(Control)** 하는 것이다.

---

# 3. Business Perspective

금융기관은 다음과 같은 자산을 보유한다.

* 국채
* 회사채
* 주식
* 외환
* 파생상품
* ETF
* Repo
* IRS
* CDS

이들 자산은 시장가격이 지속적으로 변한다.

가격 변동은 손익(P&L)에 직접 영향을 주며, 시장위험 관리는 이러한 손익 변동을 정량적으로 관리하는 활동이다.

---

# 4. Market Risk Drivers

시장위험은 다양한 위험요인의 변동으로 발생한다.

| Risk Factor      | Description |
| ---------------- | ----------- |
| Interest Rate    | 금리          |
| Equity Price     | 주가          |
| Foreign Exchange | 환율          |
| Commodity Price  | 상품가격        |
| Credit Spread    | 신용스프레드      |
| Volatility       | 변동성         |
| Correlation      | 상관관계        |

이러한 위험요인을 **Risk Factor**라고 한다.

---

# 5. Risk Factor Model

```text
Market
      │
      ▼
Risk Factors
      │
      ├── Interest Rate
      ├── FX Rate
      ├── Equity
      ├── Credit Spread
      ├── Commodity
      └── Volatility
              │
              ▼
Financial Instruments
              │
              ▼
Profit & Loss
```

시장은 개별 자산을 직접 변화시키는 것이 아니라 **Risk Factor**를 변화시키며, Risk Factor가 금융상품의 가치에 영향을 준다.

---

# 6. Market Risk Process

시장위험 관리는 일반적으로 다음 순서로 수행된다.

```text
Market Data
      │
      ▼
Risk Factor Mapping
      │
      ▼
Pricing
      │
      ▼
Sensitivity
      │
      ▼
Risk Measure
      │
      ▼
Capital Requirement
```

---

# 7. Market Risk Measurement

시장위험을 측정하는 대표적인 방법은 다음과 같다.

| Method                  | Purpose             |
| ----------------------- | ------------------- |
| Sensitivity             | 위험요인 변화에 대한 민감도     |
| Value at Risk (VaR)     | 일정 신뢰수준에서의 최대 예상 손실 |
| Expected Shortfall (ES) | 극단적 손실 평균           |
| Stress Test             | 극단적 시나리오 분석         |
| Scenario Analysis       | 가정된 시장 변화 분석        |

Basel III(FRTB)에서는 **Expected Shortfall**를 핵심 측정 지표로 사용한다.

---

# 8. Trading Book vs Banking Book

Basel III는 자산을 다음 두 영역으로 구분한다.

| Trading Book         | Banking Book     |
| -------------------- | ---------------- |
| 매매 목적 보유             | 만기 보유 및 일반 은행업무  |
| 시가평가(Mark-to-Market) | 회계 기준 평가         |
| FRTB 적용              | IRRBB 등 별도 규제 적용 |

시장위험은 주로 **Trading Book**을 대상으로 관리한다.

---

# 9. Relationship with Basel III

```text
Basel III
      │
      ▼
Market Risk
      │
      ▼
FRTB
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

시장위험은 Basel III의 Pillar 1에서 규제자본 산정의 중요한 구성 요소이며, 계산된 Market RWA는 Credit RWA 및 Operational RWA와 합산되어 Total RWA를 구성한다.

---

# 10. Relationship with FRKP

| Topic              | Related Document |
| ------------------ | ---------------- |
| Basel III          | RL-110           |
| FRTB               | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)           |
| Financial Risk     | [KB-201](../01_Basel_III/KB-201_FINANCIAL_RISK_OVERVIEW.md)           |
| FRTB Framework     | [KB-222](KB-222_FRTB_FRAMEWORK.md)           |
| Why VaR Failed     | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)           |
| Expected Shortfall | [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)           |
| Liquidity Horizon  | [FC-422](../../04_Formula_Catalog/02_FRTB/FC-422_LIQUIDITY_HORIZON.md)           |
| FRTB Architecture  | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)         |

---

# 11. Practical Example

예를 들어, 한 금융기관이 국채와 금리스왑(IRS)을 보유하고 있다고 가정한다.

* 기준금리가 1% 상승하면 국채 가격은 하락할 수 있다.
* 동일한 금리 변화는 IRS의 현재가치에도 영향을 미친다.
* 변동성 확대는 옵션의 가치에도 영향을 준다.

이처럼 **하나의 Risk Factor 변화가 여러 금융상품의 가치에 동시에 영향을 주며**, 이를 통합적으로 측정하는 것이 시장위험 관리의 핵심이다.

---

# 12. Knowledge Graph

```text
Financial Risk
        │
        ▼
Market Risk
        │
        ├── Risk Factor
        ├── Sensitivity
        ├── VaR
        ├── Expected Shortfall
        ├── Liquidity Horizon
        ├── Trading Book
        └── Market RWA
```

---

# 13. Learning Path

권장 학습 순서는 다음과 같다.

```text
KB-201 Financial Risk Overview
        │
        ▼
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
ARCH-721 FRTB Calculation Architecture
```

---

# 14. Summary

시장위험은 금융기관이 직면하는 핵심 리스크 중 하나이며, 시장 가격을 구성하는 다양한 Risk Factor의 변동으로 발생한다.

Basel III의 FRTB는 이러한 시장위험을 보다 현실적으로 측정하기 위해 Expected Shortfall, Liquidity Horizon 및 Sensitivity-Based Method를 도입하였다.

FRKP에서는 시장위험을 단순한 규제 개념이 아니라 **Risk Factor → Pricing → Sensitivity → Risk Measure → Capital Requirement**로 이어지는 하나의 통합 프로세스로 정의하며, Formula Engine과 Risk Engine Architecture의 핵심 입력으로 활용한다.

---

# 15. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
