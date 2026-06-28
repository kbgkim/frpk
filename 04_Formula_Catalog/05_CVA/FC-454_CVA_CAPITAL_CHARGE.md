<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Formula Catalog](../README.md) > [FC-454_CVA_CAPITAL_CHARGE](FC-454_CVA_CAPITAL_CHARGE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-453](FC-453_CREDIT_VALUATION_ADJUSTMENT.md) |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
- [KB-252](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)
- [AN-251](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)
- [MF-451](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)
<!-- FRKP-NAV-END -->
---

# FC-454 — CVA Capital Charge

---

# Document Information

| Item               | Value                                          |
| ------------------ | ---------------------------------------------- |
| Document ID        | FC-454                                         |
| Document Name      | CVA Capital Charge                             |
| Version            | 1.0.0                                          |
| Status             | Active                                         |
| Category           | Formula Catalog                                |
| Bundle             | Bundle-005 — Credit Valuation Adjustment (CVA) |
| Layer              | Formula Catalog                                |
| Created            | 2026-06-27                                     |
| Last Updated       | 2026-06-27                                     |
| Formula Type       | Regulatory Capital Formula                     |
| Primary Regulation | Basel III / Basel Framework for CVA Risk       |

---

# 1. Purpose

본 문서는 Basel III/IV 규제체계에서 정의하는 **Credit Valuation Adjustment (CVA) Capital Charge**의 계산 목적과 계산 계약(Calculation Contract)을 정의한다.

본 문서는 Formula Catalog 계층에 속하며 구현 기술과 독립적으로 CVA 자본 산식의 논리적 정의를 제공한다.

---

# 2. Business Purpose

CVA Capital Charge는 거래상대방의 **부도(Default)** 자체가 아니라 **신용스프레드(Credit Spread)의 변동으로 인해 파생상품의 공정가치가 변하는 위험**을 자본으로 측정하기 위한 공식이다.

주요 목적은 다음과 같다.

* OTC 파생상품 포트폴리오의 CVA 위험 측정
* 거래상대방 신용스프레드 위험 반영
* Basel 규제자본 산정
* 은행의 자본 적정성 관리
* CCR과 별도의 시장가치 위험 측정

---

# 3. Regulatory Perspective

Basel III 이후 규제에서는 금융위기 경험을 반영하여 **CVA Risk**를 Counterparty Credit Risk(CCR)와 별도의 위험으로 정의하였다.

대표적인 접근법은 다음과 같다.

* Basic CVA (BA-CVA)
* Standardized CVA (SA-CVA)

본 Formula는 특정 접근법의 구현이 아니라 **공통적인 계산 계약**을 정의한다.

---

# 4. Mathematical Definition

CVA Capital Charge는 개념적으로 다음과 같이 표현할 수 있다.

```math
Capital_{CVA}=f(EE,PD,LGD,DF,Spread,Hedges)
```

이 정의는 CVA 자본요구액이 익스포저, 부도확률, 손실률, 할인계수, 신용스프레드 및 인정 헤지 효과를 입력으로 하는 규제 자본 산식임을 나타낸다.

여기서 함수 \(f\)는 적용되는 규제 방식(BA-CVA 또는 SA-CVA)에 따라 달라지며, 본 문서는 특정 방식의 세부 계수나 감독상 파라미터를 고정하지 않는다.

---

# 5. Variable Definitions

| Symbol     | Description                 |
| ---------- | --------------------------- |
| EE         | Expected Exposure           |
| PD         | Probability of Default      |
| LGD        | Loss Given Default          |
| DF         | Discount Factor             |
| Spread     | Credit Spread               |
| Hedges     | Eligible CVA Hedges         |
| CapitalCVA | Required Regulatory Capital |

---

# 6. Formula Interpretation

CVA Capital Charge는 기대손실(Expected Loss)을 계산하는 공식이 아니라 **신용스프레드 변동으로 인한 시장가치 위험**을 규제자본으로 환산하는 공식이다.

계산에는 다음 요소가 반영된다.

1. Expected Exposure
2. Default Probability
3. Loss Given Default
4. Discount Factor
5. Credit Spread
6. Eligible Hedge Effects

---

# 7. Input Contract

