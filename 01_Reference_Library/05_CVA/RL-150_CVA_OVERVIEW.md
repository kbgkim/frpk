# RL-150 — Credit Valuation Adjustment (CVA) Overview

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Reference Library](../README.md) > [RL-150 — Credit Valuation Adjustment (CVA) Overview](RL-150_CVA_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Reference Library](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-140](../04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
- [KB-252](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)
- [AN-251](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)
- [FC-451](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)
<!-- FRKP-NAV-END -->

## Document Information

| Item            | Value                                      |
| --------------- | ------------------------------------------ |
| Document ID     | RL-150                                     |
| Document Name   | Credit Valuation Adjustment (CVA) Overview |
| Version         | 1.0.0                                      |
| Status          | Active                                     |
| Category        | Reference Library                          |
| Parent Bundle   | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)                                 |
| Parent Standard | [FRKP-DOC-001](../../00_Project_Management/Governance/Standards/FRKP-DOC-001_DOCUMENT_STANDARD.md)                               |
| Created         | 2026-06-27                                 |
| Last Updated    | 2026-06-27                                 |

---

# 1. Purpose

본 문서는 Basel III의 **Credit Valuation Adjustment(CVA)** 에 대한 개요를 설명한다.

CVA의 도입 배경, 경제적 의미, 규제 목적 및 Basel Framework에서의 위치를 설명하며, 이후 Knowledge Base, Formula Catalog 및 Implementation Guide의 기초 자료로 활용한다.

---

# 2. Scope

본 문서에서 다루는 범위는 다음과 같다.

### 포함

* Credit Valuation Adjustment 개요
* 도입 배경
* 경제적 의미
* Basel III에서의 역할
* SA-CCR와의 관계
* XVA 계열에서의 위치

### 제외

* 상세 계산 공식
* Hazard Rate 모델
* Discounting 모델
* Monte Carlo 구현
* CVA Capital Charge 산식

해당 내용은 후속 문서에서 다룬다.

---

# 3. Background

2007~2008년 글로벌 금융위기 이전에는 거래상대방 부도위험(Counterparty Credit Risk)이 충분히 반영되지 않았다.

그러나 금융위기 과정에서 대형 금융기관의 신용등급 하락과 부도 가능성이 파생상품 가치에 직접적인 영향을 미친다는 사실이 확인되었다.

대표적인 사례는 다음과 같다.

* Lehman Brothers
* Bear Stearns
* AIG

시장에서는 실제 부도(Default)보다 **신용스프레드(Credit Spread)의 확대**로 인해 더 큰 손실이 발생하는 경우가 많았다.

이에 따라 Basel III는 거래상대방 신용위험을 시장가치에 반영하는 **Credit Valuation Adjustment(CVA)** 개념을 도입하였다.

---

# 4. Definition

Credit Valuation Adjustment(CVA)는 거래상대방의 부도위험을 반영하여 파생상품의 공정가치를 조정하는 금액이다.

즉,

> 거래상대방이 부도날 가능성이 존재한다면 해당 계약의 현재 가치는 무위험 가치(Risk-Free Value)보다 낮아져야 한다.

이를 수식으로 표현하면 다음과 같은 개념이다.

```text
Risk-Free Value

        -

Expected Credit Loss

        =

Risk-Adjusted Value
```

여기서 Expected Credit Loss를 현재가치로 평가한 금액이 CVA이다.

---

# 5. Economic Meaning

CVA는 미래의 거래상대방 부도에 따른 예상 손실(Expected Loss)을 현재 가치로 환산한 것이다.

경제적으로는 다음 요소가 결합된다.

```text
Exposure

↓

Probability of Default

↓

Loss Given Default

↓

Discounting

↓

Credit Valuation Adjustment
```

즉,

* 노출금액(Exposure)
* 부도확률(PD)
* 부도 시 손실률(LGD)
* 할인율(Discount Factor)

