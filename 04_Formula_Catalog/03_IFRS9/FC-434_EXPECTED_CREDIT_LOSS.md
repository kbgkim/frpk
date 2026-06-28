# FC-434 — Expected Credit Loss (ECL)

---

# Document Information

| Item            | Value                |
| --------------- | -------------------- |
| Document ID     | FC-434               |
| Document Name   | Expected Credit Loss |
| Version         | 1.0.0                |
| Status          | Draft                |
| Category        | Formula Catalog      |
| Parent Document | KB-232               |
| Created         | 2026-06-26           |
| Last Updated    | 2026-06-26           |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Formula Catalog](../README.md) > [FC-434 — Expected Credit Loss (ECL)](FC-434_EXPECTED_CREDIT_LOSS.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-433](FC-433_EXPOSURE_AT_DEFAULT.md) |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | None |

### Related Documents

- [FC-431](FC-431_PROBABILITY_OF_DEFAULT.md)
- [FC-432](FC-432_LOSS_GIVEN_DEFAULT.md)
- [FC-433](FC-433_EXPOSURE_AT_DEFAULT.md)
- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Expected Credit Loss(ECL)** 의 개념, 수학적 정의, 업무적 의미, 계산 절차 및 Formula Engine 관점을 설명한다.

Expected Credit Loss는 IFRS 9 손상(Impairment) 모델의 핵심 산식이며, 미래의 신용손실을 현재가치 기준으로 추정하여 금융자산의 손상충당금(Impairment Allowance)을 산출하는 데 사용된다.

FRKP에서는 ECL을 **PD, LGD, EAD, 할인율(Discounting), Stage, 미래 거시경제 시나리오를 통합하는 신용손실 계산 계약(Calculation Contract)** 으로 정의한다.

---

# 2. Business Purpose

금융기관은 대출이 실제 부도난 이후가 아니라 **부도가 발생하기 전에 예상되는 손실을 미리 인식**해야 한다.

Expected Credit Loss는 다음 질문에 대한 정량적 답을 제공한다.

> "현재 보유한 금융자산에서 미래에 발생할 것으로 예상되는 신용손실은 얼마인가?"

이를 통해

* 재무제표의 신뢰성 향상
* 손실의 조기 인식
* 신용위험 변화의 적시 반영
* 경기변동에 대한 선제 대응

이 가능해진다.

---

# 3. Regulatory Perspective

IAS 39는 발생손실(Incurred Loss) 모형을 사용하였다.

IFRS 9는 이를 Expected Credit Loss 모형으로 대체하였다.

| IAS 39        | IFRS 9               |
| ------------- | -------------------- |
| Incurred Loss | Expected Credit Loss |
| 과거 사건 중심      | 미래 전망 포함             |
| 손상사건 발생 후 인식  | 예상 손실 선제 인식          |
| 단일 손상 접근      | Stage 기반 접근          |

---

# 4. Mathematical Definition

가장 기본적인 Expected Credit Loss는 다음과 같이 표현된다.

[
ECL = PD \times LGD \times EAD
]

실제 IFRS 9에서는 다음 요소를 함께 반영한다.

[
ECL
===

\sum_{t}
PD_t
\times
LGD_t
\times
EAD_t
\times
DF_t
\times
ScenarioWeight_t
]

여기서

* **PD** : Probability of Default
* **LGD** : Loss Given Default
* **EAD** : Exposure at Default
* **DF** : Discount Factor
* **ScenarioWeight** : 시나리오 확률 가중치

---

# 5. Formula Interpretation

```text
Credit Risk
      │
      ▼
PD
      │
      ▼
LGD
      │
      ▼
EAD
      │
      ▼
Discounting
      │
      ▼
Scenario Weight
      │
      ▼
Expected Credit Loss
```

각 요소는 서로 독립적인 모델에서 계산되며, ECL은 이들을 통합하는 최종 산식이다.

---

# 6. Stage-based Calculation

IFRS 9는 Stage에 따라 계산 범위가 달라진다.

| Stage   | Credit Condition | Loss Measurement             |
| ------- | ---------------- | ---------------------------- |
| Stage 1 | 정상               | 12-Month ECL                 |
| Stage 2 | SICR 발생          | Lifetime ECL                 |
| Stage 3 | Credit Impaired  | Lifetime ECL (이자수익 인식 방식 변경) |

Stage는 계산 기간(Time Horizon)을 결정한다.

---

# 7. Discounting

Expected Credit Loss는 미래 손실을 현재가치로 할인하여 계산한다.

할인은 일반적으로 유효이자율(Effective Interest Rate, EIR)을 사용한다.

```text
Future Loss
      │
      ▼
Discount Factor
      │
      ▼
Present Value Loss
```

할인율은 시간가치를 반영하기 위한 핵심 요소이다.

