# RL-001 — Basel III Overview

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) > [Reference Library](../README.md) > [RL-001 — Basel III Overview](RL-001_BASEL_III_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) |
| ⬆ Parent Layer | [Reference Library](../README.md) |
| ➡ Next | None |

### Related Documents

- [KB-201](../../02_Knowledge_Base/01_Basel_III/KB-201_FINANCIAL_RISK_OVERVIEW.md)
- [KB-301](../../02_Knowledge_Base/01_Basel_III/KB-301_BASEL_III_FRAMEWORK.md)
- [FC-401](../../04_Formula_Catalog/01_Basel_III/FC-401_CAPITAL_ADEQUACY_RATIO.md)
- [FC-402](../../04_Formula_Catalog/01_Basel_III/FC-402_RISK_WEIGHTED_ASSETS.md)
- [ARCH-701](../../07_Architecture/01_Basel_III/ARCH-701_CAPITAL_CALCULATION_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item          | Value              |
| ------------- | ------------------ |
| Document ID   | RL-001             |
| Document Name | Basel III Overview |
| Version       | 1.0.0              |
| Status        | Draft              |
| Owner         | Project Lead       |
| Category      | Reference Library  |
| Created       | 2026-06-26         |
| Last Updated  | 2026-06-27         |

---

# 1. Purpose

본 문서는 Basel III 규제 체계의 전체 구조와 목적을 이해하기 위한 Reference Library 문서이다.

Basel III의 세부 규정을 모두 설명하는 것이 목적이 아니라, 전체 구조와 각 구성 요소의 역할을 이해하고 FRKP의 Knowledge Base, Formula Catalog 및 Risk Engine Architecture와 연결하기 위한 기준 문서로 활용한다.

---

# 2. What is Basel III?

Basel III는 국제 은행감독위원회(Basel Committee on Banking Supervision, BCBS)가 글로벌 금융위기(2007~2008) 이후 금융시스템의 안정성을 강화하기 위해 마련한 국제 은행 건전성 규제 체계이다.

Basel III의 핵심 목표는 다음과 같다.

* 은행의 자본 건전성 강화
* 과도한 레버리지 억제
* 유동성 리스크 관리 강화
* 시장 리스크 측정 개선
* 금융 시스템의 복원력(Resilience) 향상

---

# 3. Basel Framework

Basel 규제는 단계적으로 발전하였다.

| Framework | 주요 내용                     |
| --------- | ------------------------- |
| Basel I   | 최소 자기자본 규제 도입             |
| Basel II  | 위험 기반 자기자본 규제             |
| Basel III | 자본, 유동성, 레버리지 및 시장 리스크 강화 |

Basel III는 Basel II를 대체하는 것이 아니라 발전시킨 규제 체계이다.

---

# 4. Basel III Architecture

Basel III는 다음과 같은 주요 영역으로 구성된다.

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
├── Liquidity Risk
│
│     ├── LCR
│     └── NSFR
│
├── Large Exposure
│
└── Disclosure (Pillar 3)
```

---

# 5. Three Pillars

Basel III는 Basel II와 동일하게 세 개의 Pillar 구조를 유지한다.

## Pillar 1 — Minimum Capital Requirements

최소 규제자본을 산정하기 위한 기준이다.

주요 위험은 다음과 같다.

* Credit Risk
* Market Risk
* Operational Risk

---

## Pillar 2 — Supervisory Review

감독기관의 정성적 심사 체계이다.

주요 내용은 다음과 같다.

* ICAAP
* 내부 리스크 관리
* Stress Testing
* Governance

---

## Pillar 3 — Market Discipline

시장 공시를 통한 시장 규율을 강화한다.

주요 내용은 다음과 같다.

* 자본 공시
* 위험 공시
* 리스크 관리 정책 공시

---

# 6. Core Components

Basel III의 핵심 구성 요소는 다음과 같다.

| Component                       | Purpose     |
| ------------------------------- | ----------- |
| Capital Ratio                   | 규제자본 적정성 평가 |
| Risk Weighted Assets (RWA)      | 위험가중자산 산정   |
| Leverage Ratio                  | 과도한 레버리지 방지 |
| Liquidity Coverage Ratio (LCR)  | 단기 유동성 관리   |
| Net Stable Funding Ratio (NSFR) | 장기 유동성 관리   |
| Capital Buffer                  | 추가 자본 확보    |

---

# 7. Relationship Between Risk Types

Basel III는 다양한 리스크를 통합하여 규제자본을 산정한다.

```text
Credit Risk
        │
Market Risk
        │
Operational Risk
        │
        ▼
Risk Weighted Assets (RWA)
        │
        ▼
Capital Ratio
```

각 리스크는 독립적으로 측정되지만, 최종적으로는 RWA를 통해 하나의 자본 규제 체계로 통합된다.

---

# 8. Relationship with FRKP

FRKP에서는 Basel III를 최상위 규제 프레임워크로 사용한다.

| Basel III 영역       | FRKP 구성 요소                       |
| ------------------ | -------------------------------- |
| Credit Risk        | Knowledge Base / Formula Catalog |
| Market Risk        | Knowledge Base / FRTB            |
| Operational Risk   | Knowledge Base                   |
| Liquidity Risk     | Knowledge Base                   |
| Capital Regulation | Formula Catalog / Volume 3       |
| Disclosure         | Reference Library                |

---

# 9. Related Documents

## Reference Library

* RL-120 - FRTB Overview
* RL-130 - IFRS 9 Overview
* RL-004 - NCR Overview

## Knowledge Base

* KB-201 - Financial Risk Overview
* KB-221 - Market Risk Overview
* KB-231 - Credit Risk Overview
* KB-008 - Regulatory Capital

## Formula Catalog

* FC-401 - Capital Adequacy Ratio
* FC-402 - Risk Weighted Assets
* FC-103 - Leverage Ratio
* FC-104 - Liquidity Coverage Ratio

---

# 10. References주요 참고 자료

* Basel Committee on Banking Supervision(Basel III Framework)
* Basel Consolidated Framework
* 국내 Basel III 감독 규정
* 금융감독원 Basel III 관련 자료

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
| 1.0.1   | 2026-06-27 | Repaired legacy cross references |

