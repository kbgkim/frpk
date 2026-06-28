# FC-453 — Credit Valuation Adjustment

---

# Document Information

| Item          | Value                       |
| ------------- | --------------------------- |
| Document ID   | FC-453                      |
| Document Name | Credit Valuation Adjustment |
| Version       | 1.0.0                       |
| Status        | Active                      |
| Category      | Formula Catalog             |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)                  |
| Created       | 2026-06-27                  |
| Last Updated  | 2026-06-27                  |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Formula Catalog](../README.md) > [FC-453 — Credit Valuation Adjustment](FC-453_CREDIT_VALUATION_ADJUSTMENT.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-452](FC-452_EXPECTED_EXPOSURE.md) |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-454](FC-454_CVA_CAPITAL_CHARGE.md) |

### Related Documents

- [FC-451](FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)
- [FC-452](FC-452_EXPECTED_EXPOSURE.md)
- [FC-454](FC-454_CVA_CAPITAL_CHARGE.md)
- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Credit Valuation Adjustment(CVA)** 의 공식(Formulas)과 계산 계약(Calculation Contract)을 정의한다.

Credit Valuation Adjustment는 거래상대방(Counterparty)의 부도위험(Default Risk)을 파생상품의 공정가치(Fair Value)에 반영하기 위한 가치조정(Value Adjustment)이다.

본 문서는 Basel III CVA Framework에서 사용되는 핵심 산식을 정의하며, Formula Engine 및 Risk Engine에서 재사용 가능한 Formula Asset으로 관리한다.

---

# 2. Business Purpose

CVA의 목적은 미래 거래상대방 부도로 인해 발생할 수 있는 기대손실(Expected Credit Loss)을 현재가치로 평가하는 것이다.

주요 목적은 다음과 같다.

* 거래상대방 신용위험 반영
* 파생상품 공정가치 조정
* Basel III 규제자본 산출
* CVA Risk 측정
* XVA Framework 지원

---

# 3. Regulatory Perspective

Basel III에서는 거래상대방 신용위험을 파생상품 가치에 반영하기 위해 CVA를 요구한다.

CVA 계산은 다음 요소를 기반으로 한다.

* Expected Exposure (EE)
* Default Probability (PD)
* Loss Given Default (LGD)
* Discount Factor (DF)

---

# 4. Mathematical Definition

연속시간(Continuous Time)에서 CVA는 다음과 같이 정의된다.

[
CVA
===

(1-R)
\int_0^T
DF(t)
\cdot
EE(t)
\cdot
dPD(t)
]

여기서

| Symbol    | Description         |
| --------- | ------------------- |
| (R)       | Recovery Rate       |
| (LGD=1-R) | Loss Given Default  |
| (DF(t))   | Discount Factor     |
| (EE(t))   | Expected Exposure   |
| (PD(t))   | Default Probability |
| (T)       | Maturity            |

---

# 5. Discrete Approximation

실무에서는 일반적으로 이산시간 근사를 사용한다.

[
CVA
===

LGD
\sum_{i=1}^{n}
DF_i
\times
EE_i
\times
\Delta PD_i
]

여기서

| Symbol        | Description                  |
| ------------- | ---------------------------- |
| (EE_i)        | Expected Exposure            |
| (DF_i)        | Discount Factor              |
| (\Delta PD_i) | Marginal Default Probability |

이 식은 Basel III 및 대부분의 CVA 시스템에서 사용하는 기본 형태이다.

---

# 6. Formula Interpretation

각 기간의 기대손실은 다음과 같이 계산된다.

```text
Expected Exposure
        ×
Marginal Default Probability
        ×
Loss Given Default
        ×
Discount Factor
        │
        ▼
Present Value of Expected Loss
```

전체 기간의 현재가치 기대손실을 합산한 값이 CVA이다.

---

# 7. Input Contract

| Input                        | Required | Description                |
| ---------------------------- | :------: | -------------------------- |
| Expected Exposure Curve      |     ✔    | 기간별 EE                     |
| Marginal Default Probability |     ✔    | 기간별 부도확률                   |
| Discount Factor              |     ✔    | 할인계수                       |
| Recovery Rate                |     ✔    | 회수율                        |
| LGD                          |     ✔    | 손실률(Recovery Rate와 일관성 유지) |

---

# 8. Computation Contract

```text
Expected Exposure
        │
        ▼
Marginal Default Probability
        │
        ▼
Expected Loss
        │
        ▼
Discount Factor
        │
        ▼
Present Value
        │
        ▼
Credit Valuation Adjustment
```

