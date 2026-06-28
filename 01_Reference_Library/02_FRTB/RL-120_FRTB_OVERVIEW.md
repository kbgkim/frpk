# RL-120 — FRTB Overview

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Reference Library](../README.md) > [RL-120 — FRTB Overview](RL-120_FRTB_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Reference Library](../README.md) |
| ➡ Next | None |

### Related Documents

- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
- [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)
- [FC-422](../../04_Formula_Catalog/02_FRTB/FC-422_LIQUIDITY_HORIZON.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item            | Value             |
| --------------- | ----------------- |
| Document ID     | RL-120            |
| Document Name   | FRTB Overview     |
| Version         | 1.0.0             |
| Status          | Draft             |
| Owner           | Project Lead      |
| Category        | Reference Library |
| Parent Document | RL-110            |
| Created         | 2026-06-26        |
| Last Updated    | 2026-06-26        |

---

# 1. Purpose

본 문서는 Fundamental Review of the Trading Book(FRTB)의 목적, 배경 및 전체 구조를 설명하는 Reference Library 문서이다.

FRTB는 Basel III 시장위험(Market Risk) 규제의 핵심 프레임워크이며, 기존 Value at Risk(VaR) 기반 규제를 Expected Shortfall(ES) 기반으로 전환한 국제 규제 체계이다.

본 문서는 FRTB의 개요를 제공하며, 세부 계산 방법은 Knowledge Base, Formula Catalog 및 Architecture Guide에서 다룬다.

---

# 2. Background

2007~2008년 글로벌 금융위기 동안 기존 Basel 2.5의 시장위험 규제는 실제 손실을 충분히 반영하지 못하였다.

주요 문제점은 다음과 같았다.

* VaR는 꼬리위험(Tail Risk)을 충분히 반영하지 못함
* 정상시장(Normal Market) 중심의 위험 측정
* 거래부문(Trading Book)과 은행부문(Banking Book) 경계의 모호성
* 복잡한 파생상품 위험의 과소평가
* 모델 위험(Model Risk)에 대한 관리 부족

이러한 문제를 해결하기 위해 BCBS는 FRTB를 도입하였다.

---

# 3. Objectives

FRTB의 주요 목표는 다음과 같다.

* 시장위험 측정의 정확성 향상
* 극단적 시장상황(Tail Event) 반영
* Trading Book과 Banking Book의 명확한 구분
* 내부모형(IMA) 승인 기준 강화
* 표준방법(Standardised Approach)의 위험 민감도 향상
* 규제자본의 일관성 확보

---

# 4. FRTB Architecture

```text
Basel III
      │
      ▼
Market Risk
      │
      ▼
FRTB
      │
      ├── Standardised Approach (SA)
      │
      └── Internal Models Approach (IMA)
```

FRTB는 크게 **표준방법(SA)** 과 **내부모형방법(IMA)** 으로 구성된다.

---

# 5. Key Components

## 5.1 Standardised Approach (SA)

SA는 모든 금융기관이 적용 가능한 기본 시장위험 측정 방법이다.

주요 구성 요소는 다음과 같다.

* Sensitivity-Based Method (SBM)
* Default Risk Charge (DRC)
* Residual Risk Add-On (RRAO)

---

## 5.2 Internal Models Approach (IMA)

IMA는 감독기관의 승인을 받은 금융기관이 사용하는 내부모형이다.

주요 특징은 다음과 같다.

* Expected Shortfall 기반
* Risk Factor Eligibility Test(RFET)
* Profit & Loss Attribution(P&L Attribution)
* Backtesting

---

# 6. Major Changes from Basel 2.5

| Basel 2.5          | FRTB                     |
| ------------------ | ------------------------ |
| VaR                | Expected Shortfall       |
| 단일 보유기간            | Liquidity Horizon 적용     |
| 단순 승인              | 엄격한 모델 승인                |
| 포트폴리오 중심           | Risk Factor 중심           |
| 단순 Standard Method | Sensitivity-Based Method |

---

# 7. Core Concepts

FRTB를 이해하기 위한 핵심 개념은 다음과 같다.

| Concept            | Description       |
| ------------------ | ----------------- |
| Trading Book       | 매매목적 보유 자산        |
| Banking Book       | 만기보유 및 일반 은행업무 자산 |
| Expected Shortfall | 극단적 손실 평균         |
| Liquidity Horizon  | 위험요인별 청산기간        |
| Risk Factor        | 위험을 발생시키는 시장 변수   |
| Sensitivity        | 위험요인에 대한 민감도      |
| Modellability      | 위험요인의 모델 가능 여부    |

---

# 8. Capital Calculation Flow

```text
Trading Positions
        │
        ▼
Risk Factor Mapping
        │
        ▼
Sensitivity Calculation
        │
        ▼
Expected Shortfall
        │
        ▼
Market Capital Requirement
        │
        ▼
Market RWA
        │
        ▼
Capital Adequacy Ratio
```

FRTB에서 계산된 Market RWA는 Credit RWA 및 Operational RWA와 함께 Total RWA를 구성한다.

---

# 9. Relationship with FRKP

| FRTB Component           | FRKP Document |
| ------------------------ | ------------- |
| Overview                 | [RL-120](RL-120_FRTB_OVERVIEW.md)        |
| Market Risk              | [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)        |
| FRTB Framework           | [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)        |
| Why VaR Failed           | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)        |
| Expected Shortfall       | [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)        |
| Liquidity Horizon        | [FC-422](../../04_Formula_Catalog/02_FRTB/FC-422_LIQUIDITY_HORIZON.md)        |
| Sensitivity-Based Method | [FC-423](../../04_Formula_Catalog/02_FRTB/FC-423_SENSITIVITY_BASED_METHOD.md)        |
| FRTB Architecture        | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)      |

---

# 10. Knowledge Graph

```text
Basel III
      │
      ▼
Market Risk
      │
      ▼
FRTB
      │
      ├── Trading Book
      ├── Expected Shortfall
      ├── Liquidity Horizon
      ├── Risk Factor
      ├── Sensitivity
      ├── DRC
      └── RRAO
```

---

# 11. Learning Path

권장 학습 순서는 다음과 같다.

```text
RL-110 Basel III Overview
        │
        ▼
KB-301 Basel III Framework
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

# 12. Summary

FRTB는 Basel III 시장위험 규제의 핵심 프레임워크로서, 금융위기에서 드러난 VaR 기반 규제의 한계를 보완하기 위해 도입되었다.

FRTB는 Expected Shortfall, Liquidity Horizon, Sensitivity-Based Method 등 새로운 개념을 도입하여 시장위험을 보다 현실적으로 측정하며, 내부모형 승인 기준도 크게 강화하였다.

FRKP에서는 FRTB를 단순한 규제가 아니라 **시장위험 측정, Formula Engine, Risk Engine Architecture를 연결하는 핵심 프레임워크**로 정의한다.

---

# 13. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
