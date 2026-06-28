# KB-252 — CVA Framework

---

# Document Information

| Item          | Value          |
| ------------- | -------------- |
| Document ID   | KB-252         |
| Document Name | CVA Framework  |
| Version       | 1.0.0          |
| Status        | Active         |
| Category      | Knowledge Base |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)     |
| Created       | 2026-06-27     |
| Last Updated  | 2026-06-27     |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Knowledge Base](../README.md) > [KB-252 — CVA Framework](KB-252_CVA_FRAMEWORK.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [KB-251](KB-251_CREDIT_VALUATION_ADJUSTMENT.md) |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [AN-251](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)
- [MF-451](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)
- [MF-452](../../05_Mathematical_Foundation/05_CVA/MF-452_SURVIVAL_FUNCTION.md)
- [MF-453](../../05_Mathematical_Foundation/05_CVA/MF-453_DISCOUNT_FACTOR.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III에서 정의하는 **Credit Valuation Adjustment (CVA) Framework**의 전체 구조를 설명한다.

CVA Framework는 거래상대방의 신용위험이 파생상품의 공정가치(Fair Value)에 미치는 영향을 평가하기 위한 통합적인 위험관리 프레임워크이다.

본 문서는 각 구성요소의 역할과 상호관계를 설명하며, 이후 Mathematical Foundation, Formula Catalog, Implementation Guide 및 Architecture Guide의 기반이 된다.

---

# 2. What is the CVA Framework?

CVA Framework는 거래상대방의 신용위험을 공정가치 평가에 반영하기 위한 일련의 모델과 계산 절차이다.

기본적인 흐름은 다음과 같다.

```text
Derivative Portfolio
        │
        ▼
Exposure Profile
        │
        ▼
Default Probability (PD)
        │
        ▼
Loss Given Default (LGD)
        │
        ▼
Discount Factor
        │
        ▼
Credit Valuation Adjustment
        │
        ▼
CVA Capital Charge
```

---

# 3. Objectives

CVA Framework의 목적은 다음과 같다.

* 거래상대방 신용위험의 시장가치 반영
* 파생상품 공정가치의 현실성 향상
* 신용스프레드 변동 위험 관리
* 규제자본 산출 지원
* 위험 민감도 기반 의사결정 지원

---

# 4. Core Components

CVA Framework는 다음 핵심 구성요소로 이루어진다.

| Component                   | Purpose                     |
| --------------------------- | --------------------------- |
| Exposure Profile            | 미래 노출(Expected Exposure) 추정 |
| Probability of Default (PD) | 거래상대방 부도확률 추정               |
| Loss Given Default (LGD)    | 부도 시 손실률 추정                 |
| Hazard Rate                 | 시간별 부도강도 모델링                |
| Survival Probability        | 생존확률 계산                     |
| Discount Factor             | 미래 현금흐름 현재가치 환산             |
| Credit Spread               | 시장 신용위험 반영                  |
| CVA                         | 신용위험에 따른 가치조정               |
| CVA Capital Charge          | 규제자본 산출                     |

---

# 5. Exposure Profile

Exposure Profile은 미래 시점별 거래상대방에 대한 위험노출을 나타낸다.

대표적인 지표는 다음과 같다.

* Current Exposure
* Expected Exposure (EE)
* Expected Positive Exposure (EPE)
* Effective EPE
* Exposure at Default (EAD)

SA-CCR는 이러한 노출 계산을 위한 표준 접근법을 제공한다.

---

# 6. Default Risk Component

거래상대방의 부도위험은 다음 요소로 표현된다.

```text
Credit Rating
        │
        ▼
Probability of Default
        │
        ▼
Hazard Rate
        │
        ▼
Survival Probability
```

Hazard Rate는 시간에 따른 순간 부도강도를 나타내며, Survival Probability는 특정 시점까지 생존할 확률을 의미한다.

---

# 7. Recovery Component

부도가 발생하더라도 모든 금액이 손실되는 것은 아니다.

Recovery Component는 다음 관계를 따른다.

```text
Recovery Rate

↓

Loss Given Default

LGD = 1 − Recovery Rate
```

LGD는 CVA 계산에서 손실 규모를 결정하는 핵심 요소이다.

---

# 8. Time Value Component

미래 손실은 현재가치로 할인되어야 한다.

이를 위해 Discount Factor를 사용한다.

```text
Future Loss
        │
        ▼
Discount Factor
        │
        ▼
Present Value
```

할인율은 일반적으로 무위험금리 곡선(Risk-Free Yield Curve)을 기반으로 산출한다.

---

# 9. Credit Spread Component

CVA는 거래상대방의 신용스프레드 변화를 직접적으로 반영한다.

```text
Credit Spread

↓

Credit Quality

↓

Market Value

↓

CVA
```

신용스프레드 확대는 거래상대방 신용도가 악화되었음을 의미하며, 일반적으로 CVA를 증가시키는 방향으로 작용한다.

---

# 10. Integrated Framework

각 구성요소를 통합하면 CVA Framework는 다음과 같이 표현할 수 있다.

```text
Trade Portfolio
        │
        ▼
Exposure Simulation
        │
        ▼
Expected Exposure
        │
        ▼
PD & Hazard Rate
        │
        ▼
Survival Probability
        │
        ▼
LGD
        │
        ▼
Discount Factor
        │
        ▼
Expected Credit Loss
        │
        ▼
Credit Valuation Adjustment
        │
        ▼
Regulatory Capital
```

---

# 11. Relationship with SA-CCR

SA-CCR와 CVA는 서로 보완적인 관계를 가진다.

```text
Trade Portfolio
        │
        ├───────────────┐
        ▼               ▼
SA-CCR              Market Data
        │               │
        ▼               ▼
Exposure        Credit Spread
        │               │
        └──────┬────────┘
               ▼
        CVA Framework
               │
               ▼
      CVA Capital Charge
```

* SA-CCR는 위험노출(EAD)을 계산한다.
* CVA는 그 노출의 신용가치 변동을 평가한다.

---

# 12. Relationship with IFRS 9

CVA와 IFRS 9 Expected Credit Loss(ECL)는 모두 신용위험을 다루지만 목적이 다르다.

| Item | IFRS 9 ECL           | Basel III CVA         |
| ---- | -------------------- | --------------------- |
| 목적   | 회계상 손실 인식            | 규제자본 산출               |
| 대상   | 금융자산                 | 파생상품                  |
| 초점   | Expected Credit Loss | Fair Value Adjustment |
| 기준   | 회계기준                 | 건전성 규제                |

---

# 13. Knowledge Dependency

CVA Framework를 이해하기 위해 필요한 선행 개념은 다음과 같다.

```text
RL-150
CVA Overview
        │
        ▼
AN-251
Why CVA Was Introduced
        │
        ▼
KB-252
CVA Framework
        │
        ├─────────────┬─────────────┬─────────────┐
        ▼             ▼             ▼             ▼
MF-451        MF-452        MF-453        FC-451~
Hazard Rate   Survival      Discount      CVA Formula
              Probability   Factor
```

---

# 14. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Reference               | [RL-150_CVA_OVERVIEW](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)                       |
| Analysis                | [AN-251_WHY_CVA_WAS_INTRODUCED](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)             |
| Mathematical Foundation | [MF-451_HAZARD_RATE](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)                        |
| Mathematical Foundation | [MF-452_SURVIVAL_FUNCTION](../../05_Mathematical_Foundation/05_CVA/MF-452_SURVIVAL_FUNCTION.md)                  |
| Mathematical Foundation | [MF-453_DISCOUNT_FACTOR](../../05_Mathematical_Foundation/05_CVA/MF-453_DISCOUNT_FACTOR.md)                    |
| Formula                 | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula                 | [FC-452_EXPECTED_EXPOSURE](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)                  |
| Formula                 | [FC-453_CREDIT_VALUATION_ADJUSTMENT](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Formula                 | [FC-454_CVA_CAPITAL_CHARGE](../../04_Formula_Catalog/05_CVA/FC-454_CVA_CAPITAL_CHARGE.md)                 |
| Implementation          | [IMP-451_CVA_IMPLEMENTATION](../../06_Implementation_Guide/05_CVA/IMP-451_CVA_IMPLEMENTATION.md)                |
| Architecture            | [ARCH-751_CVA_ARCHITECTURE](../../07_Architecture/05_CVA/ARCH-751_CVA_ARCHITECTURE.md)                 |

---

# 15. Summary

CVA Framework는 거래상대방 신용위험을 파생상품의 공정가치와 규제자본에 반영하기 위한 통합적인 위험관리 체계이다.

Framework는 **Exposure, PD, Hazard Rate, Survival Probability, LGD, Discount Factor, Credit Spread**를 결합하여 Credit Valuation Adjustment를 산출하며, Basel III의 거래상대방 신용위험 관리에서 핵심적인 역할을 수행한다.

이 Framework는 이후 Mathematical Foundation에서 각 수학적 개념을 정의하고, Formula Catalog에서 산식을 기술하며, Implementation Guide와 Architecture Guide에서 시스템 구현으로 확장된다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
