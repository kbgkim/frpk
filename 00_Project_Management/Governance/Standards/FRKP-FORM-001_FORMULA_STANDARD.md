# FRKP-FORM-001 — Formula Documentation Standard

---

# Document Information

| Item          | Value                                                                    |
| ------------- | ------------------------------------------------------------------------ |
| Standard ID   | FRKP-FORM-001                                                            |
| Document Name | Formula Documentation Standard                                           |
| Version       | 1.1.0                                                                    |
| Status        | Active                                                                   |
| Category      | Governance Standard                                                      |
| Created       | 2026-06-26                                                               |
| Last Updated  | 2026-06-27                                                               |
| Applies To    | All `FC-*` Documents                                                     |
| Updated By    | FRKP Governance                                                          |
| Reason        | Formula Asset Model, Dependency Model 및 Computational Characteristics 추가 |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../../README.md) > [Home](../../../README.md) > [Project Management](../../README.md) > [Governance](../FRKP-001_PROJECT_CHARTER.md) > [FRKP-FORM-001 — Formula Documentation Standard](FRKP-FORM-001_FORMULA_STANDARD.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FRKP-ID-001](FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md) |
| ⬆ Parent Bundle | None |
| ⬆ Parent Layer | [Governance](../../README.md) |
| ➡ Next | [FRKP-BUNDLE-001](FRKP-BUNDLE-001_BUNDLE_STANDARD.md) |

### Related Documents

