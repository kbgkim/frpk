# FC-442 — Potential Future Exposure (PFE)

---

# Document Information

| Item            | Value                     |
| --------------- | ------------------------- |
| Document ID     | FC-442                    |
| Document Name   | Potential Future Exposure |
| Version         | 1.0.0                     |
| Status          | Draft                     |
| Category        | Formula Catalog           |
| Parent Document | KB-242                    |
| Created         | 2026-06-26                |
| Last Updated    | 2026-06-26                |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Formula Catalog](../README.md) > [FC-442 — Potential Future Exposure (PFE)](FC-442_POTENTIAL_FUTURE_EXPOSURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-441](FC-441_REPLACEMENT_COST.md) |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-443](FC-443_ALPHA.md) |

### Related Documents

- [FC-441](FC-441_REPLACEMENT_COST.md)
- [FC-443](FC-443_ALPHA.md)
- [FC-444](FC-444_SA_CCR_EAD.md)
- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 SA-CCR(Standardised Approach for Counterparty Credit Risk)의 두 번째 핵심 계산 요소인 **Potential Future Exposure(PFE)** 의 개념, 수학적 정의, 계산 구조 및 Formula Contract를 설명한다.

Potential Future Exposure는 계약의 잔존기간 동안 시장가격 변동으로 인해 미래에 발생할 수 있는 잠재적 노출을 나타낸다.

FRKP에서는 PFE를 **미래 시장환경을 고려하여 추정한 잠재 경제적 노출(Potential Economic Exposure)** 로 정의한다.

---

# 2. Business Purpose

현재 노출(Replacement Cost)은 현재 시점의 위험만 측정한다.

그러나 파생상품은 계약 기간 동안 시장가격이 지속적으로 변동하므로 미래에는 현재보다 더 큰 노출이 발생할 수 있다.

PFE는 이러한 미래 위험을 규제자본 계산에 반영하기 위해 사용된다.

---

# 3. Regulatory Perspective

SA-CCR는 거래상대방 위험을 다음 두 부분으로 구분한다.

| Component                 | Purpose                   |
| ------------------------- | ------------------------- |
| Replacement Cost          | 현재 노출(Current Exposure)   |
| Potential Future Exposure | 미래 잠재 노출(Future Exposure) |

Replacement Cost는 현재 시점을, PFE는 계약 만기까지의 잠재적 위험을 반영한다.

---

# 4. Conceptual Formula

개념적으로 PFE는 다음과 같은 계층적 구조를 가진다.

[
PFE = Multiplier \times Aggregate\ AddOn
]

여기서

* **Aggregate Add-on** : 자산군별 잠재 노출의 합
* **Multiplier** : 담보 및 현재 노출 수준을 반영하는 조정계수

실제 규제식은 감독계수와 자산군별 규칙을 포함한다.

---

# 5. Hierarchical Calculation Model

```text
Trade
   │
   ▼
Asset Class
   │
   ▼
Hedging Set
   │
   ▼
Trade Add-on
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

PFE는 단일 공식이 아니라 여러 단계의 집계 과정을 거쳐 계산된다.

---

# 6. Asset Class Structure

SA-CCR는 자산군별로 서로 다른 계산 규칙을 적용한다.

| Asset Class      | Examples                    |
| ---------------- | --------------------------- |
| Interest Rate    | IRS, OIS                    |
| Foreign Exchange | FX Forward, FX Swap         |
| Credit           | CDS                         |
| Equity           | Equity Swap, Equity Option  |
| Commodity        | Oil, Gas, Metal Derivatives |

각 자산군은 고유한 감독계수와 상계 규칙을 가진다.

---

# 7. Supervisory Factor

감독계수(Supervisory Factor)는 자산군별 위험 수준을 반영하는 규제 파라미터이다.

예를 들어,

* 금리 파생상품
* 외환 파생상품
* 신용 파생상품

은 서로 다른 감독계수를 적용받는다.

감독계수는 규제기관이 정의하며 Formula Engine의 입력값으로 사용된다.

---

# 8. Hedging Set

동일한 위험요인에 대한 거래는 Hedging Set으로 묶어 계산한다.

```text
Interest Rate Swap A
Interest Rate Swap B
Interest Rate Swap C
          │
          ▼
      Hedging Set
          │
          ▼
     Net Sensitivity
```

Hedging Set은 위험 상쇄 효과를 반영하기 위한 계산 단위이다.

---

# 9. Aggregate Add-on

각 Hedging Set의 결과를 자산군별로 집계하여 Aggregate Add-on을 계산한다.

```text
Interest Rate Add-on
         │
FX Add-on
         │
Credit Add-on
         │
