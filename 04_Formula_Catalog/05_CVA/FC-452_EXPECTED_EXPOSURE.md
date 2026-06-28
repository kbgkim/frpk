# FC-452 — Expected Exposure

---

# Document Information

| Item          | Value             |
| ------------- | ----------------- |
| Document ID   | FC-452            |
| Document Name | Expected Exposure |
| Version       | 1.0.0             |
| Status        | Active            |
| Category      | Formula Catalog   |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)        |
| Created       | 2026-06-27        |
| Last Updated  | 2026-06-27        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Formula Catalog](../README.md) > [FC-452 — Expected Exposure](FC-452_EXPECTED_EXPOSURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FC-451](FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-453](FC-453_CREDIT_VALUATION_ADJUSTMENT.md) |

### Related Documents

- [FC-451](FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)
- [FC-453](FC-453_CREDIT_VALUATION_ADJUSTMENT.md)
- [FC-454](FC-454_CVA_CAPITAL_CHARGE.md)
- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Credit Valuation Adjustment(CVA) 계산에 사용되는 **Expected Exposure (EE)** 의 공식(Formulas)과 계산 계약을 정의한다.

Expected Exposure는 미래 특정 시점에서 거래상대방에 대해 예상되는 평균 양(+)의 익스포저를 의미하며, CVA 계산에서 기간별 신용손실을 산출하기 위한 핵심 입력이다.

---

# 2. Business Purpose

Expected Exposure는 거래상대방이 미래에 부도할 경우 금융기관이 실제로 노출될 가능성이 있는 금액을 추정하기 위해 사용된다.

주요 목적은 다음과 같다.

* 미래 노출(Profile) 추정
* 거래상대방 신용위험 정량화
* CVA 계산 입력 제공
* Exposure Profile 생성
* SA-CCR 및 Monte Carlo 기반 노출 분석 지원

---

# 3. Regulatory Perspective

Basel III에서는 거래상대방 신용위험을 시간에 따른 Exposure Profile로 평가한다.

Expected Exposure는

* CVA Framework
* SA-CCR
* Internal Model Method (IMM)

등에서 공통적으로 사용되는 핵심 개념이다.

---

# 4. Mathematical Definition

시점 (t)에서의 Expected Exposure는 다음과 같이 정의한다.

[
EE(t)=E[\max(V(t),0)]
]

여기서

| Symbol     | Description            |
| ---------- | ---------------------- |
| (V(t))     | Portfolio Market Value |
| (EE(t))    | Expected Exposure      |
| (E[\cdot]) | Expectation Operator   |

즉, 미래 시점의 시장가치가 음수인 경우는 제외하고, 양(+)의 노출만 평균하여 계산한다.

---

# 5. Formula Interpretation

Expected Exposure는 거래상대방이 부도할 경우 금융기관이 회수하지 못할 가능성이 있는 평균 노출액을 나타낸다.

```text
Future Portfolio Value

        │

        ▼

Positive Exposure

        │

        ▼

Expected Exposure
```

Exposure가 클수록 동일한 부도확률에서도 기대손실은 증가한다.

---

# 6. Input Contract

| Input                       | Required | Description      |
| --------------------------- | :------: | ---------------- |
| Portfolio Market Value Path |     ✔    | 미래 시장가치 경로       |
| Evaluation Time             |     ✔    | 평가 시점            |
| Simulation Scenario         |     △    | Monte Carlo 시나리오 |
| Netting Set                 |     △    | 상계 계약            |
| Collateral Information      |     △    | 담보 정보            |

---

# 7. Computation Contract

Expected Exposure 계산 절차는 다음과 같다.

```text
Future Portfolio Value
        │
        ▼
Positive Exposure
        │
        ▼
Scenario Averaging
        │
        ▼
Expected Exposure
```

Monte Carlo 기반 계산에서는 각 시나리오의 Positive Exposure를 평균한다.

---

# 8. Output Contract

| Output            | Description       |
| ----------------- | ----------------- |
| Expected Exposure | 시점별 평균 양(+)의 익스포저 |

단위는 일반적으로 거래 통화(Currency) 기준이다.

---

