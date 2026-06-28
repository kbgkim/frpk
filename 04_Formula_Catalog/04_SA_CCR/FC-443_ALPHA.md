# FC-443 — Alpha (α)

---

# Document Information

| Item            | Value           |
| --------------- | --------------- |
| Document ID     | FC-443          |
| Document Name   | Alpha           |
| Version         | 1.0.0           |
| Status          | Draft           |
| Category        | Formula Catalog |
| Parent Document | KB-242          |
| Created         | 2026-06-26      |
| Last Updated    | 2026-06-26      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Formula Catalog](../README.md) > [FC-443 — Alpha (α)](FC-443_ALPHA.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-442](FC-442_POTENTIAL_FUTURE_EXPOSURE.md) |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-444](FC-444_SA_CCR_EAD.md) |

### Related Documents

- [FC-441](FC-441_REPLACEMENT_COST.md)
- [FC-444](FC-444_SA_CCR_EAD.md)
- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
- [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 SA-CCR(Standardised Approach for Counterparty Credit Risk)의 규제 보정계수인 **Alpha(α)** 의 개념, 규제 목적, 수학적 정의 및 계산 계약(Calculation Contract)을 설명한다.

Alpha는 현재 노출(Replacement Cost)과 미래 잠재 노출(Potential Future Exposure)을 규제 목적에 맞게 보정하여 최종 Exposure at Default(EAD)를 산출하기 위한 Basel III의 규제 계수이다.

FRKP에서는 Alpha를 **모델 불확실성(Model Risk), 측정 오차(Measurement Uncertainty), 규제 보수성(Regulatory Conservatism)을 반영하는 규제 보정계수**로 정의한다.

---

# 2. Business Purpose

Replacement Cost와 Potential Future Exposure를 계산하더라도 실제 거래상대방 위험을 완벽하게 설명할 수는 없다.

다음과 같은 불확실성이 항상 존재한다.

* 시장가격의 급격한 변동
* 모델 단순화에 따른 오차
* 데이터 품질 문제
* 극단적 시장 상황
* 측정되지 않은 위험요인

Alpha는 이러한 불확실성을 규제 목적상 보완하기 위해 사용된다.

---

# 3. Regulatory Perspective

Basel III는 SA-CCR 계산에서 **Alpha = 1.4**를 규정한다.

이 값은 금융기관이 임의로 변경하는 입력값이 아니라 규제에서 정한 표준 계수이다.

Alpha의 목적은 다음과 같다.

* 규제 보수성 확보
* 모델 위험 반영
* 금융기관 간 일관성 확보
* 과소평가 방지

---

# 4. Mathematical Definition

Alpha는 EAD 계산식에 적용된다.

[
EAD = \alpha \times (RC + PFE)
]

여기서

* **α** : Basel III 규제 보정계수
* **RC** : Replacement Cost
* **PFE** : Potential Future Exposure

Alpha 자체는 계산되는 값이 아니라 규제에서 정의한 파라미터이다.

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
Regulatory Exposure
```

Alpha는 계산 결과를 규제 목적의 노출로 변환하는 마지막 보정 단계이다.

---

# 6. Why Alpha Is Needed

RC와 PFE만으로는 다음 요소를 완전히 반영하기 어렵다.

* 모델 단순화
* 위험요인 누락
* 비정상 시장
* 극단적 변동성
* 계산 오차

Alpha는 이러한 잔여 위험(Residual Risk)을 규제적으로 반영한다.

---

# 7. Regulatory Philosophy

Alpha는 다음과 같은 규제 철학을 구현한다.

| Principle   | Meaning         |
| ----------- | --------------- |
| Prudence    | 보수적 자본 산정       |
| Consistency | 금융기관 간 비교 가능성   |
| Stability   | 경기 변동 시 자본의 안정성 |
| Simplicity  | 표준화된 계산 방식      |

---

# 8. Business Example

예를 들어,

| 항목                        |   값 |
| ------------------------- | --: |
| Replacement Cost          |  80 |
| Potential Future Exposure | 120 |
| Alpha                     | 1.4 |

계산은 다음과 같다.

```text
Exposure Before Alpha

=

80 + 120

=

200

↓

Exposure at Default

=

1.4 × 200

=

280
```

Alpha를 적용함으로써 규제 목적의 노출액이 산출된다.

---

# 9. Relationship with RC and PFE

| Component                 | Role     |
| ------------------------- | -------- |
| Replacement Cost          | 현재 위험    |
| Potential Future Exposure | 미래 위험    |
| Alpha                     | 규제 보정    |
| Exposure at Default       | 최종 규제 노출 |

Alpha는 RC나 PFE를 대체하지 않으며, 이 둘을 보정하는 역할만 수행한다.

---

# 10. Input Contract

| Input                     | Description |
| ------------------------- | ----------- |
| Replacement Cost          | 현재 노출       |
| Potential Future Exposure | 미래 잠재 노출    |
| Regulatory Alpha          | 규제 계수       |

---

# 11. Computation Contract

```text
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Exposure Before Alpha
        │
        ▼
Apply Regulatory Alpha
        │
        ▼
Adjusted Exposure
```

Alpha는 최종 단계에서 적용된다.

---

# 12. Output Contract

| Output                  | Description |
| ----------------------- | ----------- |
| Alpha-adjusted Exposure |             |
| Regulatory Exposure     |             |
| Applied Alpha           |             |

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
AlphaCalculator
        │
        ▼
AdjustedExposure
```

Alpha는 별도의 계산 로직을 갖기보다는 규제 파라미터를 적용하는 컴포넌트로 구현한다.

---

# 14. Implementation Considerations

구현 시 고려사항

* Alpha는 외부 설정(Configuration)으로 관리한다.
* 규제 버전별 계수 변경을 지원한다.
* RC/PFE 계산과 독립적으로 적용한다.
* 계산 과정에서 Alpha 적용 여부를 추적 가능하게 기록한다.

---

# 15. Performance Considerations

Alpha 자체의 계산 비용은 매우 작다.

성능 측면에서는 다음 사항을 고려한다.

* 규제 파라미터 캐싱
* 배치 계산 시 재사용
* 규제 버전별 파라미터 관리

---

# 16. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)           |
| Knowledge      | [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md), [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)   |
| Analysis       | [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)           |
| Formula        | [FC-441](FC-441_REPLACEMENT_COST.md) ~ [FC-444](FC-444_SA_CCR_EAD.md)  |
| Implementation | [IMP-441](../../06_Implementation_Guide/04_SA_CCR/IMP-441_SA_CCR_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-741](../../07_Architecture/04_SA_CCR/ARCH-741_SA_CCR_ARCHITECTURE.md)         |

---

# 17. Knowledge Graph

```text
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Exposure Before Alpha
        │
        ▼
Alpha
        │
        ▼
Exposure at Default
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

Alpha는 SA-CCR에서 현재 노출(Replacement Cost)과 미래 잠재 노출(Potential Future Exposure)을 규제 목적에 맞게 보정하는 Basel III의 표준 규제 계수이다.

Alpha는 단순한 상수가 아니라 모델 위험, 측정 불확실성 및 규제 보수성을 반영하기 위한 정책적 요소이며, 최종 Exposure at Default를 산출하는 마지막 단계에서 적용된다.

FRKP에서는 Alpha를 **Regulatory Adjustment Factor**로 정의하고, 규제 파라미터로 관리되는 독립적인 계산 계약으로 취급한다.

---

# 20. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
