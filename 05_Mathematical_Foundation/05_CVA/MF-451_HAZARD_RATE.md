# MF-451 — Hazard Rate

---

# Document Information

| Item          | Value                   |
| ------------- | ----------------------- |
| Document ID   | MF-451                  |
| Document Name | Hazard Rate             |
| Version       | 1.0.0                   |
| Status        | Active                  |
| Category      | Mathematical Foundation |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)              |
| Created       | 2026-06-27              |
| Last Updated  | 2026-06-27              |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Mathematical Foundation](../README.md) > [MF-451 — Hazard Rate](MF-451_HAZARD_RATE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Mathematical Foundation](../README.md) |
| ➡ Next | [MF-452](MF-452_SURVIVAL_FUNCTION.md) |

### Related Documents

- [FC-451](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)
- [FC-453](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)
- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
- [KB-252](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Credit Valuation Adjustment(CVA) 계산의 핵심이 되는 **Hazard Rate(위험률, 부도강도)** 의 수학적 개념과 금융적 의미를 설명한다.

Hazard Rate는 특정 시점까지 생존한 거래상대방이 **바로 다음 순간 부도에 이를 조건부 확률의 강도(Intensity)** 를 나타낸다.

이는 Survival Function, Default Probability, Credit Spread 및 CVA 계산의 기초가 되는 가장 중요한 수학적 개념이다.

---

# 2. Why Hazard Rate?

거래상대방 신용위험은 단순히 "부도확률(PD)" 하나로 표현하기 어렵다.

예를 들어,

* A기업은 향후 1년 동안 매우 안정적일 수 있다.
* 그러나 5년 이후에는 부도위험이 크게 증가할 수 있다.

따라서 시간에 따라 변화하는 부도위험을 모델링해야 한다.

Hazard Rate는 이러한 시간의존적(Default Intensity) 위험을 표현하기 위해 도입되었다.

---

# 3. Intuitive Meaning

Hazard Rate는 다음 질문에 대한 답이다.

> **"지금까지 살아남은 거래상대방이 바로 다음 순간 부도날 가능성은 얼마나 되는가?"**

즉,

```text
Already Survived Until Time t
              │
              ▼
 Default During Next Instant
```

을 나타낸다.

중요한 점은 **조건부(Conditional)** 개념이라는 것이다.

이미 부도나지 않았다는 사실을 전제로 미래의 순간 부도강도를 측정한다.

---

# 4. Mathematical Definition

Hazard Rate는 다음과 같이 정의된다.

[
\lambda(t)
==========

\lim_{\Delta t\rightarrow0}
\frac{
P(t<T\le t+\Delta t \mid T>t)
}{
\Delta t
}
]

여기서

| Symbol       | Meaning      |
| ------------ | ------------ |
| (T)          | Default Time |
| (t)          | Current Time |
| (\lambda(t)) | Hazard Rate  |

Hazard Rate는 **순간적인 조건부 부도강도**를 의미한다.

---

# 5. Relationship with Survival Probability

Hazard Rate와 Survival Probability는 직접 연결된다.

Survival Function은

[
S(t)=P(T>t)
]

이며,

Hazard Rate와의 관계는

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

이다.

즉,

```text
Hazard Rate
      │
      ▼
Accumulated Hazard
      │
      ▼
Survival Probability
```

의 관계를 가진다.

---

# 6. Constant Hazard Rate

Hazard Rate가 일정하다고 가정하면

[
\lambda(t)=\lambda
]

이고,

Survival Probability는

[
S(t)=e^{-\lambda t}
]

가 된다.

이 경우 부도시간은 **지수분포(Exponential Distribution)** 를 따른다.

---

# 7. Relationship with Default Probability

누적 부도확률은

[
PD(t)
=====

1-S(t)
]

이므로,

[
PD(t)
=====

1-
e^{-\lambda t}
]

이다.

관계는 다음과 같다.

```text
Hazard Rate
      │
      ▼
Survival Probability
      │
      ▼
Default Probability
```

---

# 8. Hazard Rate and Credit Spread

시장에서는 Hazard Rate를 직접 관측하지 않는다.

대신 CDS Spread와 회사채 스프레드 등을 이용하여 추정한다.

단순화된 관계는

[
\lambda
\approx
\frac{\text{Credit Spread}}{\text{LGD}}
]

이다.

여기서

* Credit Spread 증가
* LGD 일정

이면

Hazard Rate도 증가한다.

즉,

```text
Credit Spread ↑
        │
        ▼
Hazard Rate ↑
        │
        ▼
Default Probability ↑
```

이다.

---

# 9. Hazard Rate in CVA

CVA 계산에서 Hazard Rate는 시간별 부도확률을 생성하는 핵심 입력값이다.

전체 흐름은 다음과 같다.

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
Expected Exposure
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

Hazard Rate가 커질수록 동일한 Exposure에서도 CVA는 증가한다.

---

# 10. Practical Interpretation

Hazard Rate를 직관적으로 이해하면 다음과 같다.

| Hazard Rate | Interpretation    |
| ----------- | ----------------- |
| 매우 낮음       | 우량 거래상대방, 부도강도 낮음 |
| 낮음          | 투자적격 수준           |
| 보통          | 중간 수준 신용위험        |
| 높음          | 고위험 거래상대방         |
| 매우 높음       | 부도 가능성이 매우 큰 상태   |

중요한 점은 Hazard Rate 자체는 **확률이 아니라 강도(Intensity)** 라는 것이다.

---

# 11. Relationship with Other Mathematical Concepts

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
Expected Loss
      │
      ▼
Credit Valuation Adjustment
```

Hazard Rate는 CVA 수학체계의 출발점이다.

---

# 12. Applications

Hazard Rate는 다음 분야에서 활용된다.

* Credit Valuation Adjustment (CVA)
* Debit Valuation Adjustment (DVA)
* Bilateral Valuation Adjustment (BVA)
* Expected Credit Loss (ECL) 모델
* CDS Pricing
* Credit Portfolio Modeling
* Reduced-Form Credit Risk Models

---

# 13. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Reference               | [RL-150_CVA_OVERVIEW](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)                       |
| Knowledge               | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Analysis                | [AN-251_WHY_CVA_WAS_INTRODUCED](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)             |
| Mathematical Foundation | [MF-452_SURVIVAL_FUNCTION](MF-452_SURVIVAL_FUNCTION.md)                  |
| Mathematical Foundation | [MF-453_DISCOUNT_FACTOR](MF-453_DISCOUNT_FACTOR.md)                    |
| Formula                 | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula                 | [FC-453_CREDIT_VALUATION_ADJUSTMENT](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Implementation          | [IMP-451_CVA_IMPLEMENTATION](../../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)                |

---

# 14. Summary

Hazard Rate는 거래상대방의 **순간 조건부 부도강도**를 나타내는 금융수학의 핵심 개념이다.

Hazard Rate는 단순한 부도확률(PD)이 아니라 시간에 따라 변화하는 신용위험을 모델링하는 함수이며, Survival Function과 Default Probability를 연결하는 중심 요소이다.

CVA에서는 Hazard Rate를 기반으로 시간별 부도확률을 계산하고, 이를 Expected Exposure, LGD 및 Discount Factor와 결합하여 Credit Valuation Adjustment를 산출한다.

따라서 Hazard Rate는 CVA뿐 아니라 현대 신용위험 모델링 전반의 수학적 기반을 제공하는 핵심 Mathematical Foundation이다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
