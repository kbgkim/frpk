# ARCH-751 — CVA Architecture

---

# Document Information

| Item          | Value              |
| ------------- | ------------------ |
| Document ID   | ARCH-751           |
| Document Name | CVA Architecture   |
| Version       | 1.0.0              |
| Status        | Active             |
| Category      | Architecture Guide |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)         |
| Created       | 2026-06-27         |
| Last Updated  | 2026-06-27         |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Architecture Guide](../README.md) > [ARCH-751 — CVA Architecture](ARCH-751_CVA_ARCHITECTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Architecture Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
- [KB-252](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)
- [AN-251](../../03_Analysis/05_CVA/AN-251_WHY_CVA_WAS_INTRODUCED.md)
- [MF-451](../../05_Mathematical_Foundation/05_CVA/MF-451_HAZARD_RATE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Credit Valuation Adjustment(CVA)를 계산하기 위한 시스템 아키텍처를 정의한다.

Architecture는 Formula를 시스템 컴포넌트로 배치하고 각 모듈의 책임, 계층 간 의존성, 데이터 흐름 및 확장 원칙을 정의한다.

본 문서는 기술 스택에 독립적인 논리 아키텍처(Logical Architecture)를 제공한다.

---

# 2. Architecture Objectives

본 Architecture는 다음 목표를 가진다.

* Formula와 구현 분리
* 모듈 간 낮은 결합도
* 높은 재사용성
* 병렬 계산 지원
* 확장 가능한 Risk Engine
* Formula Traceability 확보

---

# 3. Position in FRKP

```text id="2m4onl"
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

Architecture는 Formula와 Implementation을 실제 시스템 구조로 조직하는 계층이다.

---

# 4. Logical Architecture

```text id="l4frva"
                Market Data
                     │
                     ▼
            Market Data Service
                     │
                     ▼
        +-------------------------+
        |     Exposure Engine     |
        +-------------------------+
                     │
                     ▼
        +-------------------------+
        |   Probability Engine    |
        +-------------------------+
                     │
                     ▼
        +-------------------------+
        |     Discount Engine     |
        +-------------------------+
                     │
                     ▼
        +-------------------------+
        |        LGD Engine       |
        +-------------------------+
                     │
                     ▼
        +-------------------------+
        |        CVA Engine       |
        +-------------------------+
                     │
                     ▼
        +-------------------------+
        |     Capital Engine      |
        +-------------------------+
                     │
                     ▼
              Result Service
```

---

# 5. Component Responsibilities

| Component           | Responsibility                       |
| ------------------- | ------------------------------------ |
| Market Data Service | 시장 데이터 제공                            |
| Exposure Engine     | Expected Exposure 계산                 |
| Probability Engine  | Hazard Rate 및 Default Probability 계산 |
| Discount Engine     | Discount Factor 계산                   |
| LGD Engine          | Loss Given Default 계산                |
| CVA Engine          | FC-453 실행                            |
| Capital Engine      | FC-454 실행                            |
| Result Service      | 결과 생성 및 제공                           |

각 컴포넌트는 단일 책임 원칙(Single Responsibility Principle)을 따른다.

---

# 6. Layered Architecture

```text id="glhk2i"
Presentation Layer
        │
        ▼
Application Layer
        │
        ▼
Risk Engine Layer
        │
        ▼
Formula Engine Layer
        │
        ▼
Domain Layer
        │
        ▼
Infrastructure Layer
```

CVA 계산은 Risk Engine과 Formula Engine을 중심으로 수행된다.

---

# 7. Processing Flow

```text id="c5y3gp"
Portfolio
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
Credit Valuation Adjustment
      │
      ▼
Capital Charge
      │
      ▼
Result
```

---

# 8. Formula Integration

| Formula | Engine             |
| ------- | ------------------ |
| FC-451  | Probability Engine |
| FC-452  | Exposure Engine    |
| FC-453  | CVA Engine         |
| FC-454  | Capital Engine     |

Formula Engine은 Formula Catalog를 변경하지 않고 실행한다.

---

# 9. Data Model

```text id="vw7j2n"
Portfolio

↓

Trade

↓

Netting Set

↓

Exposure Profile

↓

Probability Curve

↓

Discount Curve

↓

CVA Result
```

각 데이터 모델은 불변(Immutable) 객체로 관리하는 것을 권장한다.

---

# 10. Service Interfaces

Architecture는 다음 논리 서비스 인터페이스를 가진다.

| Service             | Responsibility    |
| ------------------- | ----------------- |
| Exposure Service    | Exposure 제공       |
| Probability Service | PD 제공             |
| Discount Service    | Discount 제공       |
| LGD Service         | LGD 제공            |
| CVA Service         | CVA 계산            |
| Capital Service     | Capital Charge 계산 |

서비스 인터페이스는 구현 기술과 독립적이다.

---

# 11. Dependency Rules

의존성은 단방향으로 유지한다.

```text id="m44g8h"
Market Data

↓

Exposure

↓

Probability

↓

Discount

↓

CVA

↓

Capital
```

상위 계층은 하위 계층의 구현 세부사항을 참조하지 않는다.

---

# 12. Scalability

Architecture는 다음 확장을 지원해야 한다.

* 대규모 Portfolio
* Multi-Currency
* Multi-Netting Set
* Monte Carlo Simulation
* Parallel Processing
* Distributed Execution

---

# 13. Performance Strategy

성능 향상을 위해 다음 전략을 적용할 수 있다.

* Exposure Cache
* Discount Curve Cache
* Probability Cache
* Parallel Scenario Processing
* Immutable Data Model
* Lazy Evaluation

최적화는 Formula 의미를 변경해서는 안 된다.

---

# 14. Error Handling Architecture

```text id="zmjlwm"
Validation

↓

Calculation

↓

Error Classification

↓

Error Report

↓

Audit Log
```

계산 오류와 시스템 오류를 분리하여 관리한다.

---

# 15. Traceability

Architecture는 다음 문서와 추적 가능해야 한다.

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
| Implementation          | IMP-451_CVA_IMPLEMENTATION                |

---

# 16. Architecture Review Checklist

| Check                 | Required |
| --------------------- | :------: |
| Component Separation  |     ✔    |
| Layer Independence    |     ✔    |
| Formula Traceability  |     ✔    |
| Technology Neutrality |     ✔    |
| Scalability           |     ✔    |
| Stateless Processing  |     ✔    |
| Reusability           |     ✔    |
| Error Isolation       |     ✔    |

---

# 17. Summary

본 문서는 Credit Valuation Adjustment를 위한 논리 아키텍처를 정의하였다.

Architecture는 Exposure Engine, Probability Engine, Discount Engine, LGD Engine, CVA Engine 및 Capital Engine을 독립적인 컴포넌트로 구성하며, Formula Catalog에서 정의한 계산 계약을 시스템 구조로 구현한다.

또한 Formula Engine과 Risk Engine의 책임을 분리하고, 계층 간 단방향 의존성과 높은 재사용성을 유지함으로써 다양한 규제 및 리스크 분석 시나리오에 확장 가능한 아키텍처를 제공한다.

---

# 18. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
