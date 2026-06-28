# FC-451 — Default Probability Term Structure

---

# Document Information

| Item          | Value                              |
| ------------- | ---------------------------------- |
| Document ID   | FC-451                             |
| Document Name | Default Probability Term Structure |
| Version       | 1.0.0                              |
| Status        | Active                             |
| Category      | Formula Catalog                    |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)                         |
| Created       | 2026-06-27                         |
| Last Updated  | 2026-06-27                         |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Formula Catalog](../README.md) > [FC-451 — Default Probability Term Structure](FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-452](FC-452_EXPECTED_EXPOSURE.md) |

### Related Documents

- [FC-452](FC-452_EXPECTED_EXPOSURE.md)
- [FC-453](FC-453_CREDIT_VALUATION_ADJUSTMENT.md)
- [FC-454](FC-454_CVA_CAPITAL_CHARGE.md)
- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Credit Valuation Adjustment(CVA) 계산에 사용되는 **Default Probability Term Structure(기간구조별 부도확률)** 의 공식(Formulas)을 정의한다.

Default Probability Term Structure는 Hazard Rate로부터 Survival Function을 계산하고, 이를 이용하여 각 기간의 Marginal Default Probability를 산출하는 공식 체계이다.

본 문서는 Basel III CVA Framework의 Formula Specification으로 사용된다.

---

# 2. Formula Overview

기간구조별 부도확률 계산은 다음 순서를 따른다.

```text
Hazard Rate
      │
      ▼
Survival Function
      │
      ▼
Cumulative Default Probability
      │
      ▼
Marginal Default Probability
```

---

# 3. Formula Inputs

| Symbol       | Description                    |
| ------------ | ------------------------------ |
| (t)          | Time                           |
| (\lambda(t)) | Hazard Rate                    |
| (S(t))       | Survival Function              |
| (PD(t))      | Cumulative Default Probability |
| (PD_i)       | Marginal Default Probability   |

---

# 4. Formula 1 — Hazard Accumulation

누적 Hazard는 다음과 같이 정의한다.

[
H(t)
====

\int_0^t
\lambda(u),du
]

| Symbol       | Description       |
| ------------ | ----------------- |
| (H(t))       | Cumulative Hazard |
| (\lambda(u)) | Hazard Rate       |

---

# 5. Formula 2 — Survival Function

생존함수는 누적 Hazard를 이용하여 계산한다.

[
S(t)
====

\exp
\left(
------

H(t)
\right)
]

또는

[
S(t)
====

\exp
\left(
------

\int_0^t
\lambda(u),du
\right)
]

---

# 6. Formula 3 — Constant Hazard Rate

Hazard Rate가 일정한 경우

[
\lambda(t)=\lambda
]

이면

[
S(t)
====

e^{-\lambda t}
]

이다.

---

# 7. Formula 4 — Cumulative Default Probability

누적 부도확률은

[
PD(t)
=====

1-S(t)
]

이다.

이는 시점 (t) 이전에 부도가 발생할 확률을 의미한다.

---

# 8. Formula 5 — Marginal Default Probability

기간

[
[t_i,t_{i+1}]
]

에서의 부도확률은

[
PD_i
====

S(t_i)-S(t_{i+1})
]

이다.

이는 CVA 적분을 이산시간으로 근사할 때 가장 많이 사용되는 공식이다.

---

# 9. Formula Flow

```text
Hazard Rate λ(t)
        │
        ▼
Cumulative Hazard H(t)
        │
        ▼
Survival Function S(t)
        │
        ▼
Marginal Default Probability
        │
        ▼
Expected Credit Loss
```

---

# 10. Numerical Example

가정

* Constant Hazard Rate = 2%
* Time = 3 years

### Step 1

[
S(3)
====

# e^{-0.02\times3}

0.9418
]

### Step 2

[
PD(3)
=====

# 1-0.9418

0.0582
]

즉,

* 생존확률 = 94.18%
* 누적 부도확률 = 5.82%

이다.

---

# 11. Relationship with CVA

Default Probability Term Structure는 다음 계산에 직접 사용된다.

```text
Hazard Rate
      │
      ▼
Survival Function
      │
      ▼
Marginal Default Probability
      │
      ▼
Expected Exposure
      │
      ▼
LGD
      │
      ▼
Discount Factor
      │
      ▼
Credit Valuation Adjustment
```

각 기간의 Marginal Default Probability가 CVA 계산의 확률 가중치 역할을 한다.

---

# 12. Implementation Notes

구현 시 다음 사항을 고려한다.

* Hazard Rate는 시간의존 함수일 수 있다.
* Survival Function은 단조 감소해야 한다.
* (0 \leq S(t) \leq 1)
* (0 \leq PD(t) \leq 1)
* 모든 기간의 Marginal Default Probability 합은 최종 누적 부도확률과 일치해야 한다.

---

# 13. Validation Rules

다음 조건을 검증한다.

| Validation          | Rule             |
| ------------------- | ---------------- |
| Hazard Rate         | (\lambda(t)\ge0) |
| Survival Function   | 단조 감소            |
| Survival Function   | (S(0)=1)         |
| Default Probability | (PD(0)=0)        |
| Marginal PD         | 음수가 될 수 없음       |

---

# 14. Cross References

| Category                | Document                           |
| ----------------------- | ---------------------------------- |
| Mathematical Foundation | [MF-451_HAZARD_RATE](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)                 |
| Mathematical Foundation | [MF-452_SURVIVAL_FUNCTION](../../05_Mathematical_Foundation/05_CVA/MF-452_SURVIVAL_FUNCTION.md)           |
| Mathematical Foundation | [MF-453_DISCOUNT_FACTOR](../../05_Mathematical_Foundation/05_CVA/MF-453_DISCOUNT_FACTOR.md)             |
| Formula                 | [FC-452_EXPECTED_EXPOSURE](FC-452_EXPECTED_EXPOSURE.md)           |
| Formula                 | [FC-453_CREDIT_VALUATION_ADJUSTMENT](FC-453_CREDIT_VALUATION_ADJUSTMENT.md) |
| Formula                 | [FC-454_CVA_CAPITAL_CHARGE](FC-454_CVA_CAPITAL_CHARGE.md)          |
| Knowledge               | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)               |
| Implementation          | [IMP-451_CVA_IMPLEMENTATION](../../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)         |

---

# 15. Summary

Default Probability Term Structure는 Hazard Rate를 기반으로 Survival Function과 기간별 부도확률을 계산하는 공식 체계이다.

CVA 계산에서는 각 미래 기간의 Marginal Default Probability가 Expected Exposure에 곱해져 기대손실을 계산하며, 이후 LGD 및 Discount Factor를 적용하여 Credit Valuation Adjustment를 산출한다.

본 문서는 Bundle-005 Formula Catalog에서 모든 CVA 산식의 확률 구조를 정의하는 기본 공식 명세이다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
