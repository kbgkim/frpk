# MF-453 — Discount Factor

---

# Document Information

| Item          | Value                   |
| ------------- | ----------------------- |
| Document ID   | MF-453                  |
| Document Name | Discount Factor         |
| Version       | 1.0.0                   |
| Status        | Active                  |
| Category      | Mathematical Foundation |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)              |
| Created       | 2026-06-27              |
| Last Updated  | 2026-06-27              |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Mathematical Foundation](../README.md) > [MF-453 — Discount Factor](MF-453_DISCOUNT_FACTOR.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [MF-452](MF-452_SURVIVAL_FUNCTION.md) |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Mathematical Foundation](../README.md) |
| ➡ Next | None |

### Related Documents

- [FC-451](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)
- [FC-452](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)
- [FC-453](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)
- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Credit Valuation Adjustment(CVA), 파생상품 평가 및 금융공학 전반에서 사용되는 **Discount Factor(할인계수)** 의 수학적 정의와 금융적 의미를 설명한다.

Discount Factor는 미래 현금흐름(Future Cash Flow)을 현재가치(Present Value)로 환산하는 계수이며, 시간가치(Time Value of Money)를 정량적으로 표현하는 핵심 개념이다.

---

# 2. Why Discount Factor?

오늘의 100원과 5년 후의 100원은 동일한 가치가 아니다.

그 이유는

* 이자수익
* 투자기회
* 인플레이션
* 시장금리
* 신용위험

등 때문이다.

따라서 미래 손실은 반드시 현재가치로 할인해야 한다.

```text
Future Cash Flow
        │
        ▼
Discount Factor
        │
        ▼
Present Value
```

---

# 3. Definition

Discount Factor는 미래의 현금흐름을 현재가치로 환산하는 비율이다.

현재가치는 다음과 같이 계산된다.

[
PV = DF(t)\times FV
]

여기서

| Symbol  | Meaning         |
| ------- | --------------- |
| (PV)    | Present Value   |
| (FV)    | Future Value    |
| (DF(t)) | Discount Factor |
| (t)     | Time            |

---

# 4. Continuous Compounding

연속복리(Continuous Compounding)를 사용하는 경우

Discount Factor는

[
DF(t)=e^{-rt}
]

로 표현된다.

여기서

| Symbol | Meaning                               |
| ------ | ------------------------------------- |
| (r)    | Continuously Compounded Interest Rate |
| (t)    | Time                                  |

시간이 증가하거나 할인율이 증가할수록 Discount Factor는 감소한다.

---

# 5. Discrete Compounding

연복리 또는 기간복리를 사용하는 경우

[
DF(t)=\frac{1}{(1+r)^t}
]

를 사용한다.

실무에서는

* 연복리
* 반기복리
* 분기복리
* 월복리
* 연속복리

등이 사용되며, 파생상품 가격평가에서는 연속복리가 널리 사용된다.

---

# 6. Discount Curve

실제 시장에서는 하나의 금리를 사용하는 것이 아니라 만기별 금리곡선을 사용한다.

```text
Market Quotes
        │
        ▼
Yield Curve
        │
        ▼
Discount Curve
        │
        ▼
Discount Factor
```

Discount Curve는 각 만기별 Discount Factor를 제공한다.

---

# 7. Relationship with Yield Curve

Discount Factor는 Yield Curve에서 직접 계산된다.

```text
Yield Curve
      │
      ▼
Spot Rate
      │
      ▼
Discount Factor
```

만기가 길수록 일반적으로 Discount Factor는 작아진다.

---

# 8. Risk-Free Discounting

Basel III와 현대 파생상품 평가에서는 일반적으로 **무위험 할인(Risk-Free Discounting)** 을 사용한다.

대표적으로 다음 금리곡선을 활용한다.

* OIS Curve
* SOFR Curve
* €STR Curve
* SONIA Curve

과거에는 LIBOR 기반 할인도 사용되었으나, 현재는 대부분 OIS 기반 할인이 표준이다.

---

# 9. Discount Factor in CVA

CVA는 미래 예상손실을 현재가치로 환산한다.

계산 흐름은 다음과 같다.

```text
Expected Exposure
        │
        ▼
Marginal Default Probability
        │
        ▼
LGD
        │
        ▼
Future Expected Loss
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

Discount Factor가 없다면 미래 손실을 현재 기준으로 비교할 수 없다.

---

# 10. Relationship with Hazard Rate

Hazard Rate는 부도위험을 모델링하고,

Discount Factor는 시간가치를 모델링한다.

```text
Hazard Rate
      │
      ▼
Survival Function
      │
      ▼
Default Probability

Discount Factor
      │
      ▼
Present Value

↓

Combined

↓

CVA
```

두 요소는 서로 독립적이지만 함께 사용된다.

---

# 11. Practical Interpretation

Discount Factor는 다음과 같이 해석할 수 있다.

| Discount Factor | Interpretation |
| --------------: | -------------- |
|           1.000 | 현재 시점          |
|           0.980 | 현재가치가 약 98%    |
|           0.950 | 현재가치가 약 95%    |
|           0.900 | 현재가치가 약 90%    |
|           0.800 | 장기 현금흐름        |

Discount Factor가 작을수록 현재가치는 감소한다.

---

# 12. Applications

Discount Factor는 다음 분야에서 활용된다.

* Credit Valuation Adjustment (CVA)
* Debit Valuation Adjustment (DVA)
* Bilateral Valuation Adjustment (BVA)
* Derivatives Pricing
* Bond Valuation
* Interest Rate Swaps
* IFRS 9 Expected Credit Loss
* Discounted Cash Flow (DCF)
* XVA Framework

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
LGD
      │
      ▼
Discount Factor
      │
      ▼
Present Value of Expected Loss
      │
      ▼
Credit Valuation Adjustment
```

Discount Factor는 미래 기대손실을 현재가치로 환산하는 마지막 수학적 구성요소이다.

---

# 14. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Reference               | [RL-150_CVA_OVERVIEW](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)                       |
| Knowledge               | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Analysis                | [AN-251_WHY_CVA_WAS_INTRODUCED](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)             |
| Mathematical Foundation | [MF-451_HAZARD_RATE](MF-451_HAZARD_RATE.md)                        |
| Mathematical Foundation | [MF-452_SURVIVAL_FUNCTION](MF-452_SURVIVAL_FUNCTION.md)                  |
| Formula                 | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula                 | [FC-452_EXPECTED_EXPOSURE](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)                  |
| Formula                 | [FC-453_CREDIT_VALUATION_ADJUSTMENT](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Implementation          | [IMP-451_CVA_IMPLEMENTATION](../../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)                |

---

# 15. Summary

Discount Factor는 미래 현금흐름과 미래 기대손실을 현재가치로 환산하기 위한 핵심 수학적 개념이다.

CVA에서는 Hazard Rate가 부도위험을 모델링하고, Survival Function이 생존확률을 계산하며, Discount Factor가 시간가치를 반영하여 미래 기대손실을 현재가치로 변환한다.

따라서 Discount Factor는 Hazard Rate 및 Survival Function과 함께 CVA Mathematical Foundation의 세 가지 핵심 축을 구성한다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
