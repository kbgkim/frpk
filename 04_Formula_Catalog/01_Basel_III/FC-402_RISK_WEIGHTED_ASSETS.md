# FC-402 — Risk Weighted Assets (RWA)

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) > [Formula Catalog](../README.md) > [FC-402 — Risk Weighted Assets (RWA)](FC-402_RISK_WEIGHTED_ASSETS.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-401](FC-401_CAPITAL_ADEQUACY_RATIO.md) |
| ⬆ Parent Bundle | [BUNDLE-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-001](../../01_Reference_Library/01_Basel_III/RL-001_BASEL_III_OVERVIEW.md)
- [KB-201](../../02_Knowledge_Base/01_Basel_III/KB-201_FINANCIAL_RISK_OVERVIEW.md)
- [KB-301](../../02_Knowledge_Base/01_Basel_III/KB-301_BASEL_III_FRAMEWORK.md)
- [FC-401](FC-401_CAPITAL_ADEQUACY_RATIO.md)
- [ARCH-701](../../07_Architecture/01_Basel_III/ARCH-701_CAPITAL_CALCULATION_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item          | Value                |
| ------------- | -------------------- |
| Document ID   | FC-402               |
| Document Name | Risk Weighted Assets |
| Version       | 1.0.0                |
| Status        | Draft                |
| Owner         | Project Lead         |
| Category      | Formula Catalog      |
| Created       | 2026-06-26           |
| Last Updated  | 2026-06-26           |

---

# 1. Purpose

본 문서는 Basel III에서 사용하는 Risk Weighted Assets(RWA)의 정의, 계산 구조, 구성 요소 및 시스템 구현 관점을 설명한다.

RWA는 금융기관의 모든 위험을 하나의 공통 척도(Risk Unit)로 환산하는 핵심 개념이며, Capital Adequacy Ratio 계산의 분모가 된다.

---

# 2. Business Purpose

모든 자산이 동일한 위험을 갖는 것은 아니다.

예를 들어,

* 국채
* 주택담보대출
* 일반 기업대출
* 파생상품

은 동일한 금액이라도 위험 수준이 서로 다르다.

Basel III는 각 자산의 위험도를 반영하여 위험가중치를 적용하고 이를 합산하여 RWA를 계산한다.

즉,

> **RWA는 "장부금액(Book Value)"이 아니라 "위험을 반영한 자산 규모"이다.**

---

# 3. Concept

```text
Exposure
      │
      ▼
Risk Weight
      │
      ▼
Risk Weighted Asset
```

모든 익스포저(Exposure)는 위험가중치(Risk Weight)를 적용받아 RWA로 변환된다.

---

# 4. Basel III Formula

전체 RWA는 다음과 같이 계산한다.

```text
Total RWA

=

Credit RWA

+

Market RWA

+

Operational RWA
```

보다 일반적으로는 다음과 같이 표현할 수 있다.

[
\text{RWA}_{Total}
==================

\text{RWA}*{Credit}
+
\text{RWA}*{Market}
+
\text{RWA}_{Operational}
]

필요한 경우 규제에 따라 다음 항목이 추가될 수 있다.

* CVA Risk
* Counterparty Credit Risk
* 기타 규제 항목

---

# 5. Credit Risk RWA

신용위험 RWA는 다음 요소로 계산된다.

```text
Exposure

×

Risk Weight

=

Credit RWA
```

예)

| Exposure | Risk Weight | Credit RWA |
| -------- | ----------: | ---------: |
| 100      |          0% |          0 |
| 100      |         20% |         20 |
| 100      |         50% |         50 |
| 100      |        100% |        100 |

---

# 6. Market Risk RWA

시장위험은 Basel III의 FRTB 체계에 따라 계산된다.

일반적인 흐름은 다음과 같다.

```text
Trading Positions

↓

Sensitivity

↓

Expected Shortfall

↓

Market Capital

↓

Market RWA
```

FRKP에서는 별도의 FRTB Formula Catalog에서 상세히 다룬다.

---

# 7. Operational Risk RWA

운영위험은 Basel III Standardised Approach(SA)에 따라 계산된다.

일반적인 흐름은

```text
Business Indicator

↓

Internal Loss

↓

Operational Capital

↓

Operational RWA
```

