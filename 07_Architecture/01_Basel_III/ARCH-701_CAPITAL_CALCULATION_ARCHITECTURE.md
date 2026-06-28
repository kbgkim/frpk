# ARCH-701 — Capital Calculation Architecture

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) > [Architecture Guide](../README.md) > [ARCH-701 — Capital Calculation Architecture](ARCH-701_CAPITAL_CALCULATION_ARCHITECTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) |
| ⬆ Parent Layer | [Architecture Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-001](../../01_Reference_Library/01_Basel_III/RL-001_BASEL_III_OVERVIEW.md)
- [KB-201](../../02_Knowledge_Base/01_Basel_III/KB-201_FINANCIAL_RISK_OVERVIEW.md)
- [KB-301](../../02_Knowledge_Base/01_Basel_III/KB-301_BASEL_III_FRAMEWORK.md)
- [FC-401](../../04_Formula_Catalog/01_Basel_III/FC-401_CAPITAL_ADEQUACY_RATIO.md)
- [FC-402](../../04_Formula_Catalog/01_Basel_III/FC-402_RISK_WEIGHTED_ASSETS.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item          | Value                            |
| ------------- | -------------------------------- |
| Document ID   | ARCH-701                         |
| Document Name | Capital Calculation Architecture |
| Version       | 1.0.0                            |
| Status        | Draft                            |
| Owner         | Project Lead                     |
| Category      | Architecture Guide               |
| Created       | 2026-06-26                       |
| Last Updated  | 2026-06-26                       |

---

# 1. Purpose

본 문서는 Basel III 규제자본(Capital Adequacy) 계산을 위한 시스템 아키텍처를 정의한다.

FRKP에서는 규제자본 계산을 단순한 산식 실행이 아니라 **독립적인 Risk Engine들의 결과를 통합하여 최종 자본비율을 산출하는 아키텍처**로 정의한다.

---

# 2. Architecture Objectives

본 아키텍처의 목표는 다음과 같다.

* 위험 유형별 계산 엔진을 독립적으로 구성한다.
* 규제 변경 시 영향 범위를 최소화한다.
* 계산 순서를 명확하게 정의한다.
* 병렬 계산이 가능하도록 설계한다.
* Formula Engine과 Risk Engine을 분리한다.
* 확장 가능한 구조를 유지한다.

---

# 3. Architecture Principles

FRKP는 다음 원칙을 따른다.

### Separation of Concerns

각 위험 계산 엔진은 자신의 위험만 계산한다.

### Single Responsibility

RWA Aggregator는 합산만 수행한다.

### Immutable Result

계산 결과는 변경되지 않는 Value Object로 관리한다.

### Configuration Driven

규제 기준 및 임계값은 설정(Configuration)으로 관리한다.

---

# 4. High-Level Architecture

```text
                           Financial Data
                                  │
                                  ▼
                     Exposure Normalization Layer
                                  │
          ┌───────────────┬───────────────┬───────────────┐
          ▼               ▼               ▼
   Credit Risk      Market Risk    Operational Risk
      Engine            Engine            Engine
          │               │               │
          └───────────────┴───────────────┘
                          │
                          ▼
                  RWA Aggregator
                          │
                          ▼
            Regulatory Capital Engine
                          │
                          ▼
             Capital Ratio Calculator
                          │
                          ▼
                 Regulatory Reports
```

---

# 5. Layered Architecture

## Layer 1 — Data Layer

역할

* 거래 데이터
* 포지션
* 회계 데이터
* 시장 데이터
* 참조 데이터

출력

```
Exposure
```

---

## Layer 2 — Risk Calculation Layer

독립적인 계산 엔진

* Credit Risk Engine
* Market Risk Engine
* Operational Risk Engine

각 엔진은 자신의 RWA만 계산한다.

---

## Layer 3 — Aggregation Layer

역할

```
Credit RWA

+

Market RWA

+

Operational RWA

↓

Total RWA
```

여기서는 어떠한 위험 계산도 수행하지 않는다.

---

## Layer 4 — Capital Layer

입력

```
CET1

AT1

Tier2

Total RWA
```

출력

```
CET1 Ratio

Tier1 Ratio

Total Capital Ratio
```

---

## Layer 5 — Reporting Layer

출력

* Regulatory Report
* Dashboard
* Management Report
* Capital Monitoring

---

# 6. Component Model

```text
ExposureProvider
        │
        ▼
ExposureNormalizer
        │
        ▼
RiskCalculationCoordinator
        │
        ├───────────────┐
        ▼               ▼
CreditEngine      MarketEngine
        │               │
        ▼               ▼
 OperationalEngine
        │
        ▼
RWAAggregator
        │
        ▼
CapitalCalculator
        │
        ▼
ReportGenerator
```

---

# 7. Processing Flow

1. 거래 데이터를 수집한다.
2. Exposure를 생성한다.
3. 위험 유형별 엔진이 병렬 계산을 수행한다.
4. 각 엔진은 자신의 RWA를 반환한다.
5. Aggregator가 Total RWA를 계산한다.
6. Capital Engine이 규제자본을 계산한다.
7. Reporting Engine이 결과를 생성한다.

---

# 8. Domain Model

## Core Value Objects

```
Exposure

↓

RiskResult

↓

CreditRiskResult

↓

MarketRiskResult

↓

OperationalRiskResult

↓

TotalRWA

↓

CapitalResult
```

모든 객체는 Immutable Value Object로 구현한다.

---

# 9. Formula Engine Relationship

Formula Engine은 개별 수식 계산만 담당한다.

예)

