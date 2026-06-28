# IMP-451 — CVA Implementation Guide

---

# Document Information

| Item          | Value                    |
| ------------- | ------------------------ |
| Document ID   | IMP-451                  |
| Document Name | CVA Implementation Guide |
| Version       | 1.0.0                    |
| Status        | Active                   |
| Category      | Implementation Guide     |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)               |
| Created       | 2026-06-27               |
| Last Updated  | 2026-06-27               |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Implementation Guide](../README.md) > [IMP-451 — CVA Implementation Guide](IMP-451_CVA_IMPLEMENTATION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Implementation Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
- [KB-252](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)
- [AN-251](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)
- [MF-451](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Credit Valuation Adjustment(CVA)를 Risk Engine 및 Formula Engine에서 구현하기 위한 구현 지침(Implementation Guide)을 정의한다.

본 문서는 코드 구현이 아니라 구현 원칙, 계산 순서, 모듈 책임 및 데이터 흐름을 정의하며, Formula Catalog를 실제 시스템으로 연결하는 구현 계약(Implementation Contract)의 역할을 수행한다.

---

# 2. Scope

본 문서는 다음 구현 범위를 다룬다.

* CVA Calculation Flow
* Formula Engine Integration
* Exposure Processing
* Default Probability Processing
* Discount Processing
* Result Composition
* Validation Strategy

다음 내용은 포함하지 않는다.

* Java 코드
* 특정 Framework
* Database 설계
* UI 구현
* 배치 스케줄링

---

# 3. Relationship within FRKP

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

Implementation Guide는 Formula Catalog를 실행 가능한 구현 단위로 연결한다.

---

# 4. Implementation Principles

모든 구현은 다음 원칙을 따른다.

1. Formula First
2. Technology Neutral
3. Deterministic Processing
4. Stateless Calculation
5. Immutable Input
6. Reusable Components
7. Traceable Calculation
8. Layer Separation

---

# 5. Required Inputs

CVA 계산에는 다음 입력이 필요하다.

| Input                  | Description       |
| ---------------------- | ----------------- |
| Portfolio Information  | 거래 포트폴리오          |
| Market Data            | 시장 데이터            |
| Exposure Profile       | Exposure Curve    |
| Hazard Rate            | Hazard Rate Curve |
| Recovery Rate          | Recovery Rate     |
| Discount Curve         | Discount Curve    |
| Netting Information    | 상계 정보             |
| Collateral Information | 담보 정보             |

---

# 6. Implementation Flow

```text
Market Data
        │
        ▼
Exposure Generation
        │
        ▼
Expected Exposure
        │
        ▼
Default Probability
        │
        ▼
LGD
        │
        ▼
Discount Factor
        │
        ▼
CVA Calculation
        │
        ▼
Validation
        │
        ▼
Result
```

각 단계는 독립적인 계산 책임을 가진다.

---

# 7. Processing Pipeline

```text
Input Collection
        │
        ▼
Normalization
        │
        ▼
Exposure Engine
        │
        ▼
Probability Engine
        │
        ▼
Discount Engine
        │
        ▼
CVA Engine
        │
        ▼
Result Builder
```

Pipeline은 순차적으로 실행되며, 각 단계는 이전 단계의 결과만 입력으로 사용한다.

---

# 8. Module Responsibilities

| Module             | Responsibility         |
| ------------------ | ---------------------- |
| Exposure Module    | Expected Exposure 계산   |
| Probability Module | Default Probability 계산 |
| Discount Module    | Discount Factor 계산     |
| LGD Module         | Loss Given Default 계산  |
| CVA Module         | 최종 CVA 계산              |
| Validation Module  | 입력 및 결과 검증             |
| Result Module      | 계산 결과 생성               |

---

# 9. Formula Mapping

| Formula | Implementation Responsibility |
| ------- | ----------------------------- |
| FC-451  | Default Probability Engine    |
| FC-452  | Exposure Engine               |
| FC-453  | CVA Engine                    |
| FC-454  | Capital Engine                |

Formula는 변경하지 않고 구현 모듈이 이를 실행한다.

---

# 10. Data Flow

```text
Portfolio
      │
      ▼
Exposure
      │
      ▼
Probability
      │
      ▼
Expected Loss
      │
      ▼
Discount
      │
      ▼
Present Value
      │
      ▼
CVA
```

---

# 11. Validation Strategy

다음 항목을 검증한다.

| Validation            | Description          |
| --------------------- | -------------------- |
| Required Input        | 필수 입력 존재 여부          |
| Currency Consistency  | 통화 일관성               |
| Time Grid Consistency | 시간축 일관성              |
| Exposure Positivity   | Positive Exposure 처리 |
| Probability Range     | 0 ≤ PD ≤ 1           |
| Recovery Range        | 0 ≤ Recovery ≤ 1     |
| Discount Range        | 0 < DF ≤ 1           |

---

# 12. Error Handling Strategy

구현은 다음 오류를 처리해야 한다.

| Error                   | Action             |
| ----------------------- | ------------------ |
| Missing Market Data     | Calculation Failed |
| Invalid Probability     | Validation Error   |
| Invalid Discount Factor | Validation Error   |
| Currency Mismatch       | Validation Error   |
| Missing Exposure        | Calculation Failed |

오류 처리 정책은 계산 결과와 분리하여 관리한다.

---

# 13. Performance Considerations

구현 시 고려 사항

* Exposure 재사용
* Discount Curve 캐싱
* Probability Curve 캐싱
* 병렬 시나리오 계산
* 불필요한 재계산 방지

최적화는 Formula 의미를 변경해서는 안 된다.

---

# 14. Relationship with Architecture

Implementation은 Architecture에서 다음 컴포넌트로 배치된다.

```text
Market Data Service
        │
        ▼
Exposure Engine
        │
        ▼
Probability Engine
        │
        ▼
CVA Engine
        │
        ▼
Capital Engine
```

Architecture는 본 문서의 구현 계약을 시스템 컴포넌트로 구체화한다.

---

# 15. Traceability

구현은 다음 문서와 추적 가능해야 한다.

| Layer                   | Document                                  |
| ----------------------- | ----------------------------------------- |
| Reference               | RL-150_CVA_OVERVIEW                       |
| Knowledge               | KB-251_CREDIT_VALUATION_ADJUSTMENT        |
| Knowledge               | KB-252_CVA_FRAMEWORK                      |
| Analysis                | AN-251_WHY_CVA_WAS_INTRODUCED             |
| Mathematical Foundation | MF-451_HAZARD_RATE                        |
| Mathematical Foundation | MF-452_SURVIVAL_FUNCTION                  |
| Mathematical Foundation | MF-453_DISCOUNT_FACTOR                    |
| Formula                 | FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE |
| Formula                 | FC-452_EXPECTED_EXPOSURE                  |
| Formula                 | FC-453_CREDIT_VALUATION_ADJUSTMENT        |
| Formula                 | FC-454_CVA_CAPITAL_CHARGE                 |

---

# 16. Implementation Checklist

| Check                    | Required |
| ------------------------ | :------: |
| Formula Mapping Complete |     ✔    |
| Input Validation         |     ✔    |
| Output Validation        |     ✔    |
| Stateless Processing     |     ✔    |
| Formula Traceability     |     ✔    |
| Module Separation        |     ✔    |
| Error Handling           |     ✔    |
| Technology Neutrality    |     ✔    |

---

# 17. Summary

본 문서는 CVA Formula Catalog를 실제 Risk Engine 구현으로 연결하기 위한 Implementation Guide를 정의하였다.

구현은 Formula를 변경하지 않고 실행하며, Exposure, Default Probability, Discount Factor 및 LGD를 독립적인 모듈로 처리한 후 이를 조합하여 최종 Credit Valuation Adjustment를 계산한다.

Implementation Guide는 Formula와 Architecture 사이의 구현 계약으로서, 기술 스택과 무관하게 일관된 구현 원칙과 데이터 흐름을 제공한다.

---

# 18. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