---

# 8. Forward-looking Information

IFRS 9는 미래 경제 전망을 반영해야 한다.

대표적인 변수는 다음과 같다.

* GDP 성장률
* 금리 수준
* 실업률
* 환율
* 부동산 가격
* 산업 전망

이러한 변수는 PD와 LGD에 영향을 미쳐 최종 ECL을 변화시킨다.

---

# 9. Multiple Scenario Framework

복수 시나리오를 사용하는 경우 계산 흐름은 다음과 같다.

```text
Base Scenario
        │
Optimistic Scenario
        │
Pessimistic Scenario
        │
        ▼
Probability-weighted ECL
```

각 시나리오별 ECL을 계산한 후 발생 확률을 적용하여 최종 Expected Credit Loss를 산출한다.

---

# 10. Relationship between PD, LGD and EAD

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

* PD는 부도 가능성
* LGD는 부도 시 손실률
* EAD는 부도 시 노출금액

을 의미하며, 세 요소가 결합되어 ECL을 구성한다.

---

# 11. Input Contract

| Input            | Description            |
| ---------------- | ---------------------- |
| Stage            | Stage 1 / 2 / 3        |
| PD               | Probability of Default |
| LGD              | Loss Given Default     |
| EAD              | Exposure at Default    |
| Discount Rate    | 할인율                    |
| Scenario         | 경제 시나리오                |
| Observation Date | 기준일                    |

---

# 12. Computation Contract

```text
Credit Risk Assessment
        │
        ▼
Stage Classification
        │
        ▼
PD
        │
        ▼
LGD
        │
        ▼
EAD
        │
        ▼
Discounting
        │
        ▼
Scenario Weighting
        │
        ▼
Expected Credit Loss
```

모든 단계는 독립적인 계산 계약을 가지며 순차적으로 결합된다.

---

# 13. Output Contract

| Output               | Description |
| -------------------- | ----------- |
| Expected Credit Loss | 예상신용손실      |
| 12-Month ECL         | 12개월 ECL    |
| Lifetime ECL         | 만기 ECL      |
| Provision Amount     | 손상충당금       |
| Stage                | 적용 Stage    |

---

# 14. Formula Engine Model

```text
StageClassifier
        │
        ▼
PDProvider
        │
        ▼
LGDProvider
        │
        ▼
EADProvider
        │
        ▼
DiscountCalculator
        │
        ▼
ScenarioAggregator
        │
        ▼
ExpectedCreditLossCalculator
```

Formula Engine은 각 구성 요소를 결합하여 Expected Credit Loss를 계산한다.

---

# 15. Implementation Considerations

구현 시 고려사항

* Stage 계산과 ECL 계산을 분리한다.
* PD·LGD·EAD를 독립 서비스로 유지한다.
* Discount 계산을 별도 컴포넌트로 구현한다.
* Scenario 처리를 독립 모듈로 분리한다.
* 모든 계산 결과는 Immutable Value Object로 관리한다.
* 규제 파라미터는 Configuration으로 관리한다.

---

# 16. Performance Considerations

대규모 포트폴리오 계산에서는 다음을 고려한다.

* Stage별 병렬 계산
* Scenario 병렬 처리
* PD/LGD/EAD 캐싱
* 벡터화 계산
* Streaming Aggregation
* Incremental Recalculation

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
Credit Risk
      │
      ▼
Stage
      │
      ▼
PD
      │
      ▼
LGD
      │
      ▼
EAD
      │
      ▼
Discount
      │
      ▼
Scenario
      │
      ▼
Expected Credit Loss
      │
      ▼
Provision
```

---

# 19. Learning Path

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
        ├── FC-431 Probability of Default
        ├── FC-432 Loss Given Default
        ├── FC-433 Exposure at Default
        └── FC-434 Expected Credit Loss
                 │
                 ▼
IMP-431 Expected Credit Loss Implementation
                 │
                 ▼
ARCH-731 IFRS 9 Calculation Architecture
```

---

# 20. Summary

Expected Credit Loss는 IFRS 9 손상모형의 핵심 산식으로, 미래의 신용손실을 현재가치 기준으로 추정하여 금융자산의 손상충당금을 산출한다.

ECL은 단순한 **PD × LGD × EAD** 공식이 아니라, **Stage 분류, 할인율, 미래 거시경제 정보, 복수 시나리오를 포함한 통합 신용위험 모델**이다.

FRKP에서는 ECL을 **Credit Risk Assessment → Stage → PD → LGD → EAD → Discounting → Scenario Weighting → Expected Credit Loss**로 이어지는 계산 계약으로 정의한다. Formula Engine은 이 계산 계약을 구현하며, 상위 계층에서는 회계 처리와 시스템 오케스트레이션을 담당한다.

---

# 21. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
