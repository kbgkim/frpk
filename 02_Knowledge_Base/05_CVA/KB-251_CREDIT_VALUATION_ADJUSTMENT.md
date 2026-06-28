# KB-251 — Credit Valuation Adjustment

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Knowledge Base](../README.md) > [KB-251 — Credit Valuation Adjustment](KB-251_CREDIT_VALUATION_ADJUSTMENT.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | [KB-252](KB-252_CVA_FRAMEWORK.md) |

### Related Documents

- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [AN-251](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)
- [KB-252](KB-252_CVA_FRAMEWORK.md)
- [MF-451](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)
- [MF-452](../../05_Mathematical_Foundation/05_CVA/MF-452_SURVIVAL_FUNCTION.md)
<!-- FRKP-NAV-END -->

## Document Information

| Item            | Value                       |
| --------------- | --------------------------- |
| Document ID     | KB-251                      |
| Document Name   | Credit Valuation Adjustment |
| Version         | 1.0.0                       |
| Status          | Active                      |
| Category        | Knowledge Base              |
| Parent Bundle   | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)                  |
| Parent Standard | [FRKP-DOC-001](../../00_Project_Management/Governance/Standards/FRKP-DOC-001_DOCUMENT_STANDARD.md)                |
| Created         | 2026-06-27                  |
| Last Updated    | 2026-06-27                  |

---

# 1. Purpose

본 문서는 **Credit Valuation Adjustment(CVA)** 의 개념적 모델(Conceptual Model)을 설명한다.

CVA가 무엇인지 정의하는 것을 넘어,

* 왜 필요한가
* 어떤 위험을 반영하는가
* Basel III에서 어떤 역할을 하는가
* SA-CCR 및 XVA와 어떻게 연결되는가

를 이해하는 것을 목적으로 한다.

본 문서는 계산 방법이 아닌 **개념과 구조**를 다룬다.

---

# 2. Scope

## Included

* CVA의 정의
* 거래상대방 신용위험과의 관계
* 경제적 의미
* 공정가치 조정
* Basel III에서의 역할
* SA-CCR와의 관계
* XVA Framework

## Excluded

다음 내용은 별도 문서에서 다룬다.

* Hazard Rate
* Survival Function
* Discount Factor
* Monte Carlo Simulation
* CVA Capital Charge
* 수학적 유도 및 계산식

---

# 3. Concept

Credit Valuation Adjustment(CVA)는 **거래상대방의 신용위험을 반영하여 파생상품의 공정가치를 조정하는 메커니즘**이다.

거래상대방이 미래에 계약을 이행하지 못할 가능성이 존재한다면, 해당 계약의 현재 가치는 무위험(Risk-Free) 가치보다 낮아야 한다.

즉,

```text
Risk-Free Value

↓

Counterparty Credit Risk

↓

Credit Valuation Adjustment

↓

Risk-Adjusted Fair Value
```

CVA는 이러한 가치 조정을 정량적으로 표현한 개념이다.

---

# 4. Why CVA Exists

전통적인 파생상품 평가는 다음을 가정하였다.

* 계약은 반드시 이행된다.
* 거래상대방은 부도나지 않는다.
* 계약의 미래 현금흐름은 모두 회수된다.

그러나 실제 시장에서는 이러한 가정이 성립하지 않는다.

대표적인 사례는 다음과 같다.

* 거래상대방의 신용등급 하락
* CDS Spread 확대
* 시장 불안
* 실제 부도(Default)

이러한 위험을 가치평가에 반영하기 위해 CVA가 도입되었다.

---

# 5. Conceptual Relationship

CVA는 거래상대방 신용위험을 가치평가로 연결하는 과정이다.

```text
Counterparty

↓

Default Risk

↓

Expected Loss

↓

Present Value

↓

Credit Valuation Adjustment

↓

Derivative Fair Value
```

즉,

**신용위험 → 손실 → 현재가치 → 가치조정**

이라는 연결 구조를 가진다.

---

# 6. Relationship with Counterparty Credit Risk

Counterparty Credit Risk(CCR)는 위험(Risk) 자체를 의미한다.

CVA는 그 위험을 가격(Pricing)에 반영한 결과이다.

```text
Counterparty Credit Risk

↓

Exposure

↓

Potential Loss

↓

Credit Valuation Adjustment
```

따라서

CCR은 원인(Cause),

CVA는 결과(Result)라고 볼 수 있다.

---

# 7. Relationship with SA-CCR

SA-CCR는 거래상대방 위험 노출을 계산한다.

CVA는 그 노출을 이용하여 가치조정을 수행한다.

```text
Trade Portfolio

↓

SA-CCR

↓

Exposure Profile

↓

CVA

↓

Adjusted Fair Value
```

두 Framework는 경쟁 관계가 아니라 상호 보완 관계이다.

---

# 8. Relationship with XVA

CVA는 XVA(Value Adjustment) Framework의 대표적인 구성 요소이다.

```text
Value Adjustment
│
├── CVA
├── DVA
├── FVA
├── MVA
├── ColVA
└── KVA
```

각 Adjustment는 서로 다른 위험 또는 비용을 반영한다.

| Adjustment | Purpose                  |
| ---------- | ------------------------ |
| CVA        | Counterparty Credit Risk |
| DVA        | Own Credit Risk          |
| FVA        | Funding Cost             |
| MVA        | Initial Margin Cost      |
| ColVA      | Collateral Cost          |
| KVA        | Capital Cost             |

---

# 9. Position in Basel III

Basel III에서는 CVA를 독립적인 규제 영역으로 관리한다.

```text
Basel III
│
├── Credit Risk
├── Market Risk
├── Counterparty Credit Risk
│      │
│      ├── SA-CCR
│      └── CVA
├── Operational Risk
└── Liquidity Risk
```

SA-CCR는 거래상대방 위험 노출(EAD)을 계산하고,

CVA는 그 노출에 신용위험을 반영하여 공정가치를 조정한다.

---

# 10. Business Significance

CVA는 금융기관의 다양한 업무와 연결된다.

* 파생상품 가격결정
* 거래 승인
* 한도관리
* 헤지 전략
* 규제자본 산정
* 재무제표 공정가치 평가
* 리스크 모니터링

---

# 11. Key Characteristics

| Characteristic        | Description   |
| --------------------- | ------------- |
| Forward Looking       | 미래 위험을 반영     |
| Credit Sensitive      | 신용스프레드 변화에 민감 |
| Market Based          | 시장가격 기반 평가    |
| Portfolio Based       | 포트폴리오 단위 관리   |
| Fair Value Adjustment | 공정가치 조정 메커니즘  |

---

# 12. Cross References

| Category                | Document                                  |
| ----------------------- | ----------------------------------------- |
| Reference               | [RL-150_CVA_OVERVIEW](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)                       |
| Analysis                | [AN-251_WHY_CVA_WAS_INTRODUCED](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)             |
| Knowledge               | [KB-252_CVA_FRAMEWORK](KB-252_CVA_FRAMEWORK.md)                      |
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

# 13. Summary

Credit Valuation Adjustment(CVA)는 거래상대방 신용위험을 파생상품의 공정가치에 반영하는 가치조정 메커니즘이다.

CVA는 거래상대방 신용위험(CCR)을 시장가치에 연결하는 핵심 개념이며, SA-CCR가 산출한 위험 노출을 기반으로 공정가치를 현실적으로 평가할 수 있도록 한다.

Basel III에서는 CVA를 독립적인 규제 영역으로 관리하며, 현대 금융기관의 파생상품 가격결정, 리스크 관리 및 규제자본 산정에서 핵심적인 역할을 수행한다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