Commodity Add-on
         │
         ▼
Aggregate Add-on
```

Aggregate Add-on은 PFE 계산의 핵심 중간 산출물이다.

---

# 10. Multiplier

Multiplier는 현재 노출 수준과 담보 효과를 반영하는 조정계수이다.

주요 역할은 다음과 같다.

* 담보 효과 반영
* 과도한 PFE 산출 방지
* 규제 보수성 유지

Multiplier를 적용하여 Aggregate Add-on을 최종 PFE로 변환한다.

---

# 11. Relationship with Replacement Cost

Replacement Cost와 PFE는 서로 다른 위험을 측정한다.

| Component | Risk  |
| --------- | ----- |
| RC        | 현재 위험 |
| PFE       | 미래 위험 |

최종 Exposure at Default는 두 요소를 결합하여 계산한다.

---

# 12. Input Contract

| Input                  | Description |
| ---------------------- | ----------- |
| Trade Portfolio        | 거래 포트폴리오    |
| Asset Class            | 자산군         |
| Supervisory Factor     | 감독계수        |
| Hedging Set            | 헤징 집합       |
| Trade Notional         | 명목금액        |
| Remaining Maturity     | 잔존만기        |
| Collateral Information | 담보 정보       |

---

# 13. Computation Contract

```text
Trade Portfolio
        │
        ▼
Asset Classification
        │
        ▼
Hedging Set Construction
        │
        ▼
Trade Add-on
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

각 단계는 독립적인 계산 계약을 가진다.

---

# 14. Output Contract

| Output                    | Description |
| ------------------------- | ----------- |
| Trade Add-on              |             |
| Asset Class Add-on        |             |
| Aggregate Add-on          |             |
| Multiplier                |             |
| Potential Future Exposure |             |

---

# 15. Formula Engine Model

```text
TradeClassifier
        │
        ▼
AssetClassCalculator
        │
        ▼
HedgingSetCalculator
        │
        ▼
TradeAddOnCalculator
        │
        ▼
AggregateAddOnCalculator
        │
        ▼
MultiplierCalculator
        │
        ▼
PotentialFutureExposureCalculator
```

Formula Engine은 PFE 계산만 담당하며 EAD 계산은 별도 Formula에서 수행한다.

---

# 16. Implementation Considerations

구현 시 고려사항

* Asset Class별 계산 모듈 분리
* Supervisory Parameter 외부 설정화
* Hedging Set 구성 로직 분리
* Aggregate Add-on 집계 최적화
* Multiplier 계산 독립화

---

# 17. Performance Considerations

대규모 포트폴리오 계산에서는 다음을 고려한다.

* Hedging Set 캐싱
* 감독계수 캐싱
* Asset Class 병렬 계산
* Trade Add-on 벡터화
* Aggregate Add-on 병렬 집계

---

# 18. Relationship with FRKP

| Layer          | Related Document               |
| -------------- | ------------------------------ |
| Reference      | [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)                         |
| Knowledge      | [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md), [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)                 |
| Analysis       | [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)                         |
| Formula        | [FC-441](FC-441_REPLACEMENT_COST.md), [FC-442](FC-442_POTENTIAL_FUTURE_EXPOSURE.md), [FC-443](FC-443_ALPHA.md), [FC-444](FC-444_SA_CCR_EAD.md) |
| Implementation | [IMP-441](../../06_Implementation_Guide/04_SA_CCR/IMP-441_SA_CCR_IMPLEMENTATION.md)                        |
| Architecture   | [ARCH-741](../../07_Architecture/04_SA_CCR/ARCH-741_SA_CCR_ARCHITECTURE.md)                       |

---

# 19. Knowledge Graph

```text
Trade Portfolio
        │
        ▼
Asset Class
        │
        ▼
Hedging Set
        │
        ▼
Trade Add-on
        │
        ▼
Aggregate Add-on
        │
        ▼
Multiplier
        │
        ▼
Potential Future Exposure
        │
        ▼
Exposure at Default
```

---

# 20. Learning Path

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

# 21. Summary

Potential Future Exposure는 계약 만기 이전 시장가격 변동으로 인해 발생할 수 있는 미래의 잠재 노출을 나타낸다.

SA-CCR에서는 PFE를 **Asset Class → Hedging Set → Trade Add-on → Aggregate Add-on → Multiplier → Potential Future Exposure**의 계층적 계산 구조로 정의한다.

FRKP에서는 PFE를 현재 노출인 Replacement Cost와 구분되는 독립적인 계산 계약으로 정의하며, 이후 Alpha를 적용하여 Exposure at Default 산출에 활용한다.

---

# 22. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
