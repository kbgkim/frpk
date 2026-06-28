# IMP-461 — FRTB Standardized Approach Implementation Guide

---

# Document Information

| Item          | Value                                           |
| ------------- | ----------------------------------------------- |
| Document ID   | IMP-461                                         |
| Document Name | FRTB Standardized Approach Implementation Guide |
| Version       | 1.0.0                                           |
| Status        | Active                                          |
| Category      | Implementation Guide                            |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                                      |
| Domain        | Market Risk                                     |
| Created       | 2026-06-27                                      |
| Last Updated  | 2026-06-27                                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Implementation Guide](../README.md) > [IMP-461 — FRTB Standardized Approach Implementation Guide](IMP-461_FRTB_SA_IMPLEMENTATION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Implementation Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-160](../../01_Reference_Library/06_Market_Risk_Standardized_Approach/RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)
- [KB-261](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)
- [KB-263](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)
- [AN-261](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB) Standardized Approach(SA)의 구현 원칙과 시스템 구성 방안을 정의한다.

본 문서는 Formula Catalog(FC-461 ~ FC-464)를 실제 Risk Engine에서 구현하기 위한 기술 중립적(Technology Neutral) 구현 가이드이다.

---

# 2. Scope

본 문서는 다음 Formula를 구현 대상으로 한다.

* FC-461 Delta Capital Formula
* FC-462 Vega Capital Formula
* FC-463 Curvature Capital Formula
* FC-464 Capital Aggregation

구현 언어, 데이터베이스 및 프레임워크에는 의존하지 않는다.

---

# 3. Implementation Objectives

구현 목표는 다음과 같다.

* Formula의 정확한 재현
* 규제 계산의 추적 가능성 확보
* 재사용 가능한 계산 컴포넌트 제공
* 대용량 포트폴리오 처리 지원
* 결정론적(Deterministic) 계산 보장

---

# 4. Overall Processing Flow

```text
Market Data
        │
        ▼
Risk Factor Loader
        │
        ▼
Sensitivity Calculator
        │
        ▼
Risk Weight Processor
        │
        ▼
Bucket Aggregator
        │
        ▼
Capital Aggregator
        │
        ▼
Result Publisher
```

각 단계는 독립적인 책임을 가지며 순차적으로 수행된다.

---

# 5. Logical Components

구현은 다음 논리 컴포넌트로 구성한다.

| Component               | Responsibility            |
| ----------------------- | ------------------------- |
| Risk Factor Loader      | 위험요인 데이터 수집               |
| Sensitivity Calculator  | Delta, Vega, Curvature 계산 |
| Risk Weight Processor   | 규제 Risk Weight 적용         |
| Bucket Aggregator       | Bucket 단위 집계              |
| Cross-Bucket Aggregator | Bucket 간 집계               |
| Capital Aggregator      | 최종 자본 계산                  |
| Result Publisher        | 결과 생성 및 전달                |

---

# 6. Processing Pipeline

```text
Load Inputs
      │
      ▼
Validate
      │
      ▼
Calculate Sensitivities
      │
      ▼
Apply Risk Weights
      │
      ▼
Within-Bucket Aggregation
      │
      ▼
Cross-Bucket Aggregation
      │
      ▼
Market Risk Capital
```

모든 단계는 입력과 출력을 명확히 정의해야 한다.

---

# 7. Input Model

최소 입력 정보는 다음과 같다.

| Input              | Description |
| ------------------ | ----------- |
| Instrument Data    | 금융상품 정보     |
| Market Data        | 시장 데이터      |
| Risk Factors       | 위험요인        |
| Risk Weights       | 감독기관 규정     |
| Correlation Matrix | 상관관계        |
| Bucket Mapping     | Bucket 정의   |

---

# 8. Output Model

구현 결과는 최소한 다음 정보를 포함한다.

| Output              | Description  |
| ------------------- | ------------ |
| Delta Capital       | Delta 자본     |
| Vega Capital        | Vega 자본      |
| Curvature Capital   | Curvature 자본 |
| Market Risk Capital | 최종 시장위험 자본   |
| Calculation Trace   | 계산 이력        |

---

# 9. Traceability Requirements

모든 계산은 추적 가능해야 한다.

```text
Input
   │
   ▼
Formula
   │
   ▼
Intermediate Result
   │
   ▼
Final Result
```

각 단계의 중간 결과는 감사(Audit) 및 검증(Model Validation)을 위해 재현 가능해야 한다.

---

# 10. Error Handling

구현은 다음 오류를 처리해야 한다.

| Error                | Handling         |
| -------------------- | ---------------- |
| Missing Market Data  | 계산 중단 또는 정책 적용   |
| Invalid Risk Weight  | Validation Error |
| Unknown Risk Factor  | 오류 기록 및 정책 적용    |
| Invalid Correlation  | 계산 중단            |
| Bucket Mapping Error | Validation Error |

오류 처리 정책은 규제 요건과 시스템 운영 정책에 따라 정의한다.

---

# 11. Performance Considerations

구현 시 다음 사항을 고려한다.

* 대용량 포트폴리오 병렬 처리
* Risk Factor 캐싱
* 공통 계산 재사용
* Bucket 단위 병렬 집계
* 메모리 사용 최소화

성능 최적화는 계산 결과를 변경해서는 안 된다.

---

# 12. Determinism

동일한 입력 데이터는 항상 동일한 결과를 생성해야 한다.

결과는 다음 조건을 만족한다.

* 순서 독립성
* 반복 실행 일관성
* 플랫폼 독립성
* 구현 언어 독립성

---

# 13. Validation Strategy

구현 검증은 다음 수준에서 수행한다.

| Level              | Purpose               |
| ------------------ | --------------------- |
| Formula Validation | Formula Catalog 일치 여부 |
| Component Test     | 개별 컴포넌트 검증            |
| Integration Test   | 전체 파이프라인 검증           |
| Regulatory Test    | 규제 예제 검증              |
| Regression Test    | 변경 영향 확인              |

---

# 14. Relationship with FRKP

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

Implementation Guide는 Formula Catalog를 실제 Risk Engine으로 구현하기 위한 기술적 연결 계층이다.

---

# 15. Cross References

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
| Architecture            | [ARCH-761_MARKET_RISK_SA_ARCHITECTURE](../../07_Architecture/06_Market_Risk_Standardized_Approach/ARCH-761_MARKET_RISK_SA_ARCHITECTURE.md) *(Planned)*  |

---

# 16. Summary

본 문서는 FRTB Standardized Approach의 Formula Catalog를 실제 Risk Engine으로 구현하기 위한 기술 중립적인 구현 가이드를 제공한다.

구현은 Risk Factor 수집, Sensitivity 계산, Risk Weight 적용, Bucket 집계 및 Capital Aggregation의 단계로 구성되며, 정확성, 재현성 및 추적 가능성을 보장해야 한다.

본 문서는 Bundle-006의 Implementation Layer를 구성하며, 이후 Architecture Guide에서 시스템 구조로 구체화된다.

---

# 17. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