- [FRKP-DOC-100](../FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md)
- [FRKP-DOC-001](FRKP-DOC-001_DOCUMENT_STANDARD.md)
- [FRKP-ID-001](FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md)
- [FRKP-BUNDLE-001](FRKP-BUNDLE-001_BUNDLE_STANDARD.md)
- [FRKP-TPL-001](../Templates/FRKP-TPL-001_DOCUMENT_TEMPLATE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 모든 **Formula Catalog(FC-xxx)** 문서에 적용되는 공통 작성 기준을 정의한다.

Formula Catalog는 금융 규제, 금융공학 및 위험관리에서 사용하는 계산 규칙을 **구현과 독립적으로 기술**하기 위한 문서이며, FRKP에서 **재사용 가능한 Formula Asset**으로 관리된다.

본 표준은 모든 Formula 문서의 상위 규격(Normative Standard)으로 적용된다.

---

# 2. Scope

본 표준은 다음 문서에 적용한다.

* FC-4xx (Credit Risk)
* FC-5xx (Market Risk)
* FC-6xx (Liquidity Risk)
* FC-7xx (Operational Risk)
* FC-8xx (Cross-domain / Common Formula)
* FC-9xx (Artificial Intelligence & Analytics)

향후 생성되는 모든 `FC-*` 문서에도 동일하게 적용한다.

---

# 3. Position in FRKP

Formula Catalog는 FRKP의 다섯 번째 Knowledge Layer이다.

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

Formula는 **무엇을 계산하는지(What)** 를 정의하며, Implementation은 **어떻게 계산하는지(How)** 를 정의한다.

---

# 4. Responsibilities

Formula Catalog의 책임은 다음과 같다.

* 계산 목적 정의
* 업무적 의미 정의
* 규제적 의미 정의
* 수학적 정의
* 계산 계약(Calculation Contract)
* 입력과 출력 정의
* 계산 순서 정의
* Formula Engine 관점의 계산 책임 정의

다음 내용은 포함하지 않는다.

* 구현 코드
* 시스템 구조
* 클래스 설계
* 알고리즘 최적화
* 배포 구조

---

# 5. Formula Principles

모든 Formula 문서는 다음 원칙을 따른다.

1. Business Before Mathematics
2. Formula Before Implementation
3. Deterministic Calculation
4. Technology Neutral
5. Reproducible
6. Traceable
7. Composable
8. Immutable Definition

---

# 6. Mandatory Sections

모든 `FC-*` 문서는 최소한 다음 장을 포함해야 한다.

1. Purpose
2. Business Purpose
3. Regulatory Perspective (해당 시)
4. Mathematical Definition
5. Formula Interpretation
6. Input Contract
7. Computation Contract
8. Output Contract
9. Formula Engine Model
10. Formula Classification
11. Formula Dependency
12. Computational Characteristics
13. Relationship with FRKP
14. Summary
15. Revision History

---

# 7. Formula Lifecycle

```text
Business Requirement
        │
        ▼
Business Concept
        │
        ▼
Mathematical Foundation
        │
        ▼
Mathematical Formula
        │
        ▼
Calculation Contract
        │
        ▼
Implementation
```

Formula는 Business와 Implementation 사이의 계약이며 Mathematical Foundation을 기반으로 한다.

---

# 8. Mathematical Definition Standard

모든 Formula는 가능한 경우 다음을 포함한다.

* 수식
* 변수 정의
* 단위(Unit)
* 계산 범위
* 적용 조건
* 제약 조건

---

# 9. Input Contract Standard

입력은 구현 기술이 아닌 업무 개념으로 정의한다.

입력 데이터의 의미와 단위를 함께 정의한다.

---

# 10. Computation Contract Standard

계산 절차는 논리적 순서를 기술한다.

```text
Input
   │
   ▼
Normalization
   │
   ▼
Calculation
   │
   ▼
Aggregation
   │
   ▼
Result
```

---

# 11. Output Contract Standard

출력 계약은 다음을 정의한다.

* 결과 값
* 의미
* 단위
* 후속 Formula와의 연결

---

# 12. Formula Engine Model

Formula는 Formula Engine의 논리적 계산 단위로 표현한다.

```text
Input Collector
        │
        ▼
Normalizer
        │
        ▼
Calculator
        │
        ▼
Result Builder
```

---

# 13. Relationship Rules

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
```

---

# 14. Naming Convention

Formula 명칭은 계산 대상 중심으로 작성한다.

예)

* ExpectedCreditLoss
* ReplacementCost
* PotentialFutureExposure
* ExposureAtDefault
* Duration
* Convexity

---

# 15. Non-functional Requirements

Formula는 다음 특성을 만족해야 한다.

* Deterministic
* Technology Neutral
* Testable
* Traceable
* Independent
* Reusable

---

# 16. Formula Classification

모든 Formula는 Formula Asset으로 관리된다.

## Formula Type

* Definition
* Transformation
* Aggregation
* Approximation
* Regulatory
* Statistical
* Optimization

## Formula Nature

* Deterministic
* Stochastic
* Recursive
* Iterative
* Closed Form
* Numerical

## Formula Category

* Credit Risk
* Market Risk
* Liquidity Risk
* Operational Risk
* Financial Mathematics

---

# 17. Formula Dependency

모든 Formula는 선행 Formula 및 후행 Formula를 명시한다.

권장 항목

* Depends On
* Input Formula
* Produces
* Consumed By

예시

```text
MF-451
    │
    ▼
FC-451
    │
    ▼
FC-452
    │
    ▼
FC-453
```

---

# 18. Computational Characteristics

Formula는 구현과 독립적으로 계산 특성을 기술할 수 있다.

| Property              | Example |
| --------------------- | ------- |
| Time Dependency       | Yes     |
| Closed Form           | Yes     |
| Numerical Integration | Yes     |
| Monte Carlo Required  | No      |
| Matrix Operation      | No      |
| Vector Operation      | No      |
| Parallelizable        | Yes     |
| Complexity            | O(n)    |

---

# 19. Formula Graph

Formula는 독립적인 계산식이 아니라 Formula Network를 구성한다.

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
```

또는

```text
FC-451
      │
      ▼
FC-452
      │
      ▼
FC-453
      │
      ▼
FC-454
```

Formula Graph는 Formula Engine의 의존성 분석과 Knowledge Graph 구축의 기반이 된다.

---

# 20. Formula Review Checklist

| Check                         | Required |
| ----------------------------- | :------: |
| Business Purpose              |     ✔    |
| Mathematical Definition       |     ✔    |
| Input Contract                |     ✔    |
| Output Contract               |     ✔    |
| Computation Contract          |     ✔    |
| Formula Classification        |     ✔    |
| Formula Dependency            |     ✔    |
| Computational Characteristics |     ✔    |
| Technology Neutrality         |     ✔    |
| Traceability                  |     ✔    |

---

# 21. Compliance

모든 `FC-*` 문서는 본 표준을 준수해야 한다.

예외가 필요한 경우 문서 내에 사유와 영향을 명시한다.

---

# 22. Relationship with Other Standards

```text
FRKP-DOC-001
      │
      ├── FRKP-ID-001
      ├── FRKP-FORM-001
      ├── FRKP-ARCH-001
      ├── FRKP-BUNDLE-001
      ├── FRKP-TPL-001
      └── FRKP-TERM-001
```

Implementation은 Formula를 구현하며, Architecture는 Formula와 Implementation을 시스템 구조로 배치한다.

---

# 23. Future Evolution

향후 다음 내용을 추가 표준으로 확장할 수 있다.

* Formula Versioning
* Formula Composition Rules
* Formula Dependency Graph
* Formula Complexity Classification
* Formula Metadata Registry
* Formula Asset Repository
* Unit & Dimension Standard
* Formula Validation Rules
* Regulatory Formula Mapping
* Symbol Dictionary
* Automatic Formula Traceability

---

# 24. Revision History

| Version | Date       | Description                                                                                                                                                         |
| ------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1.1.0   | 2026-06-27 | Added Formula Asset Model, Formula Classification, Formula Dependency, Computational Characteristics, Formula Graph, and aligned with Mathematical Foundation layer |
| 1.0.0   | 2026-06-26 | Initial Standard                                                                                                                                                    |