* Present Value
* Duration
* VaR
* Expected Shortfall
* PD
* LGD

Risk Engine은 Formula Engine을 호출하여 업무 계산을 수행한다.

```
Formula Engine

↓

Risk Engine

↓

Capital Engine
```

Formula Engine은 업무 흐름을 알지 못한다.

---

# 10. Runtime Architecture

```text
Calculation Request
          │
          ▼
Runtime Context
          │
          ▼
Formula Engine
          │
          ▼
Risk Engine
          │
          ▼
Capital Engine
          │
          ▼
Execution Result
```

Runtime은 계산 상태만 관리하며 비즈니스 규칙은 포함하지 않는다.

---

# 11. Scalability

확장 가능한 구조를 위해 다음 원칙을 적용한다.

* 새로운 위험 유형 추가 가능
* 병렬 계산 지원
* Engine 간 독립성 유지
* Aggregator 변경 최소화
* 규제 변경 시 Formula 교체 가능

---

# 12. Mapping to FRKP

| Layer        | Related Documents |
| ------------ | ----------------- |
| Regulation   | RL-110            |
| Knowledge    | KB-201, KB-301    |
| Formula      | FC-401, FC-402    |
| Architecture | ARCH-701          |

---

# 13. Future Extensions

향후 다음 Engine을 동일한 구조로 추가한다.

* FRTB Engine
* IFRS 9 Engine
* SA-CCR Engine
* CVA Engine
* Liquidity Engine
* Stress Testing Engine
* Monte Carlo Engine
* Diffusion Risk Engine

---

# 14. Design Decisions

| Decision               | Reason   |
| ---------------------- | -------- |
| Risk Engine 분리         | 독립성 확보   |
| Formula Engine 재사용     | 중복 제거    |
| Immutable Value Object | 안정성 확보   |
| Aggregator 분리          | 책임 분리    |
| Configuration 기반 규제    | 규제 변경 대응 |
| 병렬 계산 구조               | 성능 향상    |

---

# 15. Knowledge Path

```text
RL-110 Basel III Overview
        │
        ▼
KB-301 Basel III Framework
        │
        ▼
FC-401 Capital Adequacy Ratio
        │
        ▼
FC-402 Risk Weighted Assets
        │
        ▼
ARCH-701 Capital Calculation Architecture
        │
        ▼
ARCH-721 FRTB Calculation Architecture
        │
        ▼
ARCH-741 Credit Risk Architecture
```

---

# 16. Summary

Capital Calculation Architecture는 FRKP Risk Engine의 최상위 계산 구조이다.

각 위험 계산 엔진은 독립적으로 Risk Weighted Assets를 산출하며, Aggregation Layer에서 이를 통합하여 Total RWA를 생성한다. Regulatory Capital Engine은 Total RWA와 규제자본(CET1, AT1, Tier2)을 이용하여 Basel III 자본비율을 계산한다.

Formula Engine은 개별 산식을 제공하는 공통 계산 계층이며, Risk Engine은 이를 조합하여 규제 업무를 수행한다. 이러한 계층형 구조는 규제 변경에 대한 유연성과 계산 엔진의 재사용성을 높이는 FRKP의 핵심 아키텍처 원칙이다.

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
