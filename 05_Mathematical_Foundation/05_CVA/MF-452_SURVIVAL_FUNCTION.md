# MF-452 — Survival Function

---

# Document Information

| Item          | Value                   |
| ------------- | ----------------------- |
| Document ID   | MF-452                  |
| Document Name | Survival Function       |
| Version       | 1.0.0                   |
| Status        | Active                  |
| Category      | Mathematical Foundation |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)              |
| Created       | 2026-06-27              |
| Last Updated  | 2026-06-27              |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Mathematical Foundation](../README.md) > [MF-452 — Survival Function](MF-452_SURVIVAL_FUNCTION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [MF-451](MF-451_HAZARD_RATE.md) |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Mathematical Foundation](../README.md) |
| ➡ Next | [MF-453](MF-453_DISCOUNT_FACTOR.md) |

### Related Documents

- [FC-451](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)
- [FC-452](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)
- [FC-453](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)
- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Credit Valuation Adjustment(CVA)와 Reduced-Form Credit Risk Model에서 사용되는 **Survival Function(생존함수)** 의 수학적 정의와 금융적 의미를 설명한다.

Survival Function은 특정 시점까지 거래상대방이 부도(Default)하지 않고 생존할 확률을 나타내며, Hazard Rate와 함께 신용위험 모델링의 핵심 기반을 제공한다.

---

# 2. Why Survival Function?

Hazard Rate는 **순간적인 부도강도(Intensity)** 를 나타낸다.

그러나 실제 CVA 계산에서는 특정 시점까지 거래상대방이 생존할 확률이 필요하다.

즉,

```text
Hazard Rate
      │
      ▼
Survival Function
      │
      ▼
Default Probability
      │
      ▼
Expected Credit Loss
      │
      ▼
CVA
```

의 흐름으로 계산이 진행된다.

---

# 3. Definition

Survival Function은 다음과 같이 정의된다.

[
S(t)=P(T>t)
]

여기서

| Symbol | Meaning           |
| ------ | ----------------- |
| (T)    | Default Time      |
| (t)    | Time              |
| (S(t)) | Survival Function |

즉,

**"거래상대방이 시점 (t)까지 부도나지 않을 확률"**

을 의미한다.

---

# 4. Intuitive Meaning

예를 들어

```text
Today
 │
 │──────────────► 5 Years
```

5년 후까지 생존할 확률이

```text
S(5)=97%
```

라면

거래상대방은 향후 5년 동안 97%의 확률로 생존한다는 의미이다.

따라서

```text
1-S(5)=3%
```

는 5년 이내 누적 부도확률이 된다.

---

# 5. Relationship with Hazard Rate

Survival Function은 Hazard Rate의 누적효과를 반영한다.

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

여기서

* (\lambda(t)) : Hazard Rate
* (S(t)) : Survival Function

즉,

```text
Hazard Rate
      │
      ▼
Cumulative Hazard
      │
      ▼
Survival Function
```

으로 계산된다.

---

# 6. Constant Hazard Rate

Hazard Rate가 일정한 경우

[
\lambda(t)=\lambda
]

이므로

[
S(t)=e^{-\lambda t}
]

이 된다.

이는 지수감쇠(Exponential Decay)의 형태를 가지며,

시간이 증가할수록 생존확률은 점진적으로 감소한다.

---

# 7. Relationship with Default Probability

누적 부도확률은

[
PD(t)=1-S(t)
]

이다.

따라서

| Survival Function | Default Probability |
| ----------------- | ------------------- |
| 100%              | 0%                  |
| 99%               | 1%                  |
| 97%               | 3%                  |
| 90%               | 10%                 |

이다.

---

# 8. Marginal Default Probability

CVA는 각 기간별 부도확률을 사용한다.

구간

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

즉,

```text
S(0)

↓

S(1)

↓

S(2)

↓

S(3)
```

각 구간의 감소량이 해당 기간의 부도확률이 된다.

---

# 9. Survival Function in CVA

CVA에서는 각 미래 시점의 Exposure에 Survival Function을 결합한다.

```text
Expected Exposure
        │
        ▼
Survival Function
        │
        ▼
Marginal Default Probability
        │
        ▼
LGD
        │
        ▼
Discount Factor
        │
        ▼
CVA
```

Survival Function은 미래 현금흐름에 적용되는 부도위험을 시간축에서 표현하는 역할을 한다.

---

# 10. Relationship with Credit Spread

시장에서는 Survival Function을 직접 관측하지 않는다.

대신

* CDS Spread
* Bond Spread
* Hazard Rate

등으로부터 역산(Bootstrap)한다.

```text
Credit Spread

↓

Hazard Rate

↓

Survival Function
```

---

# 11. Relationship with Expected Exposure

CVA 계산에서는

Exposure와 Survival Function이 함께 사용된다.

```text
Time

↓

Exposure(t)

↓

Survival(t)

↓

Incremental Default Probability

↓

Expected Loss
```

생존확률이 낮아질수록 동일한 Exposure에서도 기대손실은 증가한다.

---

# 12. Applications

Survival Function은 다음 분야에서 활용된다.

* Credit Valuation Adjustment (CVA)
* Debit Valuation Adjustment (DVA)
* Bilateral Valuation Adjustment (BVA)
* CDS Pricing
* Credit Portfolio Models
* Expected Credit Loss (ECL)
* Counterparty Credit Risk Models

---

# 13. Relationship with Other Mathematical Concepts

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
Discount Factor
      │
      ▼
Credit Valuation Adjustment
```

Survival Function은 Hazard Rate와 Default Probability를 연결하는 핵심 함수이다.

---

# 14. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Reference               | [RL-150_CVA_OVERVIEW](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)                       |
| Knowledge               | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Mathematical Foundation | [MF-451_HAZARD_RATE](MF-451_HAZARD_RATE.md)                        |
| Mathematical Foundation | [MF-453_DISCOUNT_FACTOR](MF-453_DISCOUNT_FACTOR.md)                    |
| Formula                 | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula                 | [FC-452_EXPECTED_EXPOSURE](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)                  |
| Formula                 | [FC-453_CREDIT_VALUATION_ADJUSTMENT](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |

---

# 15. Summary

Survival Function은 거래상대방이 특정 시점까지 부도나지 않을 확률을 나타내는 함수이다.

Hazard Rate를 누적하여 계산되며, Default Probability와 Expected Exposure를 연결하는 핵심 요소이다.

CVA에서는 Survival Function을 이용하여 각 미래 시점의 구간별 부도확률(Marginal Default Probability)을 계산하고, 이를 Exposure, LGD 및 Discount Factor와 결합하여 Credit Valuation Adjustment를 산출한다.

따라서 Survival Function은 Hazard Rate와 함께 현대 신용위험 모델의 가장 중요한 수학적 기반 중 하나이다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
