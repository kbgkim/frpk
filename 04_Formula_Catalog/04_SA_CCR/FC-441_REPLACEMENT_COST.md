# FC-441 — Replacement Cost (RC)

---

# Document Information

| Item            | Value            |
| --------------- | ---------------- |
| Document ID     | FC-441           |
| Document Name   | Replacement Cost |
| Version         | 1.0.0            |
| Status          | Draft            |
| Category        | Formula Catalog  |
| Parent Document | KB-242           |
| Created         | 2026-06-26       |
| Last Updated    | 2026-06-26       |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Formula Catalog](../README.md) > [FC-441 — Replacement Cost (RC)](FC-441_REPLACEMENT_COST.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-442](FC-442_POTENTIAL_FUTURE_EXPOSURE.md) |

### Related Documents

- [FC-442](FC-442_POTENTIAL_FUTURE_EXPOSURE.md)
- [FC-443](FC-443_ALPHA.md)
- [FC-444](FC-444_SA_CCR_EAD.md)
- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 SA-CCR(Standardised Approach for Counterparty Credit Risk)의 첫 번째 핵심 계산 요소인 **Replacement Cost(RC)** 의 개념, 수학적 정의, 업무적 의미 및 계산 계약(Calculation Contract)을 설명한다.

Replacement Cost는 거래상대방이 현재 시점에 부도할 경우 금융기관이 동일한 경제적 계약을 다시 체결하기 위해 부담해야 하는 현재 노출(Current Exposure)을 의미한다.

FRKP에서는 RC를 **담보와 상계(Netting)를 반영한 현재 경제적 노출(Current Economic Exposure)** 로 정의한다.

---

# 2. Business Purpose

파생상품 계약은 시간이 지남에 따라 시장가치가 변한다.

현재 시점에서 계약의 시장가치가 금융기관에 유리한 경우, 거래상대방이 즉시 부도하면 동일한 계약을 다시 체결하기 위해 비용이 발생할 수 있다.

Replacement Cost는 이러한 **현재 시점의 경제적 손실 가능성**을 측정하기 위한 지표이다.

---

# 3. Regulatory Perspective

SA-CCR는 현재 노출과 미래 잠재 노출을 구분한다.

| Component                 | Purpose                   |
| ------------------------- | ------------------------- |
| Replacement Cost          | 현재 노출(Current Exposure)   |
| Potential Future Exposure | 미래 잠재 노출(Future Exposure) |

Replacement Cost는 현재 시점에서 이미 발생한 노출을 반영한다.

---

# 4. Mathematical Definition

개념적으로 Replacement Cost는 다음과 같이 표현할 수 있다.

[
RC = \max(V - C,;0)
]

여기서

* **V** : Netting Set의 현재 시장가치(Current Market Value)
* **C** : 인정 가능한 담보(Recognized Collateral)
* **RC** : Replacement Cost

음수 노출은 인정하지 않으므로 결과는 0 이상이다.

---

# 5. Economic Interpretation

Replacement Cost는 단순한 시가평가(Mark-to-Market)가 아니다.

다음 요소를 모두 반영한 **순현재노출(Net Current Exposure)** 이다.

* 현재 시장가치
* Netting Agreement
* Variation Margin
* 인정 담보
* 규제 인정 기준

---

# 6. Business Example

다음과 같은 거래를 가정한다.

| 항목      |     금액 |
| ------- | -----: |
| 현재 시장가치 | 120억 원 |
| 인정 담보   |  80억 원 |

계산 결과

```text
RC

=

max(120−80, 0)

=

40억 원
```

즉, 거래상대방이 현재 부도할 경우 금융기관의 현재 노출은 40억 원이다.

---

# 7. Netting

여러 계약이 법적으로 상계 가능한 경우 Netting Set 단위로 평가한다.

```text
Trade A   +120

Trade B   -90

Trade C   +30

      │

      ▼

Netting Set

      │

Net Market Value = +60
```

Replacement Cost는 개별 계약이 아니라 Netting Set 기준으로 계산한다.

---

# 8. Collateral Treatment

담보는 RC를 감소시키는 핵심 요소이다.

반영 대상

* Cash Collateral
* Eligible Securities
* Variation Margin

담보는 규제 기준에 따라 인정 여부와 인정 금액이 결정된다.

---

# 9. Current Exposure

