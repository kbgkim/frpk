# IMP-441 — SA-CCR Implementation Guide

---

# Document Information

| Item            | Value                       |
| --------------- | --------------------------- |
| Document ID     | IMP-441                     |
| Document Name   | SA-CCR Implementation Guide |
| Version         | 1.0.0                       |
| Status          | Draft                       |
| Category        | Implementation Guide        |
| Parent Document | FC-444                      |
| Created         | 2026-06-26                  |
| Last Updated    | 2026-06-26                  |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Implementation Guide](../README.md) > [IMP-441 — SA-CCR Implementation Guide](IMP-441_SA_CCR_IMPLEMENTATION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Implementation Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
- [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)
- [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)
- [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 SA-CCR(Standardised Approach for Counterparty Credit Risk)의 계산 과정을 실제 시스템에서 구현하기 위한 실행 절차와 구현 원칙을 정의한다.

본 문서는 Formula Catalog에서 정의한 계산식을 실행 가능한 처리 단계로 변환하며, 코드 구현이 아니라 **계산 파이프라인(Processing Pipeline)** 과 **모듈 간 책임 분리**를 설명하는 것을 목적으로 한다.

---

# 2. Implementation Scope

본 문서는 다음 Formula Catalog를 구현 대상으로 한다.

| Formula | Description               |
| ------- | ------------------------- |
| FC-441  | Replacement Cost          |
| FC-442  | Potential Future Exposure |
| FC-443  | Alpha                     |
| FC-444  | Exposure at Default       |

---

# 3. Processing Pipeline

SA-CCR 계산은 다음 순서로 수행한다.

```text
Trade Portfolio
        │
        ▼
Trade Validation
        │
        ▼
Trade Classification
        │
        ▼
Netting Set Construction
        │
        ▼
Collateral Processing
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Apply Alpha
        │
        ▼
Exposure at Default
```

각 단계는 독립적인 처리 모듈로 구현한다.

---

# 4. Implementation Layers

```text
Input Layer
        │
        ▼
Validation Layer
        │
        ▼
Trade Processing Layer
        │
        ▼
Calculation Layer
        │
        ▼
Aggregation Layer
        │
        ▼
Output Layer
```

각 계층은 하나의 책임만 수행한다.

---

# 5. Input Contract

필수 입력 정보는 다음과 같다.

| Input                  | Description              |
| ---------------------- | ------------------------ |
| Trade Portfolio        | 거래 목록                    |
| Trade Information      | 계약 정보                    |
| Asset Class            | 자산군                      |
| Netting Agreement      | 상계 계약                    |
| Market Value           | 현재 시장가치                  |
| Collateral             | 담보 정보                    |
| Margin Information     | Initial/Variation Margin |
| Supervisory Parameters | 감독 파라미터                  |

---

# 6. Validation Stage

입력 데이터 검증

* Null 검사
* 계약 중복 검사
* 자산군 유효성 검사
* Netting Agreement 존재 여부
* 담보 정보 검증
* 만기 정보 검증
* 감독 파라미터 존재 여부

검증 실패 시 계산을 진행하지 않는다.

---

# 7. Trade Classification

모든 거래를 자산군별로 분류한다.

```text
Trade Portfolio
      │
      ├── Interest Rate
      ├── FX
      ├── Credit
      ├── Equity
      └── Commodity
```

이 단계에서 각 거래는 해당 계산 규칙에 연결된다.

---

# 8. Netting Set Construction

거래를 법적 상계 단위(Netting Set)로 그룹화한다.

```text
Trade
    │
    ▼
Netting Agreement
    │
    ▼
Netting Set
```

이후 계산은 Netting Set 단위로 수행한다.

---

# 9. Collateral Processing

담보 처리 단계에서는 다음을 수행한다.

* 인정 담보 확인
* Variation Margin 반영
* Initial Margin 반영
* 담보 평가
* 인정금액 계산

담보 정보는 Replacement Cost 계산에 사용된다.

---

# 10. Replacement Cost Calculation

Replacement Cost 계산 모듈은 다음 입력을 사용한다.

* Netting Set
* Current Market Value
* Recognized Collateral

출력

* Replacement Cost

RC 계산은 다른 계산과 독립적으로 수행한다.

---

# 11. Potential Future Exposure Calculation

PFE 계산 단계에서는 다음을 수행한다.

```text
Trade
      │
      ▼
Trade Add-on
      │
      ▼
Hedging Set
      │
      ▼
Asset Class Add-on
      │
      ▼
Aggregate Add-on
      │
      ▼
Multiplier
      │
      ▼
Potential Future Exposure
```

PFE 계산은 자산군별 모듈을 분리하여 구현한다.

---

# 12. Alpha Application

Replacement Cost와 Potential Future Exposure를 합산한 후 Alpha를 적용한다.

```text
RC

+

PFE

↓

Exposure Before Alpha

↓

Alpha

↓

Exposure at Default
```

Alpha는 외부 규제 파라미터를 사용한다.

---

# 13. Output Generation

최종 출력

| Output                    | Description |
| ------------------------- | ----------- |
| Replacement Cost          | 현재 노출       |
| Potential Future Exposure | 미래 노출       |
| Exposure Before Alpha     | Alpha 적용 전  |
| Exposure at Default       | 최종 노출       |

---

# 14. Module Decomposition

```text
TradeValidator

TradeClassifier

NettingBuilder

CollateralProcessor

ReplacementCostCalculator

PotentialFutureExposureCalculator

AlphaApplier

ExposureAtDefaultCalculator
```

각 모듈은 단일 책임 원칙(Single Responsibility Principle)을 따른다.

---

# 15. Error Handling Strategy

다음 오류를 처리한다.

| Error                      | Handling            |
| -------------------------- | ------------------- |
| Missing Trade Data         | Validation Error    |
| Invalid Asset Class        | Validation Error    |
| Missing Netting Agreement  | Business Error      |
| Invalid Collateral         | Business Error      |
| Missing Supervisory Factor | Configuration Error |

오류는 계산을 중단하고 원인을 명확하게 기록한다.

---

# 16. Performance Strategy

대규모 거래 처리 시 고려사항

* Netting Set 캐싱
* 감독 파라미터 캐싱
* 자산군 병렬 계산
* PFE 병렬 집계
* Incremental Recalculation
* Immutable 계산 객체 사용

---

# 17. Traceability

계산 과정은 모두 추적 가능해야 한다.

```text
Trade
      │
      ▼
Netting Set
      │
      ▼
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

각 단계의 중간 결과를 조회할 수 있어야 한다.

---

# 18. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)           |
| Knowledge      | [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md), [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)   |
| Analysis       | [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)           |
| Formula        | [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md) ~ [FC-444](../../04_Formula_Catalog/04_SA_CCR/FC-444_SA_CCR_EAD.md)  |
| Implementation | [IMP-441](IMP-441_SA_CCR_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-741](../../07_Architecture/04_SA_CCR/ARCH-741_SA_CCR_ARCHITECTURE.md)         |

---

# 19. Knowledge Graph

```text
Trade Portfolio
        │
        ▼
Validation
        │
        ▼
Trade Classification
        │
        ▼
Netting Set
        │
        ▼
Collateral
        │
        ▼
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

---

# 20. Implementation Principles

SA-CCR 구현은 다음 원칙을 따른다.

1. Formula와 Implementation을 분리한다.
2. 계산 순서를 변경하지 않는다.
3. 모듈 간 의존성을 최소화한다.
4. 각 계산 단계는 독립적으로 테스트 가능해야 한다.
5. 규제 파라미터는 외부 설정으로 관리한다.
6. 계산 결과는 재현 가능해야 한다.
7. 모든 중간 산출물은 추적 가능해야 한다.

---

# 21. Summary

SA-CCR 구현은 Formula Catalog에서 정의한 계산식을 **Trade Validation → Trade Classification → Netting → Collateral → Replacement Cost → Potential Future Exposure → Alpha → Exposure at Default**의 실행 파이프라인으로 구현한다.

FRKP에서는 각 계산 단계를 독립적인 모듈로 분리하고, 입력·출력 계약을 명확히 정의하여 재사용성과 테스트 용이성을 확보한다. 이를 통해 규제 변경에 대응 가능한 확장성과 계산 과정의 추적 가능성을 동시에 달성한다.

---

# 22. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
