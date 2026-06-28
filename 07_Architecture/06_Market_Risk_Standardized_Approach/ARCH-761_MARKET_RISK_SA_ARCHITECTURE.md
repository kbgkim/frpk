# ARCH-761 — Market Risk Standardized Approach Architecture

---

# Document Information

| Item          | Value                                          |
| ------------- | ---------------------------------------------- |
| Document ID   | ARCH-761                                       |
| Document Name | Market Risk Standardized Approach Architecture |
| Version       | 1.0.0                                          |
| Status        | Active                                         |
| Category      | Architecture Guide                             |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                                     |
| Domain        | Market Risk                                    |
| Created       | 2026-06-27                                     |
| Last Updated  | 2026-06-27                                     |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Architecture Guide](../README.md) > [ARCH-761 — Market Risk Standardized Approach Architecture](ARCH-761_MARKET_RISK_SA_ARCHITECTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Architecture Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-261](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)
- [KB-263](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)
- [AN-261](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB) Standardized Approach(SA)를 지원하기 위한 시스템 아키텍처를 정의한다.

본 문서는 Formula Catalog와 Implementation Guide를 실제 Risk Engine Architecture로 연결하는 설계 기준을 제공하며, 특정 기술이나 제품에 종속되지 않는 기술 중립적(Technology Neutral) 아키텍처를 제시한다.

---

# 2. Scope

본 문서는 다음 기능을 포함한다.

* Market Risk 데이터 수집
* Risk Factor 관리
* Sensitivity 계산
* Risk Weight 적용
* Bucket Aggregation
* Capital Aggregation
* 결과 생성 및 제공

다음은 범위에 포함하지 않는다.

* 데이터베이스 물리 설계
* 프로그래밍 언어
* UI/UX
* 운영 인프라 구성

---

# 3. Architectural Principles

본 아키텍처는 다음 원칙을 따른다.

1. Layered Architecture
2. Separation of Concerns
3. Formula Independence
4. Technology Neutrality
5. Deterministic Processing
6. Traceability
7. Scalability
8. Reusability

---

# 4. Logical Architecture

```text
                    +----------------------+
                    |     Market Data      |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Risk Factor Manager  |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Sensitivity Engine   |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Risk Weight Engine   |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Bucket Aggregator    |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Capital Aggregator   |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Reporting Interface  |
                    +----------------------+
```

각 컴포넌트는 단일 책임(Single Responsibility Principle)을 유지한다.

---

# 5. Component Responsibilities

| Component           | Responsibility            |
| ------------------- | ------------------------- |
| Market Data         | 시장 데이터 제공                 |
| Risk Factor Manager | 위험요인 관리 및 정규화             |
| Sensitivity Engine  | Delta, Vega, Curvature 계산 |
| Risk Weight Engine  | 규제 Risk Weight 적용         |
| Bucket Aggregator   | Bucket 단위 집계              |
| Capital Aggregator  | 최종 규제자본 계산                |
| Reporting Interface | 결과 전달 및 보고                |

---

# 6. Data Flow

```text
Market Data
      │
      ▼
Risk Factors
      │
      ▼
Sensitivities
      │
      ▼
Weighted Sensitivities
      │
      ▼
Bucket Capitals
      │
      ▼
Market Risk Capital
      │
      ▼
Reports / API / Downstream Systems
```

데이터는 단방향으로 흐르며, 계산 단계는 이전 단계의 결과를 기반으로 수행된다.

---

# 7. Formula Integration

Architecture는 Formula Catalog를 다음과 같이 연결한다.

```text
FC-461
Delta Capital
      │
      ├──────────────┐
      │              │
FC-462         FC-463
Vega          Curvature
      │              │
      └──────┬───────┘
             ▼
FC-464
Capital Aggregation
             │
             ▼
Market Risk Capital
```

Formula는 독립적인 계산 모듈로 구성되며, Capital Aggregation에서 통합된다.

---

# 8. Traceability Architecture

모든 계산은 추적 가능해야 한다.

```text
Market Data
      │
      ▼
Risk Factor
      │
      ▼
Formula
      │
      ▼
Intermediate Result
      │
      ▼
Final Capital
```

각 단계의 입력과 출력은 감사(Audit) 및 모델 검증(Model Validation)을 위해 보존할 수 있어야 한다.

---

# 9. Integration with FRKP Layers