이다.

---

# 8. Complete RWA Flow

```text
Assets
        │
        ▼
Credit Exposure
Market Position
Operational Indicator
        │
        ▼
Risk Measurement
        │
        ▼
Credit RWA
Market RWA
Operational RWA
        │
        ▼
Total RWA
```

---

# 9. Input Data Model

| Field           | Description |
| --------------- | ----------- |
| Exposure Amount | 익스포저 금액     |
| Risk Weight     | 위험가중치       |
| Credit RWA      | 신용위험 RWA    |
| Market RWA      | 시장위험 RWA    |
| Operational RWA | 운영위험 RWA    |
| Currency        | 기준 통화       |

---

# 10. Output Data Model

| Field           | Description |
| --------------- | ----------- |
| Credit RWA      |             |
| Market RWA      |             |
| Operational RWA |             |
| Total RWA       |             |

---

# 11. Example

| Component       | Amount |
| --------------- | -----: |
| Credit RWA      |    620 |
| Market RWA      |    180 |
| Operational RWA |    200 |

계산 결과

```text
Total RWA

=

620

+

180

+

200

=

1,000
```

이 값은 Capital Adequacy Ratio 계산의 분모가 된다.

---

# 12. Relationship with Capital Ratio

```text
Eligible Capital
        │
        ▼
Capital Adequacy Ratio
        ▲
        │
Total RWA
        ▲
        │
Credit RWA
Market RWA
Operational RWA
```

Capital Adequacy Ratio는

```text
Capital

÷

Total RWA
```

로 계산된다.

---

# 13. Implementation Architecture

```text
Credit Risk Engine
        │
        ├────────────┐
Market Risk Engine   │
        │            │
Operational Engine   │
        │            │
        ▼            ▼
      RWA Aggregator
              │
              ▼
       Total RWA
              │
              ▼
Capital Ratio Calculator
```

---

# 14. Implementation Considerations

시스템 구현 시 고려사항

* 위험 유형별 계산 엔진을 분리한다.
* RWA Aggregator는 합산만 수행한다.
* 각 위험 엔진은 독립적으로 검증 가능해야 한다.
* 위험 유형 추가(CVA 등)에 대비하여 확장 가능한 구조를 사용한다.
* 통화 및 단위 일관성을 보장한다.

---

# 15. Related Documents

## Reference Library

* RL-110 — Basel III Overview
* RL-120 — FRTB Overview

## Knowledge Base

* KB-201 — Financial Risk Overview
* KB-221 — Market Risk Overview
* KB-241 — Credit Risk Overview
* KB-281 — Operational Risk Overview
* KB-301 — Basel III Framework

## Formula Catalog

* FC-401 — Capital Adequacy Ratio
* FC-421 — Value at Risk
* FC-422 — Expected Shortfall
* FC-441 — Probability of Default
* FC-442 — Loss Given Default
* FC-443 — Exposure at Default

## Architecture Guide

* ARCH-701 — Capital Calculation Architecture
* ARCH-741 — RWA Aggregation Engine

---

# 16. Knowledge Path

```text
RL-110 Basel III Overview
        │
        ▼
KB-301 Basel III Framework
        │
        ▼
FC-402 Risk Weighted Assets
        │
        ├── FC-421 Expected Shortfall
        ├── FC-441 Probability of Default
        ├── FC-442 Loss Given Default
        └── FC-443 Exposure at Default
                │
                ▼
ARCH-741 RWA Aggregation Engine
```

---

# 17. Summary

Risk Weighted Assets(RWA)는 Basel III 규제 체계에서 서로 다른 위험을 공통 기준으로 환산하는 핵심 지표이다.

신용위험, 시장위험, 운영위험은 각각 독립적인 계산 엔진에서 산출되며, RWA Aggregator를 통해 Total RWA로 통합된다. Total RWA는 Capital Adequacy Ratio 계산의 분모로 사용되며, 금융기관의 규제자본 적정성을 평가하는 가장 중요한 입력값 중 하나이다.

FRKP에서는 RWA를 단순한 합산 결과가 아닌 **위험 측정(Risk Measurement)과 규제자본(Regulatory Capital)을 연결하는 핵심 Formula**로 정의한다.

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
