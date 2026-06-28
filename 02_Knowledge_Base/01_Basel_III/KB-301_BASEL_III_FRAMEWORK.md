# KB-301 — Basel III Framework

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) > [Knowledge Base](../README.md) > [KB-301 — Basel III Framework](KB-301_BASEL_III_FRAMEWORK.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [KB-201](KB-201_FINANCIAL_RISK_OVERVIEW.md) |
| ⬆ Parent Bundle | [BUNDLE-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-001](../../01_Reference_Library/01_Basel_III/RL-001_BASEL_III_OVERVIEW.md)
- [KB-201](KB-201_FINANCIAL_RISK_OVERVIEW.md)
- [FC-401](../../04_Formula_Catalog/01_Basel_III/FC-401_CAPITAL_ADEQUACY_RATIO.md)
- [FC-402](../../04_Formula_Catalog/01_Basel_III/FC-402_RISK_WEIGHTED_ASSETS.md)
- [ARCH-701](../../07_Architecture/01_Basel_III/ARCH-701_CAPITAL_CALCULATION_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item          | Value               |
| ------------- | ------------------- |
| Document ID   | KB-301              |
| Document Name | Basel III Framework |
| Version       | 1.0.0               |
| Status        | Draft               |
| Owner         | Project Lead        |
| Category      | Knowledge Base      |
| Created       | 2026-06-26          |
| Last Updated  | 2026-06-26          |

---

# 1. Purpose

본 문서는 Basel III 규제 체계의 전체 구조를 이해하기 위한 Knowledge Base 문서이다.

Reference Library(RL-110)가 Basel III의 개요를 제공한다면, 본 문서는 Basel III를 구성하는 각 규제 요소와 이들 간의 관계를 설명한다.

---

# 2. Overview

Basel III는 국제 은행감독위원회(BCBS)가 제정한 글로벌 은행 건전성 규제 프레임워크이다.

목표는 금융기관이 충분한 자본과 유동성을 확보하여 시장 충격에도 안정적으로 운영될 수 있도록 하는 것이다.

Basel III는 단일 규제가 아니라 여러 규제 체계를 통합한 프레임워크이다.

---

# 3. Basel III Structure

```text
Basel III
│
├── Capital Regulation
│
├── Credit Risk
│
├── Market Risk (FRTB)
│
├── Counterparty Credit Risk
│
├── CVA Risk
│
├── Operational Risk
│
├── Leverage Ratio
│
├── Liquidity
│     ├── LCR
│     └── NSFR
│
└── Disclosure (Pillar 3)
```

---

# 4. Three Pillars

Basel III는 세 개의 Pillar를 기반으로 구성된다.

| Pillar   | Description                 |
| -------- | --------------------------- |
| Pillar 1 | 최소 규제자본 산정                  |
| Pillar 2 | 감독기관의 건전성 평가(SREP, ICAAP 등) |
| Pillar 3 | 시장 공시를 통한 시장 규율             |

세 Pillar는 상호 보완적으로 금융기관의 건전성을 확보한다.

---

# 5. Capital Framework

규제자본은 다음 세 가지로 구성된다.

| Capital | Description           |
| ------- | --------------------- |
| CET1    | Common Equity Tier 1  |
| AT1     | Additional Tier 1     |
| Tier 2  | Supplementary Capital |

규제자본은 Risk Weighted Assets(RWA)와 비교하여 자본 적정성을 평가한다.

---

# 6. Risk Components

Pillar 1의 최소자본 규제는 다음 위험을 포함한다.

| Risk                     | Description |
| ------------------------ | ----------- |
| Credit Risk              | 신용위험        |
| Market Risk              | 시장위험(FRTB)  |
| Operational Risk         | 운영위험        |
| CVA Risk                 | 신용가치조정 위험   |
| Counterparty Credit Risk | 거래상대방 위험    |

각 위험은 독립적으로 측정되며 최종적으로 RWA에 반영된다.

---

# 7. Capital Calculation Flow

```text
Financial Position
        │
        ▼
Credit Risk
Market Risk
Operational Risk
        │
        ▼
Risk Weighted Assets (RWA)
        │
        ▼
Eligible Capital
        │
        ▼
Capital Ratios
```

---

# 8. Relationship with FRKP

| Basel III              | FRKP Document   |
| ---------------------- | --------------- |
| Basel III Overview     | RL-110          |
| Financial Risk         | [KB-201](KB-201_FINANCIAL_RISK_OVERVIEW.md)          |
| Basel III Framework    | [KB-301](KB-301_BASEL_III_FRAMEWORK.md)          |
| Capital Adequacy Ratio | [FC-401](../../04_Formula_Catalog/01_Basel_III/FC-401_CAPITAL_ADEQUACY_RATIO.md)          |
| Risk Weighted Assets   | [FC-402](../../04_Formula_Catalog/01_Basel_III/FC-402_RISK_WEIGHTED_ASSETS.md)          |
| FRTB                   | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md) / [KB-221](../02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md) |

---

# 9. Knowledge Path

```text
RL-110
Basel III Overview
        │
        ▼
KB-301
Basel III Framework
        │
        ▼
FC-401
Capital Adequacy Ratio
        │
        ▼
FC-402
Risk Weighted Assets
        │
        ▼
RL-120
FRTB Overview
```

---

# 10. Summary

Basel III는 단일 규제가 아니라 자본, 유동성, 레버리지, 시장위험, 신용위험, 운영위험을 하나의 규제 체계로 통합한 글로벌 금융 규제 프레임워크이다.

FRKP에서는 Basel III를 최상위 규제 프레임워크로 정의하며, 이후 Formula Catalog와 Architecture Guide에서 각 규제 요소의 계산 방법과 구현 구조를 상세히 다룬다.

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
