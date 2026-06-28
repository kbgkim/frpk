# FC-432 — Loss Given Default (LGD)

---

# Document Information

| Item            | Value              |
| --------------- | ------------------ |
| Document ID     | FC-432             |
| Document Name   | Loss Given Default |
| Version         | 1.0.0              |
| Status          | Draft              |
| Category        | Formula Catalog    |
| Parent Document | KB-232             |
| Created         | 2026-06-26         |
| Last Updated    | 2026-06-26         |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Formula Catalog](../README.md) > [FC-432 — Loss Given Default (LGD)](FC-432_LOSS_GIVEN_DEFAULT.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-431](FC-431_PROBABILITY_OF_DEFAULT.md) |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-433](FC-433_EXPOSURE_AT_DEFAULT.md) |

### Related Documents

- [FC-431](FC-431_PROBABILITY_OF_DEFAULT.md)
- [FC-433](FC-433_EXPOSURE_AT_DEFAULT.md)
- [FC-434](FC-434_EXPECTED_CREDIT_LOSS.md)
- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Loss Given Default(LGD)** 의 개념, 수학적 정의, 업무적 의미, 계산 모델 및 시스템 구현 관점을 설명한다.

LGD는 차주가 부도(Default)에 도달한 이후 금융기관이 최종적으로 회수하지 못하는 손실의 비율을 의미하며, IFRS 9 Expected Credit Loss(ECL), Basel III Internal Ratings-Based(IRB) Approach 및 내부 신용위험 모델의 핵심 입력 변수이다.

FRKP에서는 LGD를 **부도 이후 회수 프로세스를 정량화한 경제적 손실률(Economic Loss Rate)** 로 정의한다.

---

# 2. Business Purpose

차주가 부도났다고 해서 대출금 전부를 잃는 것은 아니다.

금융기관은 다음과 같은 방법으로 일부를 회수할 수 있다.

* 담보 처분
* 보증기관 청구
* 채권 회수
* 법적 절차
* 구조조정
* 채무 재조정

LGD는 이러한 회수 절차를 모두 고려한 후 **최종적으로 회수하지 못하는 비율**을 의미한다.

---

# 3. Regulatory Perspective

LGD는 다음 영역에서 사용된다.

| Framework      | Usage                   |
| -------------- | ----------------------- |
| IFRS 9         | Expected Credit Loss 계산 |
| Basel III IRB  | Credit RWA 계산           |
| Stress Testing | 경기 악화 시 회수율 추정          |
| ICAAP          | 경제적 자본 산정               |
| Credit Pricing | 위험기반 가격결정               |

---

# 4. Mathematical Definition

LGD는 일반적으로 다음과 같이 정의한다.

[
LGD
===

## 1

Recovery\ Rate
]

또는

[
LGD
===

\frac{Exposure-Recovery}
{Exposure}
]

여기서

* **Exposure** : 부도 시 익스포저(EAD)
* **Recovery** : 회수금액(담보, 보증, 현금회수 등 포함)

---

# 5. Economic Interpretation

LGD는 단순한 회계 손실이 아니다.

회수 과정에서 발생하는 모든 경제적 요소를 포함한다.

* 담보 할인
* 담보 처분 기간
* 법률 비용
* 회수 비용
* 시장가격 하락
* 할인율(Time Value of Money)

따라서 LGD는 **경제적 손실(Economic Loss)** 을 나타낸다.

---

# 6. Business Example

부도 시 익스포저가

```text
100억 원
```

이고

회수 가능한 금액이

```text
담보 회수     45억
보증 회수     10억
현금 회수      5억
-------------------
총 회수       60억
```

이라면

```text
LGD

=

(100-60)

/100

=

40%
```

이다.

---

# 7. Recovery Components

회수금액은 다양한 요소로 구성된다.

| Component           | Description |
| ------------------- | ----------- |
| Collateral Recovery | 담보 회수       |
| Guarantee Recovery  | 보증 회수       |
| Cash Recovery       | 현금 회수       |
| Workout Recovery    | 채권 회수       |
| Legal Recovery      | 법적 절차 회수    |

---

# 8. Relationship with Collateral

담보는 LGD를 가장 크게 감소시키는 요소이다.

```text
Exposure
      │
      ▼
Collateral Value
      │
      ▼
Haircut
      │
      ▼
Recognized Collateral
      │
      ▼
Recovery
      │
      ▼
LGD
```

담보가 있다고 해서 전액 인정되는 것은 아니다.

---

# 9. Haircut

