# KB-201 — Financial Risk Overview

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) > [Knowledge Base](../README.md) > [KB-201 — Financial Risk Overview](KB-201_FINANCIAL_RISK_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | [KB-301](KB-301_BASEL_III_FRAMEWORK.md) |

### Related Documents

- [RL-001](../../01_Reference_Library/01_Basel_III/RL-001_BASEL_III_OVERVIEW.md)
- [KB-301](KB-301_BASEL_III_FRAMEWORK.md)
- [FC-401](../../04_Formula_Catalog/01_Basel_III/FC-401_CAPITAL_ADEQUACY_RATIO.md)
- [FC-402](../../04_Formula_Catalog/01_Basel_III/FC-402_RISK_WEIGHTED_ASSETS.md)
- [ARCH-701](../../07_Architecture/01_Basel_III/ARCH-701_CAPITAL_CALCULATION_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item          | Value                   |
| ------------- | ----------------------- |
| Document ID   | KB-201                  |
| Document Name | Financial Risk Overview |
| Version       | 1.0.0                   |
| Status        | Draft                   |
| Owner         | Project Lead            |
| Category      | Knowledge Base          |
| Created       | 2026-06-26              |
| Last Updated  | 2026-06-26              |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 최상위 Knowledge Base 문서이다.

금융 리스크 관리의 전체 구조를 설명하며, 이후 작성되는 모든 Knowledge Base, Formula Catalog, Architecture Guide 및 Handbook의 출발점 역할을 한다.

---

# 2. What is Financial Risk?

금융 리스크(Financial Risk)는 미래의 불확실성으로 인해 금융기관이나 투자자가 경제적 손실을 입을 가능성을 의미한다.

금융 리스크 관리는 이러한 손실 가능성을 식별(Identify), 측정(Measure), 모니터링(Monitor), 통제(Control)하는 체계적인 활동이다.

궁극적인 목적은 위험을 제거하는 것이 아니라 **허용 가능한 수준으로 관리하면서 안정적인 수익을 창출하는 것**이다.

---

# 3. Financial Risk Management Framework

금융 리스크 관리는 다음과 같은 순환 구조로 이루어진다.

```text
Risk Identification
        │
        ▼
Risk Measurement
        │
        ▼
Risk Monitoring
        │
        ▼
Risk Control
        │
        ▼
Risk Reporting
        │
        └──────────────┐
                       ▼
             Continuous Improvement
```

각 단계는 독립적이지 않으며 지속적으로 반복된다.

---

# 4. Classification of Financial Risk

금융기관이 관리하는 주요 리스크는 다음과 같다.

| Risk Type             | Description                           |
| --------------------- | ------------------------------------- |
| Market Risk           | 시장 가격 변동으로 발생하는 손실 위험                 |
| Credit Risk           | 거래상대방의 채무불이행으로 발생하는 손실 위험             |
| Liquidity Risk        | 필요한 자금을 적시에 조달하지 못하는 위험               |
| Operational Risk      | 내부 프로세스, 시스템, 인적 오류 및 외부 사건으로 발생하는 위험 |
| Interest Rate Risk    | 금리 변동으로 인한 위험                         |
| Foreign Exchange Risk | 환율 변동으로 인한 위험                         |
| Counterparty Risk     | 파생상품 거래 상대방 위험                        |
| Concentration Risk    | 특정 자산이나 거래상대방에 대한 편중 위험               |

---

# 5. Regulatory Framework

금융 리스크 관리는 다양한 국제 규제 체계를 기반으로 수행된다.

| Regulation     | Primary Scope   |
| -------------- | --------------- |
| Basel III      | 은행 건전성 및 규제자본   |
| FRTB           | 시장 리스크          |
| IFRS 9         | 기대신용손실(ECL)     |
| SA-CCR         | 장외파생상품 거래상대방 위험 |
| BCBS Standards | 국제 은행 감독 기준     |

각 규제는 독립적으로 존재하지만 실제 금융기관에서는 하나의 리스크 관리 체계로 통합되어 운영된다.

---

# 6. Core Risk Management Process

일반적인 금융 리스크 관리 프로세스는 다음과 같다.

```text
Financial Products
        │
        ▼
Exposure Calculation
        │
        ▼
Risk Measurement
        │
        ▼
Capital Calculation
        │
        ▼
Limit Management
        │
        ▼
Management Reporting
```

FRKP에서는 각 단계를 독립적인 Knowledge Base와 Formula Catalog로 상세히 다룬다.

---

# 7. Risk Measurement

리스크 측정은 금융 리스크 관리의 핵심이다.

대표적인 측정 방법은 다음과 같다.

| Measure                 | Purpose             |
| ----------------------- | ------------------- |
| Value at Risk (VaR)     | 일정 신뢰수준에서의 최대 예상 손실 |
| Expected Shortfall (ES) | 극단적 손실의 평균          |
| Stress Test             | 극한 시장 상황 분석         |
| Scenario Analysis       | 가정된 시장 변화 분석        |
| Sensitivity Analysis    | 위험요인 변화에 대한 민감도 분석  |

---

# 8. Relationship Between Risk Types

금융 리스크는 서로 독립적이지 않다.

```text
Financial Products
        │
        ├── Market Risk
        ├── Credit Risk
        ├── Liquidity Risk
        └── Operational Risk
                │
                ▼
      Risk Aggregation
                │
                ▼
   Regulatory Capital
```

최종적으로 다양한 리스크는 규제자본(Regulatory Capital) 산정을 위해 통합된다.

---

# 9. FRKP Knowledge Map

FRKP에서는 금융 리스크를 다음 계층으로 관리한다.

```text
Reference Library
        │
        ▼
Knowledge Base
        │
        ▼
Formula Catalog
        │
        ▼
Implementation Guide
        │
        ▼
Architecture Guide
        │
        ▼
Handbook Volumes
```

각 계층은 동일한 주제를 서로 다른 관점에서 설명한다.

---

# 10. Related Documents

## Reference Library

* RL-110 — Basel III Overview
* RL-120 — FRTB Overview
* RL-130 — IFRS 9 Overview

## Knowledge Base

* KB-221 — Market Risk Overview
* KB-241 — Credit Risk Overview
* KB-261 — Liquidity Risk Overview
* KB-281 — Operational Risk Overview
* KB-301 — Basel III Framework

## Formula Catalog

* FC-401 — Capital Adequacy Ratio
* FC-402 — Risk Weighted Assets
* FC-421 — Value at Risk
* FC-422 — Expected Shortfall
* FC-441 — Probability of Default
* FC-442 — Loss Given Default

---

# 11. Learning Path

본 문서를 학습한 후 다음 순서를 권장한다.

```text
KB-201 Financial Risk Overview
        │
        ├── RL-110 Basel III Overview
        ├── RL-120 FRTB Overview
        ├── RL-130 IFRS 9 Overview
        │
        ▼
KB-221 Market Risk Overview
        │
        ▼
KB-241 Credit Risk Overview
        │
        ▼
FC-401 Capital Adequacy Ratio
        │
        ▼
ARCH-701 Capital Calculation Architecture
```

---

# 12. Summary

Financial Risk Management는 다양한 위험을 개별적으로 측정하는 것이 아니라, 이를 통합하여 금융기관의 건전성과 지속 가능성을 확보하는 활동이다.

FRKP는 이러한 금융 리스크 관리 체계를 **Reference → Knowledge → Formula → Implementation → Architecture → Volume**의 계층 구조로 체계화하여 금융 실무자와 개발자가 함께 활용할 수 있는 지식 플랫폼을 구축하는 것을 목표로 한다.

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
