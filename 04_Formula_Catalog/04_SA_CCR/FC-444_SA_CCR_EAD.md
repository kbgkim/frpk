# FC-444 — Exposure at Default (SA-CCR)

---

# Document Information

| Item            | Value                        |
| --------------- | ---------------------------- |
| Document ID     | FC-444                       |
| Document Name   | Exposure at Default (SA-CCR) |
| Version         | 1.0.0                        |
| Status          | Draft                        |
| Category        | Formula Catalog              |
| Parent Document | KB-242                       |
| Created         | 2026-06-26                   |
| Last Updated    | 2026-06-26                   |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Formula Catalog](../README.md) > [FC-444 — Exposure at Default (SA-CCR)](FC-444_SA_CCR_EAD.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-443](FC-443_ALPHA.md) |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | None |

### Related Documents

- [FC-441](FC-441_REPLACEMENT_COST.md)
- [FC-442](FC-442_POTENTIAL_FUTURE_EXPOSURE.md)
- [FC-443](FC-443_ALPHA.md)
- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 SA-CCR(Standardised Approach for Counterparty Credit Risk)의 최종 산출물인 **Exposure at Default(EAD)** 의 개념, 수학적 정의, 계산 절차 및 Formula Contract를 정의한다.

Exposure at Default는 거래상대방이 부도하는 시점에 금융기관이 규제 목적상 보유하고 있다고 간주하는 총 신용노출(Regulatory Credit Exposure)을 의미한다.

FRKP에서는 EAD를 **Replacement Cost(RC), Potential Future Exposure(PFE), Alpha를 결합하여 계산하는 최종 규제 노출액**으로 정의한다.

---

# 2. Business Purpose

SA-CCR의 목적은 단순히 현재 손실을 계산하는 것이 아니라, 거래상대방 부도 시 금융기관이 실제로 부담할 것으로 예상되는 노출 규모를 규제 기준에 따라 추정하는 것이다.

Exposure at Default는 다음 업무에서 핵심 입력값으로 사용된다.

* Basel III 규제자본 계산
* Credit Risk RWA 산출
* 거래상대방 신용위험 관리
* CVA(Credit Valuation Adjustment) 계산
* 내부 리스크 한도 관리

---

# 3. Regulatory Perspective

SA-CCR는 현재 노출과 미래 노출을 구분하여 계산한다.

| Component                       | Description |
| ------------------------------- | ----------- |
| Replacement Cost (RC)           | 현재 경제적 노출   |
| Potential Future Exposure (PFE) | 미래 잠재 노출    |
| Alpha (α)                       | 규제 보정계수     |
| Exposure at Default (EAD)       | 최종 규제 노출    |

EAD는 Basel III 신용위험 규제체계에서 사용하는 공식 노출액이다.

---

# 4. Mathematical Definition

SA-CCR의 기본 산식은 다음과 같다.

```math
EAD = α × (RC + PFE)
```

여기서

* **RC** : Replacement Cost
* **PFE** : Potential Future Exposure
* **α** : Basel III 규제 보정계수(표준 접근법에서는 일반적으로 1.4)
* **EAD** : Exposure at Default

---

# 5. Formula Interpretation

```text
Replacement Cost
        │
        ├──────────────┐
        ▼              ▼
Potential Future Exposure
        │
        ▼
Current + Future Exposure
        │
        ▼
Alpha Adjustment
        │
        ▼
Exposure at Default
```

RC는 현재 위험을, PFE는 미래 위험을 나타내며 Alpha는 규제 보수성을 반영한다.

---

# 6. Component Responsibilities

| Component | Responsibility |
| --------- | -------------- |
| RC        | 현재 노출 계산       |
| PFE       | 미래 잠재 노출 계산    |
| Alpha     | 규제 보정          |
| EAD       | 최종 규제 노출 산출    |

각 요소는 독립적인 Formula Contract를 가지며 EAD에서 통합된다.

---

# 7. Business Example

예를 들어 다음과 같은 포트폴리오를 가정한다.

| Item                      | Value |
| ------------------------- | ----: |
| Replacement Cost          |    35 |
| Potential Future Exposure |    65 |
| Alpha                     |   1.4 |

계산은 다음과 같다.

```text
Exposure Before Alpha

35 + 65 = 100

↓

EAD

1.4 × 100 = 140
```

