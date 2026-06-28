# RL-140 — SA-CCR Overview

---

# Document Information

| Item            | Value             |
| --------------- | ----------------- |
| Document ID     | RL-140            |
| Document Name   | SA-CCR Overview   |
| Version         | 1.0.0             |
| Status          | Draft             |
| Category        | Reference Library |
| Parent Document | Bundle-004        |
| Created         | 2026-06-26        |
| Last Updated    | 2026-06-26        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Reference Library](../README.md) > [RL-140 — SA-CCR Overview](RL-140_SA_CCR_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Reference Library](../README.md) |
| ➡ Next | None |

### Related Documents

- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
- [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)
- [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)
- [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md)
- [FC-442](../../04_Formula_Catalog/04_SA_CCR/FC-442_POTENTIAL_FUTURE_EXPOSURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III에서 정의한 **SA-CCR (Standardised Approach for Counterparty Credit Risk)** 의 개요를 설명한다.

SA-CCR는 파생상품 및 증권금융거래(Securities Financing Transactions, SFT)의 **거래상대방 신용위험(Counterparty Credit Risk, CCR)** 을 측정하기 위한 국제 표준 접근법이다.

FRKP에서는 SA-CCR를 **Counterparty Credit Risk의 표준 노출액 산정 프레임워크**로 정의한다.

---

# 2. Background

Basel II에서는 거래상대방 신용위험 측정을 위해 다음과 같은 방법을 사용하였다.

* Current Exposure Method (CEM)
* Standardized Method (SM)
* Internal Model Method (IMM)

이들 방법은 금융위기 이후 다음과 같은 한계가 확인되었다.

* 위험 민감도가 낮음
* 담보 효과 반영 부족
* 상계(Netting) 효과 반영 부족
* 파생상품 특성 반영 부족
* 시장 변동성 반영 부족

이를 개선하기 위해 Basel III는 SA-CCR를 도입하였다.

---

# 3. What is Counterparty Credit Risk?

거래상대방 신용위험(CCR)은 계약 상대방이 계약 만기 이전에 채무를 이행하지 못하여 금융기관이 손실을 입을 위험이다.

일반적인 대출의 신용위험과 달리 CCR은 시장가격 변동에 따라 익스포저가 지속적으로 변화한다.

대표적인 대상은 다음과 같다.

* 금리 스왑
* 통화 스왑
* 선도계약
* 선물계약
* 옵션
* Repo
* Reverse Repo
* Securities Lending

---

# 4. Position within Basel III

```text
Basel III
     │
     ├───────────────┐
     ▼               ▼
Market Risk      Credit Risk
(FRTB)               │
                     ▼
      Counterparty Credit Risk
                     │
                     ▼
                  SA-CCR
                     │
                     ▼
                     EAD
                     │
          ┌──────────┴──────────┐
          ▼                     ▼
      Basel IRB               CVA
```

SA-CCR는 Basel III 신용위험 체계의 핵심 구성 요소이다.

---

# 5. Objectives of SA-CCR

SA-CCR의 주요 목적은 다음과 같다.

* 거래상대방 신용위험의 현실적 측정
* 위험 민감도 향상
* 담보 효과 반영
* 상계 계약(Netting Agreement) 반영
* 국제 규제의 일관성 확보
* 자본규제의 정확성 향상

---

# 6. Core Components

SA-CCR는 다음 요소로 구성된다.

| Component                       | Description |
| ------------------------------- | ----------- |
| Replacement Cost (RC)           | 현재 재조달 비용   |
| Potential Future Exposure (PFE) | 잠재 미래 익스포저  |
| Alpha                           | 규제 보정 계수    |
| Exposure at Default (EAD)       | 부도 시 익스포저   |

---

# 7. High-Level Formula

SA-CCR의 핵심 구조는 다음과 같다.

```text
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Alpha
        │
        ▼
Exposure at Default
```

세부 산식은 Formula Catalog에서 설명한다.

---

# 8. Replacement Cost

Replacement Cost(RC)는 거래를 현재 시점에서 다시 체결하기 위해 필요한 비용이다.

시장가치(Mark-to-Market)를 기준으로 계산되며 담보 효과가 반영된다.

---

# 9. Potential Future Exposure

PFE는 계약 만기까지 시장가격이 변동함에 따라 미래에 발생할 수 있는 추가 익스포저를 의미한다.

PFE는 다음 요소에 영향을 받는다.

* 자산군
* 계약 만기
* 변동성
* 상계 효과
* 담보

---

# 10. Alpha

Alpha는 Basel 규제에서 정의한 보정계수이다.

SA-CCR는 RC와 PFE를 단순 합산하지 않고 Alpha를 적용하여 최종 EAD를 산출한다.

Alpha는 규제기관이 정의한 보수적 계수이며 위험 과소평가를 방지하는 역할을 한다.

---

# 11. Netting and Collateral

SA-CCR는 다음 요소를 적극 반영한다.

* 법적 상계(Netting Agreement)
* Variation Margin
* Initial Margin
* 현금 담보
* 증권 담보

이는 기존 CEM 대비 큰 개선 사항이다.

---

# 12. Relationship with Other Frameworks

| Framework     | Relationship                     |
| ------------- | -------------------------------- |
| IFRS 9        | SA-CCR EAD는 일부 신용위험 평가에 활용될 수 있음 |
| Basel III IRB | SA-CCR 산출 EAD를 규제자본 계산에 활용       |
| CVA           | SA-CCR 노출액을 기반으로 CVA 위험 측정       |
| FRTB          | 시장위험과 거래상대방 신용위험을 상호 보완          |

---

# 13. FRKP Bundle Relationship

```text
Bundle-001
Basel III
      │
      ▼
Bundle-002
FRTB
      │
      ▼
Bundle-003
IFRS 9
      │
      ▼
Bundle-004
SA-CCR
      │
      ├──────────────┐
      ▼              ▼
Bundle-005      Bundle-006
IRB             CVA
```

---

# 14. Related Documents

| Category       | Document                         |
| -------------- | -------------------------------- |
| Knowledge      | [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md) Counterparty Credit Risk  |
| Knowledge      | [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md) SA-CCR Framework          |
| Analysis       | [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md) Why CEM Failed            |
| Formula        | [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md) Replacement Cost          |
| Formula        | [FC-442](../../04_Formula_Catalog/04_SA_CCR/FC-442_POTENTIAL_FUTURE_EXPOSURE.md) Potential Future Exposure |
| Formula        | [FC-443](../../04_Formula_Catalog/04_SA_CCR/FC-443_ALPHA.md) Alpha                     |
| Formula        | [FC-444](../../04_Formula_Catalog/04_SA_CCR/FC-444_SA_CCR_EAD.md) SA-CCR EAD                |
| Implementation | [IMP-441](../../06_Implementation_Guide/04_SA_CCR/IMP-441_SA_CCR_IMPLEMENTATION.md) SA-CCR Implementation    |
| Architecture   | [ARCH-741](../../07_Architecture/04_SA_CCR/ARCH-741_SA_CCR_ARCHITECTURE.md) SA-CCR Architecture     |

---

# 15. Learning Path

```text
RL-140 SA-CCR Overview
        │
        ▼
KB-241 Counterparty Credit Risk
        │
        ▼
AN-241 Why CEM Failed
        │
        ▼
KB-242 SA-CCR Framework
        │
        ▼
FC-441 Replacement Cost
        │
        ▼
FC-442 Potential Future Exposure
        │
        ▼
FC-443 Alpha
        │
        ▼
FC-444 SA-CCR EAD
        │
        ▼
IMP-441 SA-CCR Implementation
        │
        ▼
ARCH-741 SA-CCR Architecture
```

---

# 16. Summary

SA-CCR(Standardised Approach for Counterparty Credit Risk)는 Basel III에서 정의한 거래상대방 신용위험 측정 표준 접근법이다.

기존 CEM의 한계를 개선하기 위해 도입되었으며, Replacement Cost, Potential Future Exposure, Alpha를 결합하여 보다 위험 민감한 Exposure at Default를 산출한다.

FRKP에서는 SA-CCR를 거래상대방 신용위험 관리의 핵심 프레임워크로 정의하며, 이후 Formula, Implementation, Architecture 문서를 통해 계산 방법과 시스템 설계를 단계적으로 설명한다.

---

# 17. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