이 함께 고려된다.

---

# 6. Position within Basel III

Basel III에서는 CVA를 독립적인 규제 영역으로 관리한다.

```text
Basel III
│
├── Credit Risk
├── Market Risk
├── Counterparty Credit Risk
│       │
│       ├── SA-CCR
│       └── CVA
├── Operational Risk
└── Liquidity Risk
```

SA-CCR는 거래상대방 위험 노출(Exposure)을 계산하고,

CVA는 해당 노출에 거래상대방의 신용위험을 반영하여 가치조정을 수행한다.

---

# 7. Relationship with SA-CCR

SA-CCR와 CVA는 상호 보완적인 관계를 가진다.

```text
Trade Portfolio
        │
        ▼
SA-CCR
        │
        ▼
Exposure at Default (EAD)
        │
        ▼
Expected Exposure Profile
        │
        ▼
Credit Valuation Adjustment
```

SA-CCR는 노출을 계산하고,

CVA는 그 노출의 시장가치 조정을 수행한다.

---

# 8. Relationship with XVA

CVA는 XVA(Value Adjustment) 계열의 일부이다.

```text
Value Adjustment
│
├── CVA
├── DVA
├── FVA
├── MVA
├── KVA
└── ColVA
```

각 Value Adjustment는 서로 다른 위험요인을 반영한다.

| Adjustment | Description              |
| ---------- | ------------------------ |
| CVA        | Counterparty Credit Risk |
| DVA        | Own Credit Risk          |
| FVA        | Funding Cost             |
| MVA        | Initial Margin Cost      |
| KVA        | Capital Cost             |
| ColVA      | Collateral Cost          |

---

# 9. Regulatory Objective

Basel III에서 CVA를 도입한 목적은 다음과 같다.

* 거래상대방 신용위험의 시장가치 반영
* 신용스프레드 변동 위험 관리
* 금융기관 자본 적정성 강화
* 파생상품 위험의 현실적 평가
* 규제자본 산정의 정교화

---

# 10. Bundle Relationship

Bundle-005는 다음 Bundle과 연결된다.

```text
Bundle-003
IFRS 9
      │
      ▼
Bundle-004
SA-CCR
      │
      ▼
Bundle-005
CVA
      │
      ▼
Bundle-006
Market Risk Standardized Approach
```

---

# 11. Related Documents

| Category       | Document                                  |
| -------------- | ----------------------------------------- |
| Reference      | [RL-140_SA_CCR_OVERVIEW](../04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)                    |
| Knowledge      | [KB-251_CREDIT_VALUATION_ADJUSTMENT](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Knowledge      | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Analysis       | [AN-251_WHY_CVA_WAS_INTRODUCED](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)             |
| Formula        | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula        | [FC-452_EXPECTED_EXPOSURE](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)                  |
| Formula        | [FC-453_CREDIT_VALUATION_ADJUSTMENT](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Formula        | [FC-454_CVA_CAPITAL_CHARGE](../../04_Formula_Catalog/05_CVA/FC-454_CVA_CAPITAL_CHARGE.md)                 |
| Implementation | [IMP-451_CVA_IMPLEMENTATION](../../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)                |
| Architecture   | [ARCH-751_CVA_ARCHITECTURE](../../07_Architecture/05_CVA/ARCH-751_CVA_ARCHITECTURE.md)                 |

---

# 12. Summary

Credit Valuation Adjustment(CVA)는 거래상대방의 신용위험을 파생상품 가치에 반영하기 위한 가치조정(Value Adjustment)이다.

Basel III에서는 SA-CCR가 계산한 거래상대방 위험 노출을 기반으로, 부도확률과 손실률 및 할인효과를 반영하여 CVA를 산출한다.

CVA는 거래상대방 신용위험을 시장가치에 반영함으로써 금융기관의 위험관리와 규제자본 산정의 정확성을 높이는 핵심 요소이다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
