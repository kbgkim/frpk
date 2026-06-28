# FC-431 — Probability of Default (PD)

---

# Document Information

| Item            | Value                  |
| --------------- | ---------------------- |
| Document ID     | FC-431                 |
| Document Name   | Probability of Default |
| Version         | 1.0.0                  |
| Status          | Draft                  |
| Category        | Formula Catalog        |
| Parent Document | KB-232                 |
| Created         | 2026-06-26             |
| Last Updated    | 2026-06-26             |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Formula Catalog](../README.md) > [FC-431 — Probability of Default (PD)](FC-431_PROBABILITY_OF_DEFAULT.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-432](FC-432_LOSS_GIVEN_DEFAULT.md) |

### Related Documents

- [FC-432](FC-432_LOSS_GIVEN_DEFAULT.md)
- [FC-433](FC-433_EXPOSURE_AT_DEFAULT.md)
- [FC-434](FC-434_EXPECTED_CREDIT_LOSS.md)
- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Probability of Default(PD)** 의 개념, 수학적 정의, 업무적 의미, 계산 모델 및 시스템 구현 관점을 설명한다.

PD는 신용위험 모델의 가장 핵심적인 입력 변수이며, IFRS 9 Expected Credit Loss(ECL), Basel III Internal Ratings-Based(IRB) Approach, 내부 신용평가모형 및 스트레스 테스트에서 공통적으로 사용된다.

FRKP에서는 PD를 **신용 품질(Credit Quality)을 시간에 따라 정량화하는 확률 모델**로 정의한다.

---

# 2. Business Purpose

금융기관은 대출이나 채권을 보유할 때 가장 먼저 다음 질문에 답해야 한다.

> **"이 차주가 일정 기간 안에 부도날 가능성은 얼마나 되는가?"**

이 질문에 대한 정량적 답이 PD이다.

PD는 단순한 과거 통계가 아니라 **현재의 신용상태와 미래 전망을 반영한 부도 가능성**을 나타낸다.

---

# 3. Regulatory Perspective

PD는 다음 규제 및 회계 체계에서 공통적으로 활용된다.

| Framework       | Usage                   |
| --------------- | ----------------------- |
| IFRS 9          | Expected Credit Loss 계산 |
| Basel III IRB   | Credit RWA 계산           |
| Stress Testing  | 경기 악화 시 부도율 추정          |
| ICAAP           | 자본 적정성 평가               |
| Internal Rating | 내부등급 산정                 |

---

# 4. Mathematical Definition

PD는 일정 기간 내에 차주가 부도(Default)에 이를 확률이다.

일반적으로 다음과 같이 정의한다.

[
PD(T)=P(\text{Default within }T)
]

여기서

* **PD(T)** : 기간 (T) 동안의 부도확률
* **Default** : 계약상 의무를 이행하지 못하는 상태
* **T** : 관측 기간(예: 12개월, Lifetime)

---

# 5. Time Horizon

PD는 관측 기간에 따라 구분된다.

| Type                       | Description        |
| -------------------------- | ------------------ |
| 12-Month PD                | 향후 12개월 부도확률       |
| Lifetime PD                | 금융자산 만기까지의 누적 부도확률 |
| Point-in-Time (PIT) PD     | 현재 경제 상황을 반영한 PD   |
| Through-the-Cycle (TTC) PD | 경기 변동을 평균화한 장기 PD  |

---

# 6. Business Example

기업 A의 내부등급이 **BBB**이고, 내부모형에서 다음과 같이 산출되었다고 가정한다.

| 항목              |    값 |
| --------------- | ---: |
| Internal Rating |  BBB |
| 12-Month PD     | 1.8% |
| Lifetime PD     | 7.6% |

이는 향후 1년 동안 약 1.8%의 확률로 부도가 발생할 것으로 추정된다는 의미이다.

---

# 7. PD Estimation Process

```text
Borrower Information
        │
        ▼
Credit Assessment
        │
        ▼
Internal Rating
        │
        ▼
PD Model
        │
        ▼
Probability of Default
```