# 9. Formula Engine Model

```text
Exposure Generator
        │
        ▼
Positive Exposure Filter
        │
        ▼
Expectation Calculator
        │
        ▼
Exposure Profile
```

Formula Engine은 논리적으로 Exposure 생성과 평균 계산을 분리한다.

---

# 10. Formula Classification

| Classification   | Value                                |
| ---------------- | ------------------------------------ |
| Formula Type     | Definition                           |
| Formula Nature   | Deterministic (주어진 Exposure Path 기준) |
| Formula Category | Credit Risk                          |
| Basel Component  | CVA                                  |

---

# 11. Formula Dependency

### Depends On

* Exposure Profile
* Portfolio Market Value

### Produces

* Expected Exposure Curve

### Consumed By

* FC-453_CREDIT_VALUATION_ADJUSTMENT

의존성은 다음과 같다.

```text
Portfolio Value
        │
        ▼
Expected Exposure
        │
        ▼
Credit Valuation Adjustment
```

---

# 12. Computational Characteristics

| Property              | Value                      |
| --------------------- | -------------------------- |
| Time Dependency       | Yes                        |
| Closed Form           | No (일반적으로)                 |
| Numerical Integration | Optional                   |
| Monte Carlo Required  | Optional                   |
| Matrix Operation      | No                         |
| Vector Operation      | Yes                        |
| Parallelizable        | Yes                        |
| Complexity            | O(n × m) (Time × Scenario) |

---

# 13. Relationship with FRKP

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
Default Probability
      │
      ▼
FC-452
Expected Exposure
      │
      ▼
FC-453
Credit Valuation Adjustment
```

Expected Exposure는 Default Probability와 결합되어 기간별 기대손실을 계산한다.

---

# 14. Numerical Example

가정

* 미래 시점의 시나리오별 Portfolio Value

| Scenario | Portfolio Value |
| -------- | --------------: |
| 1        |             120 |
| 2        |              80 |
| 3        |             -30 |
| 4        |             150 |

Positive Exposure만 고려하면

| Scenario | Positive Exposure |
| -------- | ----------------: |
| 1        |               120 |
| 2        |                80 |
| 3        |                 0 |
| 4        |               150 |

따라서

[
EE=\frac{120+80+0+150}{4}=87.5
]

Expected Exposure는 **87.5**가 된다.

---

# 15. Validation Rules

다음 조건을 만족해야 한다.

| Validation        | Rule        |
| ----------------- | ----------- |
| Expected Exposure | (EE(t)\ge0) |
| Positive Exposure | 음수 제거       |
| Scenario Count    | 1 이상        |
| Currency          | 모든 입력 동일 통화 |

---

# 16. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Mathematical Foundation | [MF-451_HAZARD_RATE](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)                        |
| Mathematical Foundation | [MF-452_SURVIVAL_FUNCTION](../../05_Mathematical_Foundation/05_CVA/MF-452_SURVIVAL_FUNCTION.md)                  |
| Mathematical Foundation | [MF-453_DISCOUNT_FACTOR](../../05_Mathematical_Foundation/05_CVA/MF-453_DISCOUNT_FACTOR.md)                    |
| Formula                 | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula                 | [FC-453_CREDIT_VALUATION_ADJUSTMENT](FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Formula                 | [FC-454_CVA_CAPITAL_CHARGE](FC-454_CVA_CAPITAL_CHARGE.md)                 |
| Knowledge               | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Implementation          | [IMP-451_CVA_IMPLEMENTATION](../../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)                |

---

# 17. Summary

Expected Exposure는 미래 시점에서 거래상대방에 대해 예상되는 평균 양(+)의 익스포저를 나타내는 핵심 산식이다.

CVA Framework에서는 기간별 Default Probability와 결합하여 기대신용손실을 계산하며, 이후 LGD 및 Discount Factor를 적용하여 Credit Valuation Adjustment를 산출한다.

Expected Exposure는 CVA뿐 아니라 SA-CCR, Internal Model Method, Exposure Simulation 등 거래상대방 신용위험 모델 전반에서 공통적으로 활용되는 핵심 Formula Asset이다.

---

# 18. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
