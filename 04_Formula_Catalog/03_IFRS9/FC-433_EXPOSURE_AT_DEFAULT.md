# FC-433 — Exposure at Default (EAD)

---

# Document Information

| Item            | Value               |
| --------------- | ------------------- |
| Document ID     | FC-433              |
| Document Name   | Exposure at Default |
| Version         | 1.0.0               |
| Status          | Draft               |
| Category        | Formula Catalog     |
| Parent Document | KB-232              |
| Created         | 2026-06-26          |
| Last Updated    | 2026-06-26          |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Formula Catalog](../README.md) > [FC-433 — Exposure at Default (EAD)](FC-433_EXPOSURE_AT_DEFAULT.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-432](FC-432_LOSS_GIVEN_DEFAULT.md) |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-434](FC-434_EXPECTED_CREDIT_LOSS.md) |

### Related Documents

- [FC-431](FC-431_PROBABILITY_OF_DEFAULT.md)
- [FC-432](FC-432_LOSS_GIVEN_DEFAULT.md)
- [FC-434](FC-434_EXPECTED_CREDIT_LOSS.md)
- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Exposure at Default(EAD)** 의 개념, 수학적 정의, 업무적 의미, 계산 모델 및 시스템 구현 관점을 설명한다.

EAD는 차주가 부도(Default)에 도달하는 시점에서 금융기관이 실제로 위험에 노출되어 있는 금액을 의미하며, IFRS 9 Expected Credit Loss(ECL), Basel III Internal Ratings-Based(IRB) Approach, SA-CCR 및 내부 신용위험 모델의 핵심 입력 변수이다.

FRKP에서는 EAD를 **부도 시점의 경제적 익스포저(Economic Exposure at the Time of Default)** 로 정의한다.

---

# 2. Business Purpose

금융기관이 100억 원의 한도를 승인했다고 해서 항상 100억 원의 위험을 부담하는 것은 아니다.

예를 들어,

* 승인한도 : 100억 원
* 현재 사용액 : 60억 원
* 미사용 한도 : 40억 원

차주가 부도 직전에 추가로 한도를 사용할 수 있다면 실제 손실 위험은 현재 잔액보다 커질 수 있다.

따라서 EAD는 **현재 잔액이 아니라 부도 시점의 예상 노출금액**을 의미한다.

---

# 3. Regulatory Perspective

EAD는 다음 규제 및 회계 체계에서 활용된다.

| Framework      | Usage                   |
| -------------- | ----------------------- |
| IFRS 9         | Expected Credit Loss 계산 |
| Basel III IRB  | Credit RWA 계산           |
| SA-CCR         | 파생상품 익스포저 계산            |
| Stress Testing | 시나리오별 익스포저 추정           |
| ICAAP          | 경제적 자본 산정               |

---

# 4. Mathematical Definition

가장 단순한 경우 EAD는 다음과 같이 표현할 수 있다.

[
EAD = Outstanding\ Balance
]

그러나 미사용 약정이 존재하는 경우에는 다음과 같이 확장된다.

[
EAD
===

Outstanding
+
CCF \times Undrawn\ Commitment
]

여기서

* **Outstanding** : 현재 사용 중인 잔액
* **Undrawn Commitment** : 미사용 약정
* **CCF (Credit Conversion Factor)** : 신용환산계수

---

# 5. Economic Interpretation

EAD는 현재 시점의 회계 장부금액이 아니라 **부도 시점에 실제로 회수 위험에 노출될 금액**을 나타낸다.

따라서 다음 요소가 반영될 수 있다.

* 현재 대출잔액
* 미사용 약정
* 지급보증
* 신용공여
* 파생상품 익스포저
* 발생이자
* 미수수익

---

# 6. Business Example

기업 A에 다음과 같은 여신이 있다고 가정한다.

| 항목     |     금액 |
| ------ | -----: |
| 승인 한도  | 100억 원 |
| 사용 잔액  |  60억 원 |
| 미사용 한도 |  40억 원 |
| CCF    |    75% |

EAD는 다음과 같이 계산된다.

```text
EAD

=

60

+

40 × 75%

=

90억 원
```

부도 시점에는 현재 잔액보다 더 큰 익스포저가 발생할 수 있다.

---

# 7. Credit Conversion Factor (CCF)

CCF는 미사용 약정 중 실제 익스포저로 전환될 것으로 예상되는 비율이다.

|  CCF | 의미        |
| ---: | --------- |
|   0% | 전환 없음     |
|  50% | 절반 사용 예상  |
|  75% | 대부분 사용 예상 |
| 100% | 전액 사용 예상  |

