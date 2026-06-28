# ARCH-721 — FRTB Calculation Architecture

---

# Document Information

| Item            | Value                         |
| --------------- | ----------------------------- |
| Document ID     | ARCH-721                      |
| Document Name   | FRTB Calculation Architecture |
| Version         | 1.0.0                         |
| Status          | Draft                         |
| Category        | Architecture                  |
| Parent Document | KB-222                        |
| Created         | 2026-06-26                    |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Architecture Guide](../README.md) > [ARCH-721 — FRTB Calculation Architecture](ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Architecture Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
- [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III FRTB 시장위험 계산을 위한 전체 시스템 아키텍처를 정의한다.

본 문서는 Formula Engine, Implementation Layer, Risk Engine의 책임을 분리하고, 각 계층 간 데이터 흐름과 오케스트레이션 구조를 설명하는 것을 목적으로 한다.

---

# 2. Architecture Principles

본 아키텍처는 다음 원칙을 따른다.

1. 계산(Formula)과 실행(Implementation)을 분리한다.
2. 실행과 오케스트레이션(Risk Engine)을 분리한다.
3. Risk Factor 중심으로 설계한다.
4. 모든 계산은 Immutable Contract를 따른다.
5. 병렬 처리가 가능하도록 Stateless Component를 사용한다.

---

# 3. Overall Architecture

```text
                    Market Data
                         │
                         ▼
               Risk Factor Mapping
                         │
                         ▼
              Sensitivity Calculation
         ┌────────┼──────────┐
         ▼        ▼          ▼
      Delta     Vega     Curvature
         └────────┼──────────┘
                  ▼
       Sensitivity-Based Method
                  │
                  ▼
        Expected Shortfall Engine
                  │
                  ▼
      Liquidity Horizon Adjustment
                  │
                  ▼
        Market Capital Calculation
                  │
                  ▼
              Market RWA
                  │
                  ▼
     Basel III Capital Framework
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
Risk Engine
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

| Layer                | Responsibility  |
| -------------------- | --------------- |
| Formula Engine       | 수학적 계산          |
| Implementation Layer | 계산 절차 실행        |
| Risk Engine          | 계산 순서 및 오케스트레이션 |
| Application Layer    | 업무 흐름           |
| Presentation Layer   | 사용자 인터페이스       |

---

# 6. Formula Engine Responsibilities

Formula Engine은 다음 계산만 담당한다.

* Expected Shortfall
* Liquidity Horizon Scaling
* Delta
* Vega
* Curvature
* Correlation
* Bucket Aggregation Formula

Formula Engine은 업무 규칙이나 상태를 관리하지 않는다.

---

# 7. Implementation Layer Responsibilities

Implementation Layer는 Formula를 실제 실행 가능한 컴포넌트로 구현한다.

예시

```text
ExpectedShortfallCalculator

LiquidityHorizonCalculator

DeltaCalculator

VegaCalculator

CurvatureCalculator
```

각 Calculator는 하나의 계산 계약만 수행한다.

---

# 8. Risk Engine Responsibilities

Risk Engine은 전체 계산을 조정한다.

```text
Market Data
      │
      ▼
Risk Factor Mapping
      │
      ▼
Sensitivity Engine
      │
      ▼
Expected Shortfall
      │
      ▼
Liquidity Horizon
      │
      ▼
SBM Aggregation
      │
      ▼
Market Capital
```

Risk Engine은 계산을 직접 수행하지 않는다.

---

# 9. Data Flow

```text
Market Data
      │
      ▼
Pricing Model
      │
      ▼
Sensitivity
      │
      ▼
Expected Shortfall
      │
      ▼
Adjusted ES
      │
      ▼
Bucket Capital
      │
      ▼
Risk Class Capital
      │
      ▼
Market Capital
      │
      ▼
Market RWA
```

---

# 10. Component Model

```text
RiskFactorMapper
        │
        ▼
SensitivityService
        │
        ▼
ExpectedShortfallService
        │
        ▼
LiquidityAdjustmentService
        │
        ▼
SBMAggregationService
        │
        ▼
MarketCapitalService
```

서비스는 명확한 입력과 출력을 가진다.

---

# 11. Contracts

각 서비스는 다음 계약을 따른다.

| Contract             | Description           |
| -------------------- | --------------------- |
| Input Contract       | Immutable Request     |
| Computation Contract | Stateless Calculation |
| Output Contract      | Immutable Result      |

모든 서비스는 부작용(Side Effect)이 없어야 한다.

---

# 12. Parallel Processing

병렬 실행이 가능한 영역

```text
Scenario Generation
        │
────────┼────────
        ▼
Delta
Vega
Curvature
        │
────────┼────────
        ▼
Aggregation
```

Delta, Vega, Curvature 계산은 서로 독립적이므로 병렬 실행이 가능하다.

---

# 13. Configuration Model

설정으로 관리할 항목

* Risk Weight
* Correlation Matrix
* Liquidity Horizon
* Confidence Level
* Bucket Definition
* Risk Class Mapping

계산 로직과 규제 설정을 분리하여 규제 변경 시 코드 변경을 최소화한다.

---

# 14. Extension Points

향후 확장을 고려한 구조

* Historical Simulation
* Monte Carlo Simulation
* GPU Processing
* Distributed Risk Engine
* Intraday Risk Calculation
* Incremental Risk Update

---

# 15. Relationship with FRKP

| Layer          | Related Documents |
| -------------- | ----------------- |
| Reference      | [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)            |
| Knowledge      | [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md), [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)    |
| Analysis       | [AN-221](../../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)            |
| Formula        | [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md) ~ [FC-426](../../04_Formula_Catalog/02_FRTB/FC-426_CURVATURE_RISK_CHARGE.md)   |
| Implementation | IMP-421           |
| Architecture   | [ARCH-721](ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md)          |

---

# 16. Knowledge Graph

```text
Market Data
      │
      ▼
Risk Factor
      │
      ▼
Formula Engine
      │
      ▼
Implementation Layer
      │
      ▼
Risk Engine
      │
      ▼
Market Capital
      │
      ▼
Market RWA
```

---

# 17. Design Principles

본 아키텍처는 다음 설계 원칙을 따른다.

* Single Responsibility Principle
* Stateless Computation
* Immutable Data
* Configuration over Hard Coding
* Separation of Formula and Execution
* Orchestration over Calculation
* Parallel-friendly Design

---

# 18. Summary

FRTB Calculation Architecture는 시장위험 계산을 Formula Engine, Implementation Layer, Risk Engine으로 명확히 분리하는 계층형 구조를 채택한다.

Formula Engine은 수학적 정의를 제공하고, Implementation Layer는 이를 실행 가능한 컴포넌트로 구현하며, Risk Engine은 전체 계산 흐름을 오케스트레이션한다.

FRKP에서는 **"계산은 Formula가 담당하고, 실행은 Implementation이 담당하며, 조정은 Architecture가 담당한다."**는 원칙을 적용하여 규제 변화에 유연하고 확장 가능한 시장위험 계산 플랫폼을 구축한다.

---

# 19. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
