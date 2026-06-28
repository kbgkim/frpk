# KB-231 — Credit Risk Overview

---

# Document Information

| Item            | Value                |
| --------------- | -------------------- |
| Document ID     | KB-231               |
| Document Name   | Credit Risk Overview |
| Version         | 1.0.0                |
| Status          | Draft                |
| Category        | Knowledge Base       |
| Parent Document | KB-201               |
| Created         | 2026-06-26           |
| Last Updated    | 2026-06-26           |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Knowledge Base](../README.md) > [KB-231 — Credit Risk Overview](KB-231_CREDIT_RISK_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | [KB-232](KB-232_IFRS9_FRAMEWORK.md) |

### Related Documents

- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-232](KB-232_IFRS9_FRAMEWORK.md)
- [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)
- [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)
- [FC-432](../../04_Formula_Catalog/03_IFRS9/FC-432_LOSS_GIVEN_DEFAULT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 금융기관이 직면하는 **신용위험(Credit Risk)** 의 개념, 발생 원인, 구성 요소 및 관리 체계를 설명하는 Knowledge Base 문서이다.

신용위험은 IFRS 9 Expected Credit Loss(ECL), Basel III Credit Risk, 내부 신용등급(IRB), 리스크 관리 시스템의 기반이 되는 핵심 위험 유형이다.

본 문서는 신용위험의 본질과 전체 구조를 설명하며, 이후 Formula Catalog와 Architecture Guide의 기반 지식을 제공한다.

---

# 2. What is Credit Risk?

신용위험(Credit Risk)은 **거래상대방(Counterparty)이 계약상 의무를 이행하지 못함으로써 금융기관이 손실을 입을 가능성**을 의미한다.

그러나 현대 금융에서는 신용위험을 단순한 **부도(Default)** 의 가능성으로만 보지 않는다.

신용등급 하락, 신용스프레드 확대, 담보가치 하락, 거래상대방의 재무상태 악화 등 **신용 품질(Credit Quality)의 변화**도 신용위험의 중요한 요소이다.

---

# 3. Business Perspective

은행은 다양한 형태의 신용 익스포저를 보유한다.

* 기업대출
* 개인대출
* 회사채
* 국채
* 지급보증
* 신용공여 약정
* 파생상품 거래
* 무역금융

이러한 거래는 모두 거래상대방의 신용상태 변화에 영향을 받는다.

신용위험 관리의 목적은 손실을 완전히 제거하는 것이 아니라 **예상 가능한 손실(Expected Loss)을 측정하고, 예상하지 못한 손실(Unexpected Loss)에 대비하는 것**이다.

---

# 4. Credit Risk Drivers

신용위험은 여러 요인의 영향을 받는다.

| Risk Driver                 | Description |
| --------------------------- | ----------- |
| Probability of Default (PD) | 부도확률        |
| Loss Given Default (LGD)    | 부도 시 손실률    |
| Exposure at Default (EAD)   | 부도 시 익스포저   |
| Credit Rating               | 신용등급        |
| Credit Spread               | 신용스프레드      |
| Collateral                  | 담보          |
| Guarantee                   | 보증          |
| Industry & Economy          | 산업 및 거시경제   |

이 요소들은 신용손실의 규모와 발생 가능성을 결정한다.

---

# 5. Credit Risk Framework

```text
Borrower
      │
      ▼
Credit Quality
      │
      ▼
PD
LGD
EAD
      │
      ▼
Expected Loss
      │
      ▼
Unexpected Loss
```

신용위험은 차주의 신용상태를 정량화하고, 이를 손실 계산으로 연결하는 과정이다.

---

# 6. Credit Risk Management Process

일반적인 신용위험 관리 절차는 다음과 같다.

```text
Customer Information
        │
        ▼
Credit Assessment
        │
        ▼
Internal Rating
        │
        ▼
PD / LGD / EAD
        │
        ▼
Expected Credit Loss
        │
        ▼
Capital & Provision
```

---

# 7. Expected Loss vs Unexpected Loss

신용손실은 크게 두 가지로 구분된다.

| Type                 | Description          |
| -------------------- | -------------------- |
| Expected Loss (EL)   | 정상적인 영업 과정에서 예상되는 손실 |
| Unexpected Loss (UL) | 예상 범위를 초과하는 손실       |

Expected Loss는 주로 **IFRS 9**에서 회계상 손상충당금 계산에 사용되며,

Unexpected Loss는 **Basel III**에서 규제자본 산정의 핵심 개념이다.

---

# 8. Relationship with IFRS 9

```text
Credit Risk
      │
      ▼
Stage Assessment
      │
      ▼
PD / LGD / EAD
      │
      ▼
Expected Credit Loss
      │
      ▼
Impairment Allowance
```

IFRS 9는 신용위험 증가 정도를 평가하여 Stage를 결정하고, 이에 따라 12개월 ECL 또는 Lifetime ECL을 계산한다.

---

# 9. Relationship with Basel III

```text
Credit Risk
      │
      ▼
PD / LGD / EAD
      │
      ▼
Risk Weight
      │
      ▼
Credit RWA
      │
      ▼
Regulatory Capital
```

Basel III는 동일한 신용위험 정보를 활용하지만, 목적은 회계가 아니라 규제자본 산정이다.

---

# 10. Relationship between IFRS 9 and Basel III

| IFRS 9        | Basel III       |
| ------------- | --------------- |
| 회계 기준         | 건전성 규제          |
| Expected Loss | Unexpected Loss |
| 손상충당금         | 자기자본            |
| 재무제표          | 규제자본비율          |
| ECL           | Credit RWA      |

두 체계는 목적은 다르지만 PD, LGD, EAD 등의 핵심 데이터를 공유한다.

---

# 11. Relationship with FRKP

| Topic                    | Related Document |
| ------------------------ | ---------------- |
| IFRS 9                   | [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)           |
| Financial Risk           | [KB-201](../01_Basel_III/KB-201_FINANCIAL_RISK_OVERVIEW.md)           |
| IFRS 9 Framework         | [KB-232](KB-232_IFRS9_FRAMEWORK.md)           |
| Why Incurred Loss Failed | [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)           |
| Probability of Default   | [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)           |
| Loss Given Default       | [FC-432](../../04_Formula_Catalog/03_IFRS9/FC-432_LOSS_GIVEN_DEFAULT.md)           |
| Exposure at Default      | [FC-433](../../04_Formula_Catalog/03_IFRS9/FC-433_EXPOSURE_AT_DEFAULT.md)           |
| Expected Credit Loss     | [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)           |
| IFRS 9 Architecture      | [ARCH-731](../../07_Architecture/03_IFRS9/ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)         |

---

# 12. Practical Example

은행이 기업 A에 100억 원을 대출했다고 가정한다.

* 부도확률(PD): 2%
* 부도 시 손실률(LGD): 40%
* 부도 시 익스포저(EAD): 100억 원

Expected Loss는 다음 요소들의 결합으로 계산된다.

```text
PD
 ×
LGD
 ×
EAD
      │
      ▼
Expected Credit Loss
```

이 계산은 이후 Formula Catalog에서 상세히 다룬다.

---

# 13. Knowledge Graph

```text
Financial Risk
        │
        ▼
Credit Risk
        │
        ├── Credit Quality
        ├── Credit Rating
        ├── PD
        ├── LGD
        ├── EAD
        ├── Expected Loss
        └── Unexpected Loss
```

---

# 14. Learning Path

```text
RL-130 IFRS 9 Overview
        │
        ▼
KB-231 Credit Risk Overview
        │
        ▼
AN-231 Why Incurred Loss Failed
        │
        ▼
KB-232 IFRS 9 Framework
        │
        ▼
FC-431 Probability of Default
        │
        ▼
FC-432 Loss Given Default
        │
        ▼
FC-433 Exposure at Default
        │
        ▼
FC-434 Expected Credit Loss
        │
        ▼
IMP-431 Expected Credit Loss Implementation
        │
        ▼
ARCH-731 IFRS 9 Calculation Architecture
```

---

# 15. Summary

신용위험은 거래상대방의 의무 불이행뿐 아니라 신용 품질의 변화로 인해 발생하는 손실 가능성을 의미한다.

현대 금융에서는 신용위험을 **Credit Quality → PD/LGD/EAD → Expected Loss → Unexpected Loss**로 이어지는 통합적인 관리 체계로 이해한다.

FRKP에서는 신용위험을 단순한 부도 위험이 아니라 **회계(IFRS 9)와 규제자본(Basel III)을 연결하는 핵심 데이터 모델**로 정의하며, PD·LGD·EAD를 공통 기반으로 활용하는 통합 Credit Risk Framework를 제시한다.

---

# 16. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
