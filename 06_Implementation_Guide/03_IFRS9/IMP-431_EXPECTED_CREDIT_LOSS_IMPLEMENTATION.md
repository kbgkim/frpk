# IMP-431 — Expected Credit Loss Implementation

---

# Document Information

| Item            | Value                               |
| --------------- | ----------------------------------- |
| Document ID     | IMP-431                             |
| Document Name   | Expected Credit Loss Implementation |
| Version         | 1.0.0                               |
| Status          | Draft                               |
| Category        | Implementation Guide                |
| Parent Document | FC-434                              |
| Created         | 2026-06-26                          |
| Last Updated    | 2026-06-26                          |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Implementation Guide](../README.md) > [IMP-431 — Expected Credit Loss Implementation](IMP-431_EXPECTED_CREDIT_LOSS_IMPLEMENTATION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Implementation Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
- [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)
- [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)
- [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 IFRS 9 Expected Credit Loss(ECL)를 실제 Risk Engine에서 구현하기 위한 실행 구조(Execution Structure)를 정의한다.

본 문서는 Formula를 구현 가능한 계산 파이프라인으로 분해하고, 각 컴포넌트의 책임과 데이터 흐름을 정의하는 것을 목적으로 한다.

Java 구현체가 아니라 **Execution Contract**를 정의하는 문서이다.

---

# 2. Scope

## 포함 범위

* Stage 기반 ECL 계산
* PD, LGD, EAD 통합
* Discount 적용
* Scenario 기반 계산
* Probability-weighted Aggregation
* Validation
* Batch Execution

## 제외 범위

* PD 모델 학습
* LGD 모델 구축
* EAD 모델 구축
* 회계 분개 처리
* UI 및 API

---

# 3. Architecture Position

```text
Credit Assessment
        │
        ▼
Stage Engine
        │
        ▼
Expected Credit Loss Engine
        │
        ▼
Provision Engine
```

Expected Credit Loss Engine은 Stage 결과를 입력으로 받아 ECL을 계산한다.

---

# 4. Processing Pipeline

```text
Input Validation
        │
        ▼
Stage Resolution
        │
        ▼
PD Retrieval
        │
        ▼
LGD Retrieval
        │
        ▼
EAD Retrieval
        │
        ▼
Discount Calculation
        │
        ▼
Scenario Execution
        │
        ▼
Probability-weighted Aggregation
        │
        ▼
Expected Credit Loss Result
```

각 단계는 독립적인 컴포넌트로 구현한다.

---

# 5. Component Model

```text
InputValidator
        │
        ▼
StageResolver
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
ScenarioExecutor
        │
        ▼
ScenarioAggregator
        │
        ▼
ExpectedCreditLossCalculator
```

모든 컴포넌트는 단일 책임(Single Responsibility Principle)을 따른다.

---

# 6. Input Contract

| Input            | Description            |
| ---------------- | ---------------------- |
| Financial Asset  | 금융자산                   |
| Observation Date | 기준일                    |
| Stage            | Stage 1 / 2 / 3        |
| PD               | Probability of Default |
| LGD              | Loss Given Default     |
| EAD              | Exposure at Default    |
| Discount Rate    | 할인율                    |
| Scenario Set     | 경제 시나리오 집합             |

### Validation Rules

* Stage는 유효한 값이어야 한다.
* PD는 0 이상 1 이하이다.
* LGD는 0 이상 1 이하이다.
* EAD는 0 이상이다.
* Scenario Weight의 합은 1이어야 한다.
* Discount Rate는 정책에 따라 검증한다.

---

# 7. Output Contract

| Output               | Description |
| -------------------- | ----------- |
| Expected Credit Loss |             |
| 12-Month ECL         |             |
| Lifetime ECL         |             |
| Applied Stage        |             |
| Scenario Results     |             |
| Discounted Loss      |             |
| Provision Amount     |             |

출력은 Immutable Value Object로 생성한다.

---

# 8. Stage-specific Execution

## Stage 1

```text
12-Month PD

↓

12-Month ECL
```

## Stage 2

```text
Lifetime PD

↓

Lifetime ECL
```

## Stage 3

```text
Lifetime PD

↓

Lifetime ECL

↓

Credit-impaired Processing
```

Implementation은 Stage에 따라 계산 범위만 변경하며 계산 구조는 동일하게 유지한다.

---

# 9. Scenario Execution

```text
Base Scenario
        │
────────┼────────
        ▼
Optimistic
Pessimistic
        │
────────┼────────
        ▼
Scenario Aggregation
```

각 Scenario는 독립적으로 계산된다.

---

# 10. Discount Processing

```text
Future Cash Loss
        │
        ▼
Discount Factor
        │
        ▼
Present Value Loss
```

Discount는 Scenario 계산 이후가 아니라 **Scenario 내부**에서 적용한다.

---

# 11. Runtime State Model

```text
Initialized
      │
      ▼
Validated
      │
      ▼
Stage Determined
      │
      ▼
Risk Factors Loaded
      │
      ▼
Scenario Calculated
      │
      ▼
Aggregated
      │
      ▼
Completed
```

Runtime은 상태를 관리하지만 계산 로직은 포함하지 않는다.

---

# 12. Error Handling

대표 오류

| Error                   | Description |
| ----------------------- | ----------- |
| Invalid Stage           | Stage 오류    |
| Missing PD              | PD 없음       |
| Missing LGD             | LGD 없음      |
| Missing EAD             | EAD 없음      |
| Invalid Scenario Weight | 시나리오 확률 오류  |
| Discount Error          | 할인 계산 오류    |

Fail-Fast 정책을 적용한다.

---

# 13. Parallel Processing

병렬 실행 가능한 영역

```text
Portfolio
     │
─────┼────────────────
     ▼
Asset 1
Asset 2
Asset 3
     │
─────┼────────────────
     ▼
Scenario Execution
     │
─────┼────────────────
     ▼
Aggregation
```

자산 단위와 시나리오 단위 모두 병렬 처리가 가능하다.

---

# 14. Performance Considerations

최적화 대상

* PD 캐싱
* LGD 캐싱
* EAD 캐싱
* Discount Factor 캐싱
* Scenario 병렬 처리
* Batch Streaming
* Incremental Recalculation

---

# 15. Extension Points

향후 확장

* Multi-period ECL
* Dynamic Scenario Generation
* GPU 기반 계산
* Distributed Batch Processing
* Real-time Portfolio Update

---

# 16. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)           |
| Knowledge      | [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md), [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)   |
| Analysis       | [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)           |
| Formula        | [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md) ~ [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)  |
| Implementation | [IMP-431](IMP-431_EXPECTED_CREDIT_LOSS_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-731](../../07_Architecture/03_IFRS9/ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)         |

---

# 17. Knowledge Graph

```text
Stage
      │
      ▼
PD
LGD
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

# 18. Summary

Expected Credit Loss Implementation은 Formula Catalog에서 정의한 ECL 계산 계약을 실행 가능한 처리 파이프라인으로 구현하는 계층이다.

FRKP에서는 ECL 구현을 **Validation → Stage Resolution → PD/LGD/EAD Retrieval → Discount Calculation → Scenario Execution → Probability-weighted Aggregation → Expected Credit Loss Result**의 순차적인 실행 구조로 정의한다.

Implementation Layer는 계산 절차를 담당하며, Formula의 수학적 정의나 Architecture의 오케스트레이션 책임은 포함하지 않는다.

---

# 19. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
