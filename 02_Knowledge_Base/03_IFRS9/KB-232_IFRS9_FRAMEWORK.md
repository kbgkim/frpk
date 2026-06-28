# KB-232 — IFRS 9 Framework

---

# Document Information

| Item            | Value            |
| --------------- | ---------------- |
| Document ID     | KB-232           |
| Document Name   | IFRS 9 Framework |
| Version         | 1.0.0            |
| Status          | Draft            |
| Category        | Knowledge Base   |
| Parent Document | RL-130           |
| Created         | 2026-06-26       |
| Last Updated    | 2026-06-26       |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Knowledge Base](../README.md) > [KB-232 — IFRS 9 Framework](KB-232_IFRS9_FRAMEWORK.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [KB-231](KB-231_CREDIT_RISK_OVERVIEW.md) |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](KB-231_CREDIT_RISK_OVERVIEW.md)
- [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)
- [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)
- [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 IFRS 9의 전체 신용손실 측정 프레임워크를 설명한다.

IFRS 9는 단순한 회계기준이 아니라 **신용위험(Credit Risk)을 지속적으로 평가하고 예상신용손실(Expected Credit Loss, ECL)을 산출하는 통합 프레임워크**이다.

FRKP에서는 IFRS 9를 **Credit Quality → Stage Assessment → PD/LGD/EAD → Expected Credit Loss → Impairment**로 이어지는 계층적 구조로 정의한다.

---

# 2. Framework Overview

IFRS 9 손상(Impairment) 모형은 다음 흐름으로 구성된다.

```text
Financial Asset
        │
        ▼
Credit Risk Assessment
        │
        ▼
Stage Classification
        │
        ▼
PD
LGD
EAD
        │
        ▼
Expected Credit Loss
        │
        ▼
Impairment Allowance
```

모든 계산은 신용위험 평가에서 시작된다.

---

# 3. Core Components

IFRS 9 Framework는 다음 여섯 개의 핵심 요소로 구성된다.

| Component              | Purpose   |
| ---------------------- | --------- |
| Credit Risk Assessment | 신용위험 평가   |
| Stage Classification   | Stage 결정  |
| PD                     | 부도확률      |
| LGD                    | 부도 시 손실률  |
| EAD                    | 부도 시 익스포저 |
| Expected Credit Loss   | 예상신용손실    |

---

# 4. Credit Risk Assessment

첫 번째 단계는 차주의 신용상태를 평가하는 것이다.

평가 대상은 다음과 같다.

* 내부 신용등급
* 외부 신용등급
* 연체 정보
* 재무상태
* 산업 전망
* 거시경제 변수
* 담보 가치
* 보증 정보

평가 결과는 Stage 분류의 입력으로 사용된다.

---

# 5. Stage Classification

IFRS 9는 자산을 세 개의 Stage로 구분한다.

| Stage   | Meaning           | Loss Measurement          |
| ------- | ----------------- | ------------------------- |
| Stage 1 | 정상                | 12-Month ECL              |
| Stage 2 | 신용위험 유의적 증가(SICR) | Lifetime ECL              |
| Stage 3 | 신용손상 발생           | Lifetime ECL + 이자수익 계산 변경 |

Stage는 계산 방식과 충당금 규모를 결정하는 핵심 요소이다.

---

# 6. Significant Increase in Credit Risk (SICR)

Stage 1에서 Stage 2로 이동하는 기준은 **SICR(Significant Increase in Credit Risk)** 이다.

SICR 평가는 다음 정보를 종합적으로 활용한다.

* PD 증가
* 연체 일수
* 신용등급 하락
* 산업 위험 증가
* 미래 거시경제 전망

SICR은 단일 규칙이 아니라 금융기관의 정책에 따라 정의되는 판단 체계이다.

---

# 7. Expected Credit Loss Components

Stage가 결정되면 ECL 계산을 수행한다.

핵심 구성 요소는 다음과 같다.

```text
PD
 │
 ├────────────┐
 ▼            ▼
LGD          EAD
      │
      ▼
Expected Credit Loss
```

각 요소는 독립적인 모델에서 계산된다.

---

# 8. Expected Credit Loss Formula

기본적인 Expected Credit Loss는 다음 요소의 결합으로 표현된다.

```text
PD
 ×
LGD
 ×
EAD
      │
      ▼
Expected Credit Loss
```

실무에서는 할인율(Discount Rate), 시나리오 확률, 미래 전망 등을 함께 반영한다.

---

# 9. Forward-looking Information

IFRS 9의 핵심 특징은 미래 정보를 반영한다는 점이다.

예를 들어

* GDP 성장률
* 실업률
* 금리
* 부동산 가격
* 환율

등의 거시경제 변수는 PD와 LGD에 영향을 줄 수 있다.

따라서 ECL은 단순한 과거 통계가 아니라 **미래 전망을 포함한 추정치**이다.

---

# 10. Multi-scenario Framework

많은 금융기관은 복수의 경제 시나리오를 사용한다.

```text
Base Scenario
        │
Optimistic Scenario
        │
Pessimistic Scenario
        │
        ▼
Probability Weighted ECL
```

각 시나리오별 ECL을 계산한 후 발생 확률을 반영하여 최종 ECL을 산출한다.

---

# 11. Relationship with Basel III

```text
Credit Risk
      │
      ├───────────────┐
      ▼               ▼
IFRS 9           Basel III
      │               │
Expected Loss    Unexpected Loss
      │               │
Provision        Regulatory Capital
```

두 체계는 목적은 다르지만 동일한 PD, LGD, EAD 데이터를 활용한다.

---

# 12. System Architecture

```text
Customer Information
        │
        ▼
Credit Assessment Engine
        │
        ▼
Stage Engine
        │
        ▼
PD Engine
LGD Engine
EAD Engine
        │
        ▼
ECL Engine
        │
        ▼
Provision Engine
```

각 엔진은 독립적인 책임을 가지며 순차적으로 연결된다.

---

# 13. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)           |
| Knowledge      | [KB-231](KB-231_CREDIT_RISK_OVERVIEW.md), [KB-232](KB-232_IFRS9_FRAMEWORK.md)   |
| Analysis       | [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)           |
| Formula        | [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md) ~ [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)  |
| Implementation | [IMP-431](../../06_Implementation_Guide/03_IFRS9/IMP-431_EXPECTED_CREDIT_LOSS_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-731](../../07_Architecture/03_IFRS9/ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)         |

---

# 14. Knowledge Graph

```text
Financial Asset
        │
        ▼
Credit Risk
        │
        ▼
Stage
        │
        ▼
PD
LGD
EAD
        │
        ▼
Expected Credit Loss
        │
        ▼
Impairment Allowance
```

---

# 15. Learning Path

```text
RL-130 IFRS 9 Overview
        │
        ▼
KB-231 Credit Risk Overview
        │
        ▼
AN-231 Why Incurred Loss Failed
        │
        ▼
KB-232 IFRS 9 Framework
        │
        ├── FC-431 Probability of Default
        ├── FC-432 Loss Given Default
        ├── FC-433 Exposure at Default
        └── FC-434 Expected Credit Loss
                 │
                 ▼
IMP-431 Expected Credit Loss Implementation
                 │
                 ▼
ARCH-731 IFRS 9 Calculation Architecture
```

---

# 16. Summary

IFRS 9는 금융자산의 신용위험을 지속적으로 평가하여 예상신용손실을 계산하는 통합 프레임워크이다.

신용위험 평가는 Stage Classification을 통해 손실 인식 범위를 결정하고, PD·LGD·EAD 모델을 활용하여 Expected Credit Loss를 산출한다.

FRKP에서는 IFRS 9를 **Credit Assessment → Stage → PD/LGD/EAD → Expected Credit Loss → Impairment**로 이어지는 계층형 신용위험 관리 구조로 정의하며, Formula, Implementation, Architecture 문서는 이 프레임워크를 기준으로 구성한다.

---

# 17. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
