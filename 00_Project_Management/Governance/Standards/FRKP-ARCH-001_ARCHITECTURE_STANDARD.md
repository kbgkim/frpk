# FRKP-ARCH-001 — Architecture Documentation Standard

---

# Document Information

| Item          | Value                               |
| ------------- | ----------------------------------- |
| Standard ID   | FRKP-ARCH-001                       |
| Document Name | Architecture Documentation Standard |
| Version       | 1.0.0                               |
| Status        | Active                              |
| Category      | Governance Standard                 |
| Created       | 2026-06-26                          |
| Last Updated  | 2026-06-26                          |
| Applies To    | All `ARCH-*` Documents              |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 모든 **Architecture Guide(ARCH-xxx)** 문서에 적용되는 공통 작성 기준을 정의한다.

Architecture Guide의 목적은 시스템의 구조적 설계와 책임을 정의하는 것이며, 구현 코드나 알고리즘을 설명하는 것이 아니다.

본 표준은 모든 Architecture 문서의 상위 규격(Normative Standard)으로 적용된다.

---

# 2. Scope

본 표준은 다음 문서에 적용한다.

* ARCH-4xx (Credit Risk)
* ARCH-5xx (Market Risk)
* ARCH-6xx (Liquidity Risk)
* ARCH-7xx (Operational Risk)
* ARCH-8xx (Mathematical Foundation)
* ARCH-9xx (AI)

향후 생성되는 모든 `ARCH-*` 문서에도 동일하게 적용한다.

---

# 3. Position in FRKP

Architecture Guide는 FRKP 6계층 구조의 마지막 계층이다.

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
Formula
        │
        ▼
Implementation
        │
        ▼
Architecture
```

Architecture는 Formula와 Implementation을 시스템 컴포넌트와 계층 구조로 조직한다.

---

# 4. Responsibilities

Architecture Guide는 다음 책임을 가진다.

* 시스템 계층 정의
* 컴포넌트 책임 정의
* 모듈 간 의존성 정의
* 데이터 흐름 정의
* 확장성(Scalability) 설계
* 비기능 요구사항(Non-functional Requirements) 정의
* Traceability 확보

다음 내용은 포함하지 않는다.

* 업무 개념 설명
* 규제 해설
* 수학 공식
* 상세 알고리즘
* 프로그래밍 언어별 구현

---

# 5. Architecture Principles

모든 Architecture 문서는 다음 원칙을 따른다.

1. Layered Architecture
2. Single Responsibility
3. Separation of Concerns
4. Loose Coupling
5. High Cohesion
6. Deterministic Processing
7. Traceability
8. Configurability
9. Extensibility

---

# 6. Standard Architecture Layers

권장 계층 구조는 다음과 같다.

```text
Presentation
        │
        ▼
Application
        │
        ▼
Domain
        │
        ▼
Calculation
        │
        ▼
Infrastructure
```

도메인 특성에 따라 계층을 추가하거나 생략할 수 있으나, 책임 분리는 유지해야 한다.

---

# 7. Component Decomposition

컴포넌트는 기능이 아닌 책임 중심으로 분리한다.

예시

```text
Input Adapter

Validation Service

Calculation Engine

Aggregation Service

Output Adapter
```

각 컴포넌트는 하나의 명확한 책임만 가진다.

---

# 8. Mandatory Sections

모든 `ARCH-*` 문서는 최소한 다음 장을 포함해야 한다.

1. Purpose
2. Architecture Scope
3. Architecture Principles
4. Layer Architecture
5. Component Architecture
6. Data Flow
7. Dependency Rules
8. Integration Points
9. Non-functional Requirements
10. Deployment Considerations (필요 시)
11. Traceability
12. Relationship with FRKP
13. Summary
14. Revision History

---

# 9. Layer Dependency Rules

의존성은 항상 상위 계층에서 하위 계층으로만 허용한다.

```text
Presentation
      │
      ▼
Application
      │
      ▼
Domain
      │
      ▼
Calculation
      │
      ▼
Infrastructure
```

순환 의존(Circular Dependency)은 허용하지 않는다.

---

# 10. Data Flow Standard

데이터 흐름은 반드시 단계적으로 표현한다.

```text
Input
   │
   ▼
Validation
   │
   ▼
Calculation
   │
   ▼
Aggregation
   │
   ▼
Output
```

양방향 데이터 흐름은 특별한 사유가 없는 한 사용하지 않는다.

---

# 11. Component Communication

컴포넌트 간 통신은 명시적인 계약(Contract)을 통해 수행한다.

* Input Contract
* Output Contract
* Interface Contract

구현 클래스 간 직접 결합은 지양한다.

---

# 12. Non-functional Requirements

모든 Architecture 문서는 다음 항목을 검토해야 한다.

* Performance
* Scalability
* Availability
* Reliability
* Maintainability
* Testability
* Observability
* Configurability
* Security (해당 시)

---

# 13. Traceability

Architecture는 Formula 및 Implementation과 연결되어야 한다.

```text
Formula
    │
    ▼
Implementation
    │
    ▼
Architecture
```

각 컴포넌트는 관련 Formula와 Implementation 문서를 참조해야 한다.

---

# 14. Relationship Rules

Architecture 문서는 반드시 다음 문서를 참조한다.

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
Formula
        │
        ▼
Implementation
        │
        ▼
Architecture
```

Architecture는 상위 계층의 정의를 변경하지 않는다.

---

# 15. Naming Convention

컴포넌트 명칭은 책임 중심으로 작성한다.

권장 예시

```text
TradeProcessor

RiskCalculator

PortfolioAggregator

ExposureEngine

ResultPublisher
```

기술 구현(Java, Spring 등)에 종속적인 이름은 사용하지 않는다.

---

# 16. Architecture Review Checklist

Architecture Review 시 다음 항목을 확인한다.

| Check                       | Required |
| --------------------------- | :------: |
| Layer Separation            |     ✔    |
| Component Responsibilities  |     ✔    |
| Dependency Rules            |     ✔    |
| Data Flow                   |     ✔    |
| Integration Points          |     ✔    |
| Non-functional Requirements |     ✔    |
| Traceability                |     ✔    |
| Formula Alignment           |     ✔    |
| Implementation Alignment    |     ✔    |

---

# 17. Compliance

모든 `ARCH-*` 문서는 본 표준을 준수해야 한다.

예외가 필요한 경우에는 문서 내에 예외 사유와 영향을 명시한다.

---

# 18. Relationship with Other Standards

본 표준은 다음 표준과 함께 적용된다.

```text
FRKP-DOC-001
      │
      ├── FRKP-KB-001
      ├── FRKP-FORM-001
      ├── FRKP-IMP-001
      ├── FRKP-ARCH-001
      └── FRKP-BUNDLE-001
```

Architecture Guide는 문서 표준과 Implementation 표준을 기반으로 시스템 구조를 정의한다.

---

# 19. Future Evolution

향후 다음 항목을 추가 표준으로 정의할 수 있다.

* Event-driven Architecture
* Distributed Calculation Architecture
* Batch Processing Architecture
* Real-time Risk Calculation Architecture
* Cloud-native Deployment Guidelines

---

# 20. Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-06-26 | Initial Standard |