| Input                  | Required | Description    |
| ---------------------- | :------: | -------------- |
| Expected Exposure      |     ✔    | 미래 예상 익스포저     |
| Probability of Default |     ✔    | 부도확률           |
| Loss Given Default     |     ✔    | 부도손실률          |
| Discount Factor        |     ✔    | 할인계수           |
| Credit Spread          |     ✔    | 거래상대방 신용스프레드   |
| Eligible Hedges        | Optional | 규제상 인정되는 헤지 정보 |

---

# 8. Computation Contract

계산 절차는 다음과 같은 논리 흐름을 따른다.

```text
Expected Exposure
        │
        ▼
Default Probability
        │
        ▼
Loss Given Default
        │
        ▼
Discount Factor
        │
        ▼
Credit Spread Adjustment
        │
        ▼
Eligible Hedge Adjustment
        │
        ▼
CVA Capital Charge
```

본 문서는 계산 절차의 논리적 계약만 정의하며 구현 알고리즘은 포함하지 않는다.

---

# 9. Output Contract

| Output             | Description       |
| ------------------ | ----------------- |
| CVA Capital Charge | 규제상 요구되는 CVA 자본금액 |

출력은 일반적으로 통화 단위(Currency Amount)로 표현된다.

---

# 10. Formula Engine Model

Formula Engine 관점의 논리 모델은 다음과 같다.

```text
Input Collector
        │
        ▼
Exposure Resolver
        │
        ▼
Risk Parameter Resolver
        │
        ▼
Capital Calculator
        │
        ▼
Result Builder
```

이는 논리 모델이며 특정 구현 기술을 의미하지 않는다.

---

# 11. Relationship with FRKP

```text
RL-150
        │
        ▼
KB-251
        │
        ▼
KB-252
        │
        ▼
AN-251
        │
        ▼
MF-451
MF-452
MF-453
        │
        ▼
FC-451
FC-452
FC-453
        │
        ▼
FC-454
        │
        ▼
IMP-451
        │
        ▼
ARCH-751
```

---

# 12. Related Formulae

| Formula  | Relationship                       |
| -------- | ---------------------------------- |
| FC-451   | Default Probability Term Structure |
| FC-452   | Expected Exposure                  |
| FC-453   | Credit Valuation Adjustment        |
| IMP-451  | CVA Implementation                 |
| ARCH-751 | CVA Architecture                   |

---

# 13. Assumptions and Constraints

본 Formula는 다음을 가정한다.

* 입력 데이터는 규제 기준에 따라 검증되어야 한다.
* 할인곡선은 시장 데이터 기반으로 구축된다.
* 헤지는 규제상 인정되는 거래만 반영한다.
* 적용 방식은 BA-CVA 또는 SA-CVA일 수 있다.

---

# 14. Non-functional Requirements

본 Formula는 다음 특성을 만족해야 한다.

* Deterministic
* Technology Neutral
* Reproducible
* Traceable
* Independent
* Reusable

---

# 15. Relationship to Other Standards

본 Formula는 다음 FRKP 표준을 준수한다.

* FRKP-DOC-001 — Documentation Standard
* FRKP-ID-001 — Document Identifier Standard
* FRKP-FORM-001 — Formula Documentation Standard

---

# 16. Formula Classification

| Classification Item | Value |
| ------------------- | ----- |
| Formula ID          | FC-454 |
| Formula Domain      | Credit Valuation Adjustment |
| Formula Category    | Regulatory Capital |
| Formula Type        | CVA Capital Charge |
| Regulatory Context  | Basel III / Basel Framework for CVA Risk |
| Implementation Role | Capital calculation contract |

---

# 17. Formula Dependency

| Dependency | Role |
| ---------- | ---- |
| FC-451     | Provides default probability term structure input |
| FC-452     | Provides expected exposure input |
| FC-453     | Provides CVA valuation context |
| MF-451     | Provides hazard-rate foundation |
| MF-452     | Provides discounting foundation |
| MF-453     | Provides expected-exposure foundation |

---

# 18. Summary

CVA Capital Charge는 거래상대방 신용스프레드 변동으로 발생하는 파생상품 가치 변동 위험을 규제자본으로 환산하는 핵심 Formula이다.

본 문서는 CVA 자본 계산의 논리적 계약을 정의하며, 실제 계산 알고리즘과 시스템 구현은 Implementation Guide와 Architecture Guide에서 다룬다.

---

# 19. Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-06-27 | Initial document |