최종 Exposure at Default는 **140**이다.

---

# 8. Relationship with Credit RWA

EAD는 Basel III 신용위험 규제자본 계산으로 연결된다.

```text
Trade Portfolio
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Exposure at Default
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

---

# 9. Relationship with CVA

SA-CCR에서 계산한 EAD는 거래상대방 신용가치조정(CVA)의 핵심 입력값이다.

```text
Exposure at Default
        │
        ▼
Counterparty Exposure
        │
        ▼
Credit Valuation Adjustment
```

---

# 10. Input Contract

| Input                     | Description |
| ------------------------- | ----------- |
| Replacement Cost          | 현재 노출       |
| Potential Future Exposure | 미래 잠재 노출    |
| Alpha                     | 규제 보정계수     |
| Netting Set               | 상계 집합       |
| Trade Portfolio           | 거래 포트폴리오    |

---

# 11. Computation Contract

```text
Trade Portfolio
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Exposure Before Alpha
        │
        ▼
Apply Alpha
        │
        ▼
Exposure at Default
```

각 단계는 독립적으로 검증 가능해야 하며 계산 순서는 변경하지 않는다.

---

# 12. Output Contract

| Output                    | Description   |
| ------------------------- | ------------- |
| Exposure at Default       | 최종 규제 노출      |
| Replacement Cost          | 현재 노출         |
| Potential Future Exposure | 미래 잠재 노출      |
| Applied Alpha             | 적용된 규제계수      |
| Exposure Before Alpha     | Alpha 적용 전 노출 |

---

# 13. Formula Engine Model

```text
ReplacementCostCalculator
        │
        ▼
PotentialFutureExposureCalculator
        │
        ▼
ExposureAggregator
        │
        ▼
AlphaApplier
        │
        ▼
ExposureAtDefaultCalculator
```

Formula Engine은 RC와 PFE를 계산한 후 Alpha를 적용하여 최종 EAD를 생성한다.

---

# 14. Implementation Considerations

구현 시 고려사항

* RC와 PFE 계산 모듈 분리
* Alpha를 외부 규제 파라미터로 관리
* 계산 결과의 추적성 확보
* Immutable Value Object 사용
* 규제 버전별 파라미터 관리

---

# 15. Performance Considerations

대규모 포트폴리오 계산에서는 다음을 고려한다.

* RC 결과 캐싱
* PFE 결과 캐싱
* Alpha 파라미터 캐싱
* Netting Set 병렬 계산
* Incremental Recalculation

---

# 16. Relationship with FRKP

| Layer          | Related Document               |
| -------------- | ------------------------------ |
| Reference      | [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)                         |
| Knowledge      | [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md), [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)                 |
| Analysis       | [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)                         |
| Formula        | [FC-441](FC-441_REPLACEMENT_COST.md), [FC-442](FC-442_POTENTIAL_FUTURE_EXPOSURE.md), [FC-443](FC-443_ALPHA.md), [FC-444](FC-444_SA_CCR_EAD.md) |
| Implementation | [IMP-441](../../06_Implementation_Guide/04_SA_CCR/IMP-441_SA_CCR_IMPLEMENTATION.md)                        |
| Architecture   | [ARCH-741](../../07_Architecture/04_SA_CCR/ARCH-741_SA_CCR_ARCHITECTURE.md)                       |

---

# 17. Knowledge Graph

```text
Trade Portfolio
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
        │
        ▼
Credit RWA
        │
        ▼
Regulatory Capital
```

---

# 18. Learning Path

```text
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
FC-444 Exposure at Default
        │
        ▼
IMP-441 SA-CCR Implementation
        │
        ▼
ARCH-741 SA-CCR Architecture
```

---

# 19. Summary

Exposure at Default는 SA-CCR의 최종 산출물이며, 거래상대방이 부도하는 시점에 규제 목적상 금융기관이 보유하고 있다고 간주하는 총 신용노출을 나타낸다.

FRKP에서는 EAD를 **Replacement Cost → Potential Future Exposure → Alpha → Exposure at Default**로 이어지는 최종 계산 계약으로 정의한다. 계산된 EAD는 Basel III 규제자본 계산, Credit RWA 산출 및 CVA 계산의 핵심 입력값으로 활용된다.

---

# 20. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
