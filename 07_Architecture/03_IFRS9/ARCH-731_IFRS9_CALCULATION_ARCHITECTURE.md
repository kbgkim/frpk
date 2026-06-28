# ARCH-731 — IFRS 9 Calculation Architecture

---

# Document Information

| Item            | Value                           |
| --------------- | ------------------------------- |
| Document ID     | ARCH-731                        |
| Document Name   | IFRS 9 Calculation Architecture |
| Version         | 1.0.0                           |
| Status          | Draft                           |
| Category        | Architecture                    |
| Parent Document | KB-232                          |
| Created         | 2026-06-26                      |
| Last Updated    | 2026-06-26                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Architecture Guide](../README.md) > [ARCH-731 — IFRS 9 Calculation Architecture](ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Architecture Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
- [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)
- [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)
- [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 IFRS 9 Expected Credit Loss(ECL) 계산을 위한 전체 시스템 아키텍처를 정의한다.

본 문서는 Credit Risk Assessment부터 Stage 분류, Expected Credit Loss 계산, Provision 산출까지의 전체 오케스트레이션 구조와 계층별 책임을 설명한다.

Formula Engine, Implementation Layer, Risk Engine, Accounting Layer의 역할을 명확히 분리하는 것을 목표로 한다.

---

# 2. Architecture Principles

본 아키텍처는 다음 원칙을 따른다.

1. 신용평가와 회계 처리를 분리한다.
2. Formula와 Implementation을 분리한다.
3. Implementation과 Orchestration을 분리한다.
4. 모든 계산은 Stateless로 구현한다.
5. 계산 결과는 Immutable Contract를 따른다.
6. 규제 정책과 계산 로직을 분리한다.

---

# 3. Overall Architecture

```text
                   Customer Information
                            │
                            ▼
                  Credit Assessment
                            │
                            ▼
                 Stage Classification
                            │
                            ▼
                 Expected Credit Loss
          ┌──────────┼──────────┐
          ▼          ▼          ▼
         PD         LGD        EAD
          └──────────┼──────────┘
                     ▼
             Discount Calculation
                     │
                     ▼
            Scenario Aggregation
                     │
                     ▼
            Expected Credit Loss
                     │
                     ▼
            Provision Calculation
                     │
                     ▼
          Financial Statements
```

---

# 4. Layered Architecture

```text
Presentation Layer
        │
        ▼
Application Layer
        │
        ▼
Credit Risk Engine
        │
        ▼
Implementation Layer
        │
        ▼
Formula Engine
        │
        ▼
Mathematical Library
```

각 계층은 자신의 책임만 수행한다.

---

# 5. Responsibility Matrix

| Layer                | Responsibility                 |
| -------------------- | ------------------------------ |
| Formula Engine       | PD, LGD, EAD, Discount, ECL 계산 |
| Implementation Layer | Formula 실행                     |
| Credit Risk Engine   | Stage, Scenario, Pipeline 제어   |
| Accounting Layer     | 충당금 및 회계 처리                    |
| Application Layer    | 업무 흐름 및 배치 관리                  |
| Presentation Layer   | 조회 및 보고                        |

---

# 6. Formula Engine Responsibilities

Formula Engine은 다음 계산만 담당한다.

* Probability of Default
* Loss Given Default
* Exposure at Default
* Discount Factor
* Expected Credit Loss
* Scenario Aggregation

업무 정책이나 회계 처리는 포함하지 않는다.

---

# 7. Implementation Layer Responsibilities

Implementation Layer는 Formula를 실행 가능한 컴포넌트로 구성한다.

예시

```text
StageResolver

PDCalculator

LGDCalculator

EADCalculator

DiscountCalculator

ExpectedCreditLossCalculator
```

각 Calculator는 하나의 계산 책임만 가진다.

---

# 8. Credit Risk Engine Responsibilities

Credit Risk Engine은 전체 ECL 계산을 오케스트레이션한다.

```text
Financial Asset
        │
        ▼
Stage Resolution
        │
        ▼
PD/LGD/EAD Loading
        │
        ▼
Scenario Execution
        │
        ▼
Discount Processing
        │
        ▼
ECL Aggregation
        │
        ▼
Provision Result
```

Credit Risk Engine은 계산을 직접 수행하지 않고 계산 순서를 관리한다.

---

# 9. Data Flow

```text
Customer Data
      │
      ▼
Credit Assessment
      │
      ▼
Stage
      │
      ▼
PD / LGD / EAD
      │
      ▼
Expected Credit Loss
      │
      ▼
Provision
      │
      ▼
Financial Statements
```

데이터는 상위 계층에서 하위 계층으로 단방향으로 흐른다.

---

# 10. Component Model

```text
CreditAssessmentService
        │
        ▼
StageService
        │
        ▼
PDService
        │
        ▼
LGDService
        │
        ▼
EADService
        │
        ▼
DiscountService
        │
        ▼
ScenarioService
        │
        ▼
ExpectedCreditLossService
        │
        ▼
ProvisionService
```

서비스 간 직접 결합을 최소화하고 명확한 입력·출력 계약을 유지한다.

---

# 11. Contracts

모든 서비스는 다음 계약을 따른다.

| Contract            | Description         |
| ------------------- | ------------------- |
| Input Contract      | Immutable Request   |
| Processing Contract | Stateless Execution |
| Output Contract     | Immutable Result    |

부작용(Side Effect)은 허용하지 않는다.

---

# 12. Batch Processing Architecture

```text
Portfolio
      │
──────┼──────────────
      ▼
Asset 1
Asset 2
Asset 3
      │
──────┼──────────────
      ▼
Scenario Processing
      │
──────┼──────────────
      ▼
Aggregation
```

포트폴리오 단위와 시나리오 단위 모두 병렬 실행이 가능하다.

---

# 13. Configuration Model

설정으로 관리할 항목

* Stage 정책
* SICR 정책
* Discount 정책
* Scenario 정책
* Macroeconomic Variable
* PD Calibration
* LGD Policy
* CCF Policy

규제 변경 시 코드 변경 없이 설정만 변경할 수 있도록 설계한다.

---

# 14. Extension Points

향후 확장 대상

* Multi-scenario Forecasting
* Climate Risk Scenario
* Real-time ECL
* Distributed Batch Engine
* GPU 기반 계산
* AI 기반 PD/LGD 모델 연계

---

# 15. Relationship with Basel III

```text
                 Credit Risk
                      │
        ┌─────────────┴─────────────┐
        ▼                           ▼
      IFRS 9                    Basel III
        │                           │
Expected Credit Loss          Credit RWA
        │                           │
Provision                  Regulatory Capital
```

두 체계는 동일한 신용위험 데이터를 공유하지만 목적과 산출물은 다르다.

---

# 16. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)           |
| Knowledge      | [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md), [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)   |
| Analysis       | [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)           |
| Formula        | [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md) ~ [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)  |
| Implementation | [IMP-431](../../06_Implementation_Guide/03_IFRS9/IMP-431_EXPECTED_CREDIT_LOSS_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-731](ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)         |

---

# 17. Knowledge Graph

```text
Financial Asset
        │
        ▼
Credit Assessment
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
Provision
        │
        ▼
Financial Statements
```

---

# 18. Design Principles

본 아키텍처는 다음 설계 원칙을 따른다.

* Single Responsibility Principle
* Separation of Formula and Execution
* Separation of Risk and Accounting
* Stateless Processing
* Immutable Data Contracts
* Configuration over Hard Coding
* Parallel-friendly Processing
* Pipeline-based Execution

---

# 19. Summary

IFRS 9 Calculation Architecture는 신용위험 데이터를 회계상 손상충당금으로 변환하는 전체 계산 구조를 정의한다.

Formula Engine은 PD, LGD, EAD 및 Expected Credit Loss를 계산하고, Implementation Layer는 이를 실행 가능한 컴포넌트로 구현한다. Credit Risk Engine은 Stage 분류와 시나리오 실행을 포함한 계산 순서를 오케스트레이션하며, Accounting Layer는 계산 결과를 손상충당금과 재무제표에 반영한다.

FRKP에서는 **"계산은 Formula가 담당하고, 실행은 Implementation이 담당하며, 오케스트레이션은 Credit Risk Engine이 담당하고, 회계 처리는 Accounting Layer가 담당한다."**는 원칙을 적용하여 확장 가능하고 규제 변화에 대응 가능한 IFRS 9 플랫폼 아키텍처를 정의한다.

---

# 20. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