Replacement Cost는 현재 노출(Current Exposure)을 나타낸다.

```text
Trade Portfolio
        │
        ▼
Current Market Value
        │
        ▼
Netting
        │
        ▼
Collateral
        │
        ▼
Replacement Cost
```

현재 시점의 손실 가능성을 측정하는 단계이다.

---

# 10. Relationship with PFE

Replacement Cost와 Potential Future Exposure는 서로 다른 위험을 나타낸다.

| Component | Meaning  |
| --------- | -------- |
| RC        | 현재 노출    |
| PFE       | 미래 잠재 노출 |

두 요소는 이후 Exposure at Default 계산에서 결합된다.

---

# 11. Input Contract

| Input                 | Description |
| --------------------- | ----------- |
| Trade Portfolio       | 거래 포트폴리오    |
| Netting Set           | 상계 집합       |
| Current Market Value  | 현재 시장가치     |
| Recognized Collateral | 인정 담보       |
| Margin Information    | 담보 정보       |

---

# 12. Computation Contract

```text
Trade Portfolio
        │
        ▼
Netting Set Construction
        │
        ▼
Market Value Aggregation
        │
        ▼
Collateral Recognition
        │
        ▼
Replacement Cost
```

각 단계는 독립적으로 수행된다.

---

# 13. Output Contract

| Output                | Description |
| --------------------- | ----------- |
| Replacement Cost      |             |
| Net Market Value      |             |
| Recognized Collateral |             |
| Current Exposure      |             |

---

# 14. Formula Engine Model

```text
TradeCollector
        │
        ▼
NettingCalculator
        │
        ▼
MarketValueCalculator
        │
        ▼
CollateralRecognizer
        │
        ▼
ReplacementCostCalculator
```

Formula Engine은 Replacement Cost만 계산하며 PFE 및 EAD 계산은 별도 Formula에서 수행한다.

---

# 15. Implementation Considerations

구현 시 고려사항

* Netting Set 단위 계산
* 담보 인정 규칙 분리
* Market Value 집계 분리
* Margin 계산과 RC 계산 분리
* Immutable 계산 결과 사용

---

# 16. Performance Considerations

대규모 포트폴리오 계산에서는 다음을 고려한다.

* Netting Set 캐싱
* Market Value 집계 최적화
* 담보 정보 캐싱
* 병렬 Portfolio 처리
* Incremental Revaluation

---

# 17. Relationship with FRKP

| Layer          | Related Document               |
| -------------- | ------------------------------ |
| Reference      | [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)                         |
| Knowledge      | [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md), [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)                 |
| Analysis       | [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)                         |
| Formula        | [FC-441](FC-441_REPLACEMENT_COST.md), [FC-442](FC-442_POTENTIAL_FUTURE_EXPOSURE.md), [FC-443](FC-443_ALPHA.md), [FC-444](FC-444_SA_CCR_EAD.md) |
| Implementation | [IMP-441](../../06_Implementation_Guide/04_SA_CCR/IMP-441_SA_CCR_IMPLEMENTATION.md)                        |
| Architecture   | [ARCH-741](../../07_Architecture/04_SA_CCR/ARCH-741_SA_CCR_ARCHITECTURE.md)                       |

---

# 18. Knowledge Graph

```text
Trade Portfolio
        │
        ▼
Netting Set
        │
        ▼
Current Market Value
        │
        ▼
Collateral
        │
        ▼
Replacement Cost
        │
        ▼
Exposure at Default
```

---

# 19. Learning Path

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
FC-444 SA-CCR EAD
        │
        ▼
IMP-441 SA-CCR Implementation
        │
        ▼
ARCH-741 SA-CCR Architecture
```

---

# 20. Summary

Replacement Cost는 거래상대방이 현재 시점에 부도할 경우 금융기관이 부담하게 되는 현재 경제적 노출을 나타낸다.

RC는 현재 시장가치, Netting Agreement, 인정 담보 및 Variation Margin을 반영하여 산출되며, SA-CCR의 현재 노출(Current Exposure)을 측정하는 핵심 요소이다.

FRKP에서는 RC를 **Trade Portfolio → Netting Set → Market Value → Collateral → Replacement Cost**로 이어지는 독립적인 계산 계약으로 정의하며, 이후 Potential Future Exposure 및 Alpha와 결합하여 Exposure at Default를 산출한다.

---

# 21. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
