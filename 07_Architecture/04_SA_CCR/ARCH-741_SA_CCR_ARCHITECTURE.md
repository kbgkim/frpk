# ARCH-741 — SA-CCR Calculation Architecture

---

# Document Information

| Item            | Value                           |
| --------------- | ------------------------------- |
| Document ID     | ARCH-741                        |
| Document Name   | SA-CCR Calculation Architecture |
| Version         | 1.0.0                           |
| Status          | Draft                           |
| Category        | Architecture Guide              |
| Parent Document | IMP-441                         |
| Created         | 2026-06-26                      |
| Last Updated    | 2026-06-26                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Architecture Guide](../README.md) > [ARCH-741 — SA-CCR Calculation Architecture](ARCH-741_SA_CCR_ARCHITECTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Architecture Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
- [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)
- [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)
- [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 SA-CCR(Standardised Approach for Counterparty Credit Risk)의 계산을 수행하기 위한 시스템 아키텍처를 정의한다.

본 문서는 계산 알고리즘이 아닌 컴포넌트 구조, 계층, 책임, 데이터 흐름 및 시스템 간 연계를 설명한다.

FRKP에서는 SA-CCR를 **모듈화된 계산 파이프라인과 명확한 책임 분리(Separation of Concerns)** 를 기반으로 설계한다.

---

# 2. Architecture Scope

본 문서는 다음 기능을 포함한다.

* Trade Intake
* Validation
* Netting Set Management
* Collateral Processing
* Replacement Cost Calculation
* Potential Future Exposure Calculation
* Alpha Application
* Exposure at Default Generation

다음 항목은 범위에서 제외한다.

* 거래 입력 UI
* 배치 스케줄러
* 데이터베이스 물리 설계
* 외부 인터페이스 구현

---

# 3. Architecture Principles

SA-CCR 아키텍처는 다음 원칙을 따른다.

1. Layered Architecture
2. Single Responsibility Principle
3. Deterministic Calculation
4. Stateless Calculation Components
5. Immutable Calculation Results
6. Technology Neutral Design
7. Traceable Processing

---

# 4. Layer Architecture

```text
External Systems
        │
        ▼
Application Layer
        │
        ▼
SA-CCR Orchestration Layer
        │
        ▼
Calculation Layer
        │
        ▼
Domain Model Layer
        │
        ▼
Infrastructure Layer
```

각 계층은 하위 계층에만 의존하며 역방향 의존은 허용하지 않는다.

---

# 5. Component Architecture

```text
Trade Intake
      │
      ▼
Trade Validator
      │
      ▼
Trade Classifier
      │
      ▼
Netting Builder
      │
      ▼
Collateral Processor
      │
      ▼
Replacement Cost Calculator
      │
      ▼
PFE Calculator
      │
      ▼
Alpha Applier
      │
      ▼
EAD Calculator
      │
      ▼
Result Publisher
```

각 컴포넌트는 하나의 책임만 수행한다.

---

# 6. Data Flow

```text
Trade Portfolio
        │
        ▼
Validation
        │
        ▼
Trade Classification
        │
        ▼
Netting Set Construction
        │
        ▼
Collateral Processing
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Apply Alpha
        │
        ▼
Exposure at Default
        │
        ▼
Risk Output
```

데이터는 단방향으로 흐르며, 계산 중간 결과는 추적 가능해야 한다.

---

# 7. Component Responsibilities

| Component                   | Responsibility |
| --------------------------- | -------------- |
| Trade Validator             | 입력 데이터 검증      |
| Trade Classifier            | 자산군 분류         |
| Netting Builder             | Netting Set 구성 |
| Collateral Processor        | 담보 평가          |
| Replacement Cost Calculator | RC 계산          |
| PFE Calculator              | PFE 계산         |
| Alpha Applier               | 규제 보정계수 적용     |
| EAD Calculator              | 최종 EAD 계산      |
| Result Publisher            | 결과 전달          |

---

# 8. Dependency Rules

의존성은 다음 순서를 따른다.

```text
Application
      │
      ▼
Orchestrator
      │
      ▼
Calculation Components
      │
      ▼
Domain Models
```

다음은 허용하지 않는다.

* Calculation → Application
* Domain → Infrastructure
* Circular Dependency

---

# 9. Integration Points

SA-CCR는 다음 시스템과 연계될 수 있다.

| System                | Purpose       |
| --------------------- | ------------- |
| Trade Repository      | 거래 정보         |
| Market Data Service   | 시장 데이터        |
| Collateral Management | 담보 정보         |
| Risk Engine           | 위험 계산         |
| Capital Engine        | RWA 및 규제자본 계산 |
| Reporting Engine      | 규제 보고         |

연계는 계약(Contract) 기반 인터페이스를 사용한다.

---

# 10. Domain Model

주요 도메인 객체

```text
Trade

Portfolio

NettingSet

Collateral

ReplacementCost

PotentialFutureExposure

ExposureAtDefault
```

도메인 객체는 불변(Immutable) 객체를 원칙으로 한다.

---

# 11. Processing Orchestration

```text
Input
   │
   ▼
Validation
   │
   ▼
Netting
   │
   ▼
Collateral
   │
   ▼
RC
   │
   ▼
PFE
   │
   ▼
Alpha
   │
   ▼
EAD
   │
   ▼
Output
```

오케스트레이터는 계산 순서를 제어하며 계산 로직은 포함하지 않는다.

---

# 12. Error Handling Architecture

오류는 다음 계층에서 처리한다.

| Layer          | Responsibility |
| -------------- | -------------- |
| Validation     | 입력 오류          |
| Domain         | 업무 규칙 위반       |
| Calculation    | 계산 불가          |
| Configuration  | 파라미터 오류        |
| Infrastructure | 시스템 오류         |

오류는 명확한 원인과 발생 위치를 포함해야 한다.

---

# 13. Non-functional Requirements

아키텍처는 다음 요구사항을 만족해야 한다.

* Deterministic Processing
* Horizontal Scalability
* Stateless Components
* Parallel Calculation
* Immutable Results
* High Testability
* Traceability
* Configurable Regulatory Parameters

---

# 14. Performance Architecture

성능 최적화 전략

* Netting Set 캐싱
* 규제 파라미터 캐싱
* 자산군 병렬 계산
* 포트폴리오 병렬 처리
* 증분 재계산(Incremental Recalculation)
* 계산 결과 재사용

---

# 15. Traceability

```text
Trade
   │
   ▼
Netting Set
   │
   ▼
Replacement Cost
   │
   ▼
Potential Future Exposure
   │
   ▼
Alpha
   │
   ▼
Exposure at Default
   │
   ▼
Credit RWA
```

모든 단계는 입력과 출력이 추적 가능해야 한다.

---

# 16. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)           |
| Knowledge      | [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md), [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)   |
| Analysis       | [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)           |
| Formula        | [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md) ~ [FC-444](../../04_Formula_Catalog/04_SA_CCR/FC-444_SA_CCR_EAD.md)  |
| Implementation | [IMP-441](../../06_Implementation_Guide/04_SA_CCR/IMP-441_SA_CCR_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-741](ARCH-741_SA_CCR_ARCHITECTURE.md)         |

---

# 17. Knowledge Graph

```text
Trade
   │
   ▼
Validation
   │
   ▼
Netting
   │
   ▼
Collateral
   │
   ▼
Replacement Cost
   │
   ▼
Potential Future Exposure
   │
   ▼
Alpha
   │
   ▼
Exposure at Default
   │
   ▼
Capital Engine
```

---

# 18. Architecture Decisions

| ID   | Decision                           | Rationale       |
| ---- | ---------------------------------- | --------------- |
| AD-1 | Layered Architecture               | 책임 분리           |
| AD-2 | Stateless Calculators              | 병렬 처리 및 테스트 용이성 |
| AD-3 | Immutable Domain Models            | 계산 일관성 확보       |
| AD-4 | Orchestrator Pattern               | 계산 순서와 계산 로직 분리 |
| AD-5 | Contract-based Integration         | 시스템 간 결합도 최소화   |
| AD-6 | Externalized Regulatory Parameters | 규제 변경 대응        |

---

# 19. Summary

SA-CCR Architecture는 거래 입력부터 Exposure at Default 산출까지의 계산 구조를 계층화된 컴포넌트 아키텍처로 정의한다.

각 컴포넌트는 단일 책임 원칙을 따르며, 계산 순서는 오케스트레이터가 제어하고 계산 로직은 독립적인 계산 컴포넌트가 수행한다. 이를 통해 확장성, 테스트 용이성, 규제 변경 대응성 및 계산 추적성을 확보한다.

---

# 20. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