```text
Reference Library
        │
        ▼
Knowledge Base
        │
        ▼
Analysis
        │
        ▼
Mathematical Foundation
        │
        ▼
Formula Catalog
        │
        ▼
Implementation Guide
        │
        ▼
Architecture Guide
```

Architecture는 상위 계층에서 정의된 개념과 계산 계약을 시스템 구조로 구체화한다.

---

# 10. Quality Attributes

아키텍처는 다음 품질 특성을 만족해야 한다.

| Attribute       | Description              |
| --------------- | ------------------------ |
| Accuracy        | Formula와 동일한 계산 결과 보장    |
| Scalability     | 대규모 포트폴리오 처리 지원          |
| Performance     | 병렬 계산 및 효율적 집계 지원        |
| Maintainability | Formula 변경 시 영향 최소화      |
| Traceability    | 계산 이력 추적 가능              |
| Reusability     | 다른 Risk Engine에서도 재사용 가능 |

---

# 11. Extensibility

본 아키텍처는 향후 다음 기능을 추가할 수 있도록 설계한다.

* Internal Models Approach (IMA)
* Expected Shortfall (ES)
* Default Risk Charge (DRC)
* Residual Risk Add-On (RRAO)
* Stress Testing
* Scenario Analysis
* Intraday Risk Monitoring

---

# 12. Security and Governance

구현 시 다음 사항을 고려한다.

* 입력 데이터 무결성 검증
* 계산 결과 변경 이력 관리
* 권한 기반 접근 제어
* 감사 로그 생성
* 규제 보고 데이터 보존

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
Formula
      │
      ▼
Implementation
      │
      ▼
Architecture
```

Architecture Guide는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)의 최종 설계 계층이며, Formula와 Implementation을 시스템 구조로 통합한다.

---

# 14. Cross References

| Category                | Document                                          |
| ----------------------- | ------------------------------------------------- |
| Reference               | [RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md) |
| Knowledge               | [KB-261_MARKET_RISK_STANDARDIZED_APPROACH](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)          |
| Knowledge               | [KB-262_SENSITIVITY_BASED_METHOD](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)                   |
| Knowledge               | [KB-263_RISK_FACTOR_CATEGORIES](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)                     |
| Analysis                | [AN-261_WHY_FRTB_REPLACED_VAR](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)                      |
| Mathematical Foundation | [MF-461_COVARIANCE_MATRIX](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md)                          |
| Mathematical Foundation | [MF-462_PRINCIPAL_COMPONENT_ANALYSIS](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-462_PRINCIPAL_COMPONENT_ANALYSIS.md)               |
| Mathematical Foundation | [MF-463_EIGENVALUE_AND_EIGENVECTOR](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-463_EIGENVALUE_AND_EIGENVECTOR.md)                 |
| Formula                 | [FC-461_DELTA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-461_DELTA_CAPITAL_FORMULA.md)                      |
| Formula                 | [FC-462_VEGA_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-462_VEGA_CAPITAL_FORMULA.md)                       |
| Formula                 | [FC-463_CURVATURE_CAPITAL_FORMULA](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-463_CURVATURE_CAPITAL_FORMULA.md)                  |
| Formula                 | [FC-464_CAPITAL_AGGREGATION](../../04_Formula_Catalog/06_Market_Risk_Standardized_Approach/FC-464_CAPITAL_AGGREGATION.md)                        |
| Implementation          | [IMP-461_FRTB_SA_IMPLEMENTATION](../../06_Implementation_Guide/06_Market_Risk_Standardized_Approach/IMP-461_FRTB_SA_IMPLEMENTATION.md)                    |

---

# 15. Summary

본 문서는 FRTB Standardized Approach를 위한 기술 중립적 시스템 아키텍처를 정의하였다.

아키텍처는 Market Data부터 Risk Factor 관리, Sensitivity 계산, Risk Weight 적용, Bucket Aggregation 및 Capital Aggregation까지의 전체 처리 흐름을 계층적으로 구성하며, Formula Catalog와 Implementation Guide를 실제 Risk Engine 구조로 연결한다.

또한 정확성, 확장성, 추적 가능성 및 재사용성을 핵심 품질 목표로 하여 향후 Internal Models Approach(IMA), Expected Shortfall(ES) 등 추가 기능을 수용할 수 있는 기반을 제공한다.

---

# 16. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
