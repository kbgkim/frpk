# FC-424 — Delta Risk Charge

---

# Document Information

| Item            | Value             |
| --------------- | ----------------- |
| Document ID     | FC-424            |
| Document Name   | Delta Risk Charge |
| Version         | 1.0.0             |
| Status          | Draft             |
| Category        | Formula Catalog   |
| Parent Document | FC-423            |
| Created         | 2026-06-26        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Formula Catalog](../README.md) > [FC-424 — Delta Risk Charge](FC-424_DELTA_RISK_CHARGE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md) |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-425](FC-425_VEGA_RISK_CHARGE.md) |

### Related Documents

- [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md)
- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 FRTB Standardised Approach(SA)의 Sensitivity-Based Method(SBM)에서 사용하는 **Delta Risk Charge**의 개념, 수학적 정의, 계산 절차 및 구현 관점을 설명한다.

Delta Risk Charge는 시장위험 자본 계산에서 가장 기본이 되는 위험 측정 요소이며, 금리, 주식, 외환, 상품, 신용스프레드 등 모든 Risk Class에 공통적으로 적용된다.

---

# 2. Business Purpose

시장위험 관리에서 가장 먼저 알고 싶은 것은 다음과 같다.

> **"시장 위험요인이 조금 변하면 내 포지션의 가치는 얼마나 변하는가?"**

이 질문에 답하는 값이 **Delta**이다.

Delta는 금융상품이 특정 Risk Factor에 얼마나 민감한지를 나타내는 1차 민감도이며, 대부분의 선형 상품에서 시장위험을 설명하는 핵심 지표이다.

---

# 3. Regulatory Perspective

FRTB Standardised Approach는 금융상품 자체가 아니라 **Risk Factor Sensitivity**를 기준으로 자본을 계산한다.

Delta Risk Charge는 다음 절차의 첫 단계이다.

```text
Risk Factor
      │
      ▼
Delta Sensitivity
      │
      ▼
Risk Weight
      │
      ▼
Bucket Aggregation
      │
      ▼
Risk Class Capital
```

---

# 4. Mathematical Definition

Delta는 금융상품 가치 (V)를 Risk Factor (x)에 대해 편미분한 값으로 정의된다.

[
\Delta=\frac{\partial V}{\partial x}
]

이는 Risk Factor가 아주 작은 폭으로 변화할 때 금융상품 가치가 얼마나 변하는지를 의미한다.

---

# 5. Formula Interpretation

Delta는 **기울기(Slope)** 를 의미한다.

예를 들어 채권의 경우

* 금리 ↑ → 채권가격 ↓
* 금리 ↓ → 채권가격 ↑

이며, Delta는 이 변화율을 수치화한 것이다.

---

# 6. Business Example

금리 민감도가

```text
-12,500 KRW / bp
```

인 국채 포지션이 있다고 가정한다.

기준금리가

```text
+5 bp
```

상승하면 예상 가격 변화는

```text
-62,500 KRW
```

이다.

Delta는 이러한 **선형 근사(linear approximation)** 를 제공한다.

---

# 7. Calculation Flow

```text
Market Data
      │
      ▼
Risk Factor
      │
      ▼
Pricing Model
      │
      ▼
Delta Calculation
      │
      ▼
Risk Weight
      │
      ▼
Weighted Sensitivity
```

---

# 8. Risk Weight Application

계산된 Delta는 규제에서 정의한 **Risk Weight(RW)** 와 결합된다.

일반적인 계산 흐름은 다음과 같다.

[
WS = RW \times \Delta
]

여기서

* (WS): Weighted Sensitivity
* (RW): Risk Weight
* (\Delta): Delta Sensitivity

Weighted Sensitivity는 이후 Bucket Aggregation의 입력값으로 사용된다.

---

# 9. Bucket Aggregation

동일 Bucket에 속하는 Weighted Sensitivity는 상관계수를 고려하여 집계된다.

```text
Weighted Sensitivity
        │
        ▼
Bucket
        │
        ▼
Correlation
        │
        ▼
Bucket Capital
```

Bucket Aggregation 공식은 FC-423(SBM Framework)에서 정의한 공통 절차를 따른다.

---

# 10. Input Contract

| Input              | Description |
| ------------------ | ----------- |
| Risk Factor        | 위험요인        |
| Delta Sensitivity  | 1차 민감도      |
| Risk Weight        | 위험가중치       |
| Bucket             | 버킷 정보       |
| Correlation Matrix | 상관계수        |

---

# 11. Computation Contract

```text
Delta Sensitivity
        │
        ▼
Validation
        │
        ▼
Risk Weight
        │
        ▼
Weighted Sensitivity
        │
        ▼
Bucket Aggregation
```

---

# 12. Output Contract

| Output               | Description |
| -------------------- | ----------- |
| Weighted Sensitivity | 위험가중 민감도    |
| Bucket Capital       | 버킷별 자본      |
| Risk Class Capital   | 위험군 자본      |

---

# 13. Formula Engine Model

```text
DeltaCalculator
        │
        ▼
RiskWeightApplier
        │
        ▼
WeightedSensitivity
```

Formula Engine은 Delta 계산과 Risk Weight 적용까지 담당한다.

Bucket 및 Risk Class 집계는 Risk Engine에서 수행한다.

---

# 14. Implementation Considerations

구현 시 고려사항

* Delta 계산과 Pricing Model을 분리한다.
* Risk Weight는 설정(Configuration)으로 관리한다.
* Weighted Sensitivity는 Immutable Value Object로 생성한다.
* Risk Factor별 확장성을 고려한 Strategy 구조를 적용한다.

---

# 15. Performance Considerations

대규모 포트폴리오에서는

* Risk Factor별 병렬 계산
* Bucket 단위 병렬 집계
* 벡터 연산 최적화

가 성능 향상의 핵심이다.

---

# 16. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)           |
| Knowledge      | [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)           |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)           |
| Formula        | [FC-423](FC-423_SENSITIVITY_BASED_METHOD.md), [FC-424](FC-424_DELTA_RISK_CHARGE.md)   |
| Implementation | IMP-421          |
| Architecture   | [ARCH-721](../../07_Architecture/02_FRTB/ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)         |

---

# 17. Knowledge Graph

```text
Risk Factor
      │
      ▼
Delta
      │
      ▼
Risk Weight
      │
      ▼
Weighted Sensitivity
      │
      ▼
Bucket Capital
      │
      ▼
Risk Class Capital
```

---

# 18. Learning Path

```text
KB-222 FRTB Framework
        │
        ▼
FC-423 Sensitivity-Based Method
        │
        ▼
FC-424 Delta Risk Charge
        │
        ▼
FC-425 Vega Risk Charge
        │
        ▼
FC-426 Curvature Risk Charge
        │
        ▼
ARCH-721 FRTB Calculation Architecture
```

---

# 19. Summary

Delta Risk Charge는 FRTB Standardised Approach에서 가장 기본적인 시장위험 측정 요소이다.

Delta는 Risk Factor 변화에 대한 금융상품 가치의 1차 민감도를 나타내며, Risk Weight를 적용한 후 Bucket 및 Risk Class 수준으로 집계되어 시장위험 자본 계산의 기초를 형성한다.

FRKP에서는 Delta Risk Charge를 **Risk Factor → Delta → Weighted Sensitivity → Bucket Aggregation**으로 이어지는 독립적인 계산 계약(Computation Contract)으로 정의하며, Formula Engine과 Risk Engine의 책임을 명확히 분리한다.

---

# 20. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