---

# 8. Typical Input Variables

PD 모델은 다양한 정보를 활용한다.

| Input | Description          |
| ----- | -------------------- |
| 재무비율  | 부채비율, 유동비율, 이자보상배율 등 |
| 거래정보  | 연체, 한도 사용률, 거래기간     |
| 신용등급  | 내부·외부 등급             |
| 담보정보  | 담보 유형 및 가치           |
| 거시경제  | GDP, 금리, 실업률 등       |
| 산업정보  | 산업별 위험도              |

---

# 9. Relationship with ECL

PD는 Expected Credit Loss의 첫 번째 입력 변수이다.

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

PD가 증가하면 동일한 조건에서 ECL도 증가한다.

---

# 10. Relationship with Basel III

Basel III IRB에서는 PD를 이용하여 규제자본을 계산한다.

```text
PD
      │
      ▼
Risk Weight Function
      │
      ▼
Credit RWA
      │
      ▼
Regulatory Capital
```

IFRS 9는 손상충당금 계산을 위해, Basel III는 규제자본 계산을 위해 PD를 사용한다.

---

# 11. Input Contract

| Input                   | Description |
| ----------------------- | ----------- |
| Borrower Information    | 차주 정보       |
| Financial Information   | 재무정보        |
| Rating Information      | 신용등급        |
| Macroeconomic Variables | 거시경제 변수     |
| Observation Horizon     | 관측 기간       |

---

# 12. Computation Contract

```text
Borrower Data
      │
      ▼
Validation
      │
      ▼
Feature Engineering
      │
      ▼
PD Model
      │
      ▼
Calibration
      │
      ▼
Probability of Default
```

PD 계산은 모델 종류(Logistic Regression, Scorecard, Machine Learning 등)와 무관하게 동일한 계약을 따른다.

---

# 13. Output Contract

| Output       | Description |
| ------------ | ----------- |
| 12-Month PD  | 12개월 부도확률   |
| Lifetime PD  | 만기까지의 부도확률  |
| Rating Grade | 내부등급        |
| PD Band      | PD 구간       |

---

# 14. Formula Engine Model

```text
BorrowerValidator
        │
        ▼
FeatureExtractor
        │
        ▼
PDModel
        │
        ▼
PDCalibrator
        │
        ▼
ProbabilityOfDefault
```

Formula Engine은 PD 계산 결과만 제공하며, Stage 분류 및 ECL 계산은 상위 계층에서 수행한다.

---

# 15. Implementation Considerations

구현 시 고려사항

* PIT와 TTC PD를 구분하여 관리한다.
* 모델과 Calibration을 분리한다.
* Feature Engineering을 독립 모듈로 구현한다.
* 버전 관리(Model Versioning)를 지원한다.
* 입력 데이터 품질 검증을 선행한다.

---

# 16. Performance Considerations

대량 포트폴리오 계산에서는 다음을 고려한다.

* 배치 기반 병렬 추론
* Feature 캐싱
* 동일 차주 재사용
* 모델 로딩 최적화
* 벡터화 연산

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
Borrower
      │
      ▼
Credit Assessment
      │
      ▼
Internal Rating
      │
      ▼
Probability of Default
      │
      ▼
Expected Credit Loss
      │
      ▼
Provision / Credit RWA
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

Probability of Default는 일정 기간 내 차주가 부도에 이를 가능성을 나타내는 핵심 신용위험 지표이다.

IFRS 9에서는 Expected Credit Loss 계산의 입력으로 사용되며, Basel III에서는 Credit RWA 산정의 핵심 변수로 활용된다.

FRKP에서는 PD를 **차주 정보 → 신용평가 → 내부등급 → 확률 추정 → Calibration**으로 이어지는 독립적인 계산 계약으로 정의한다. Formula Engine은 PD를 산출하고, 상위 계층에서는 Stage 분류, ECL 계산 및 규제자본 산정에 이를 활용한다.

---

# 21. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