---

# 9. Output Contract

| Output                      | Description    |
| --------------------------- | -------------- |
| Credit Valuation Adjustment | 현재가치 기준 기대신용손실 |

출력 통화는 입력 Exposure와 동일한 기준 통화를 사용한다.

---

# 10. Formula Engine Model

```text
Exposure Provider
        │
        ▼
Default Probability Provider
        │
        ▼
LGD Provider
        │
        ▼
Discount Engine
        │
        ▼
CVA Calculator
```

Formula Engine은 각 구성요소를 독립적으로 계산한 후 최종 CVA를 조합한다.

---

# 11. Formula Classification

| Classification   | Value         |
| ---------------- | ------------- |
| Formula Type     | Regulatory    |
| Formula Nature   | Deterministic |
| Formula Category | Credit Risk   |
| Basel Component  | CVA           |

---

# 12. Formula Dependency

### Depends On

* FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE
* FC-452_EXPECTED_EXPOSURE
* MF-453_DISCOUNT_FACTOR

### Produces

* Credit Valuation Adjustment

### Consumed By

* FC-454_CVA_CAPITAL_CHARGE

```text
MF-451
      │
      ▼
FC-451
      │
      ▼
FC-452
      │
      ▼
FC-453
      │
      ▼
FC-454
```

---

# 13. Computational Characteristics

| Property              | Value      |
| --------------------- | ---------- |
| Time Dependency       | Yes        |
| Closed Form           | No (일반적으로) |
| Numerical Integration | Yes        |
| Monte Carlo Required  | Optional   |
| Matrix Operation      | No         |
| Vector Operation      | Yes        |
| Parallelizable        | Yes        |
| Complexity            | O(n)       |

---

# 14. Relationship with FRKP

```text
Reference
      │
      ▼
Knowledge
      │
      ▼
Analysis
      │
      ▼
Mathematical Foundation
      │
      ▼
FC-451
      │
      ▼
FC-452
      │
      ▼
FC-453
      │
      ▼
FC-454
      │
      ▼
Implementation
```

---

# 15. Numerical Example

가정

| Parameter       | Value |
| --------------- | ----: |
| LGD             |   60% |
| EE              |   100 |
| Discount Factor |  0.97 |
| Marginal PD     |    2% |

계산

[
CVA
===

0.60
\times
100
\times
0.97
\times
0.02
====

1.164
]

따라서

```text
Credit Valuation Adjustment = 1.164
```

이다.

---

# 16. Validation Rules

| Validation        | Rule                    |
| ----------------- | ----------------------- |
| Expected Exposure | (EE \ge 0)              |
| Marginal PD       | (0 \le \Delta PD \le 1) |
| Discount Factor   | (0 < DF \le 1)          |
| Recovery Rate     | (0 \le R \le 1)         |
| LGD               | (LGD = 1 - R)           |

---

# 17. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Mathematical Foundation | [MF-451_HAZARD_RATE](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)                        |
| Mathematical Foundation | [MF-452_SURVIVAL_FUNCTION](../../05_Mathematical_Foundation/05_CVA/MF-452_SURVIVAL_FUNCTION.md)                  |
| Mathematical Foundation | [MF-453_DISCOUNT_FACTOR](../../05_Mathematical_Foundation/05_CVA/MF-453_DISCOUNT_FACTOR.md)                    |
| Formula                 | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula                 | [FC-452_EXPECTED_EXPOSURE](FC-452_EXPECTED_EXPOSURE.md)                  |
| Formula                 | [FC-454_CVA_CAPITAL_CHARGE](FC-454_CVA_CAPITAL_CHARGE.md)                 |
| Knowledge               | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Analysis                | [AN-251_WHY_CVA_WAS_INTRODUCED](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)             |
| Implementation          | [IMP-451_CVA_IMPLEMENTATION](../../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)                |
| Architecture            | [ARCH-751_CVA_ARCHITECTURE](../../07_Architecture/05_CVA/ARCH-751_CVA_ARCHITECTURE.md)                 |

---

# 18. Summary

Credit Valuation Adjustment는 거래상대방 부도위험을 파생상품 가치에 반영하기 위한 핵심 규제 산식이다.

기간별 Expected Exposure, Marginal Default Probability, Loss Given Default 및 Discount Factor를 결합하여 미래 기대신용손실을 현재가치로 환산한다.

CVA는 Basel III Counterparty Credit Risk Framework의 핵심 요소이며, XVA 체계의 기반이 되는 대표적인 Formula Asset이다.

---

# 19. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