담보는 시장가격 변동과 유동성을 고려하여 할인(Haircut)된다.

예를 들어

| 항목      |   금액 |
| ------- | ---: |
| 담보 시가   | 100억 |
| Haircut |  20% |
| 인정 담보   |  80억 |

LGD 계산에는 **Haircut이 적용된 담보가치**를 사용한다.

---

# 10. Recovery Rate

Recovery Rate는

[
Recovery\ Rate
==============

\frac{Recovery}
{Exposure}
]

로 정의한다.

Recovery Rate와 LGD는 서로 보완 관계이다.

```text
Recovery Rate

+

LGD

=

100%
```

(실무에서는 할인비용과 회수비용 반영으로 단순 합계와 차이가 발생할 수 있으므로 내부 정책에 따른 정의를 따른다.)

---

# 11. Input Contract

| Input               | Description |
| ------------------- | ----------- |
| Exposure at Default | 부도 시 익스포저   |
| Collateral Value    | 담보가치        |
| Haircut             | 담보 할인율      |
| Guarantee           | 보증 정보       |
| Recovery Cost       | 회수 비용       |
| Discount Rate       | 할인율         |

---

# 12. Computation Contract

```text
EAD
 │
 ▼
Collateral Valuation
 │
 ▼
Haircut
 │
 ▼
Recovery Estimate
 │
 ▼
Recovery Rate
 │
 ▼
Loss Given Default
```

---

# 13. Output Contract

| Output          | Description |
| --------------- | ----------- |
| LGD             |             |
| Recovery Rate   |             |
| Recovery Amount |             |
| Net Loss        |             |

---

# 14. Formula Engine Model

```text
CollateralValuator
        │
        ▼
HaircutApplier
        │
        ▼
RecoveryCalculator
        │
        ▼
LGDCalculator
        │
        ▼
LossGivenDefault
```

Formula Engine은 LGD를 계산하며, ECL 계산은 상위 계층에서 수행한다.

---

# 15. Implementation Considerations

구현 시 고려사항

* 담보 평가 모듈과 LGD 계산을 분리한다.
* Haircut 규칙을 Configuration으로 관리한다.
* 보증과 담보를 독립적으로 평가한다.
* 할인율을 정책 기반으로 관리한다.
* 회수비용과 회수기간을 반영할 수 있도록 확장성을 확보한다.

---

# 16. Performance Considerations

대규모 계산에서는 다음을 고려한다.

* 담보 정보 캐싱
* Haircut 룰 캐싱
* 병렬 담보 평가
* 담보 재사용 최적화
* 대량 포트폴리오 배치 처리

---

# 17. Relationship with FRKP

| Layer          | Related Document               |
| -------------- | ------------------------------ |
| Reference      | [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)                         |
| Knowledge      | [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md), [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)                 |
| Analysis       | [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)                         |
| Formula        | [FC-431](FC-431_PROBABILITY_OF_DEFAULT.md), [FC-432](FC-432_LOSS_GIVEN_DEFAULT.md), [FC-433](FC-433_EXPOSURE_AT_DEFAULT.md), [FC-434](FC-434_EXPECTED_CREDIT_LOSS.md) |
| Implementation | [IMP-431](../../06_Implementation_Guide/03_IFRS9/IMP-431_EXPECTED_CREDIT_LOSS_IMPLEMENTATION.md)                        |
| Architecture   | [ARCH-731](../../07_Architecture/03_IFRS9/ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)                       |

---

# 18. Knowledge Graph

```text
Exposure
      │
      ▼
Collateral
      │
      ▼
Haircut
      │
      ▼
Recovery
      │
      ▼
Recovery Rate
      │
      ▼
Loss Given Default
      │
      ▼
Expected Credit Loss
```

---

# 19. Learning Path

```text
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

# 20. Summary

Loss Given Default는 차주가 부도한 이후 금융기관이 최종적으로 회수하지 못하는 경제적 손실의 비율을 나타낸다.

LGD는 담보, 보증, 회수 절차, 헤어컷, 할인율 및 회수비용을 모두 고려하여 산출되며, Expected Credit Loss와 Basel III Credit Risk 계산의 핵심 입력 변수이다.

FRKP에서는 LGD를 **Exposure → Collateral → Haircut → Recovery → Recovery Rate → Loss Given Default**로 이어지는 독립적인 계산 계약으로 정의한다. Formula Engine은 LGD를 계산하고, 상위 계층에서는 PD 및 EAD와 결합하여 Expected Credit Loss와 Credit RWA 산정에 활용한다.

---

# 21. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