CCF는 상품 유형과 규제 기준에 따라 달라질 수 있다.

---

# 8. Relationship with Loan Products

상품 유형에 따라 EAD 계산 방식이 달라질 수 있다.

| Product          | EAD Characteristics |
| ---------------- | ------------------- |
| Term Loan        | 현재 잔액 중심            |
| Revolving Credit | CCF 적용              |
| Credit Card      | 사용액 + 미사용 한도        |
| Guarantee        | 보증금액 기준             |
| Letter of Credit | 약정금액 기준             |
| Derivatives      | SA-CCR 방식 적용        |

---

# 9. Relationship with SA-CCR

파생상품의 경우 EAD는 SA-CCR(Standardized Approach for Counterparty Credit Risk)을 통해 계산한다.

```text
Derivative Contract
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
SA-CCR Exposure
        │
        ▼
EAD
```

FRKP에서는 파생상품 EAD를 별도의 Bundle에서 상세히 다룬다.

---

# 10. Relationship with ECL

EAD는 Expected Credit Loss의 세 번째 핵심 요소이다.

```text
PD
 │
 ├────────────┐
 ▼            ▼
LGD          EAD
      │
      ▼
Expected Credit Loss
```

PD는 부도 가능성을,

LGD는 손실률을,

EAD는 손실 규모를 결정한다.

---

# 11. Input Contract

| Input                    | Description |
| ------------------------ | ----------- |
| Outstanding Balance      | 현재 잔액       |
| Credit Limit             | 승인 한도       |
| Undrawn Commitment       | 미사용 약정      |
| Credit Conversion Factor | 신용환산계수      |
| Product Type             | 상품 유형       |

---

# 12. Computation Contract

```text
Outstanding Balance
        │
        ▼
Undrawn Commitment
        │
        ▼
Credit Conversion Factor
        │
        ▼
Exposure Estimation
        │
        ▼
Exposure at Default
```

---

# 13. Output Contract

| Output           | Description |
| ---------------- | ----------- |
| EAD              | 부도 시 익스포저   |
| Drawn Exposure   | 사용 익스포저     |
| Undrawn Exposure | 미사용 익스포저    |
| Total Exposure   | 총 익스포저      |

---

# 14. Formula Engine Model

```text
ExposureCollector
        │
        ▼
CommitmentAnalyzer
        │
        ▼
CCFCalculator
        │
        ▼
ExposureEstimator
        │
        ▼
ExposureAtDefault
```

Formula Engine은 EAD를 계산하며, ECL 계산은 상위 계층에서 수행한다.

---

# 15. Implementation Considerations

구현 시 고려사항

* 상품 유형별 EAD 계산 전략을 분리한다.
* CCF를 Configuration으로 관리한다.
* 대출, 약정, 보증, 파생상품을 공통 인터페이스로 모델링한다.
* 발생이자 및 미수수익 포함 여부를 정책으로 관리한다.
* IFRS 9와 Basel III의 계산 목적 차이를 고려하여 확장성을 확보한다.

---

# 16. Performance Considerations

대규모 계산에서는 다음을 고려한다.

* 약정 정보 캐싱
* CCF 룰 캐싱
* 상품 유형별 병렬 계산
* 동일 고객 익스포저 집계 최적화
* 배치 처리 시 메모리 사용량 최적화

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
Credit Facility
        │
        ▼
Outstanding Balance
        │
        ▼
Undrawn Commitment
        │
        ▼
Credit Conversion Factor
        │
        ▼
Exposure at Default
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

Exposure at Default는 차주가 부도에 도달하는 시점에서 금융기관이 실제로 위험에 노출되어 있는 경제적 익스포저를 나타낸다.

EAD는 현재 잔액뿐 아니라 미사용 약정, 신용환산계수(CCF), 지급보증 및 파생상품 익스포저 등을 반영하여 산출되며, IFRS 9의 Expected Credit Loss와 Basel III의 Credit RWA 계산에 공통적으로 사용되는 핵심 입력 변수이다.

FRKP에서는 EAD를 **Outstanding Balance → Undrawn Commitment → Credit Conversion Factor → Exposure Estimation → Exposure at Default**로 이어지는 독립적인 계산 계약으로 정의한다. Formula Engine은 EAD를 산출하고, 상위 계층에서는 PD 및 LGD와 결합하여 ECL과 규제자본 계산에 활용한다.

---

# 21. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
