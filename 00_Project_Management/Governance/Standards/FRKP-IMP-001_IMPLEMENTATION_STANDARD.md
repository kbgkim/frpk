# FRKP-IMP-001 — Implementation Documentation Standard

---

# Document Information

| Item          | Value                                 |
| ------------- | ------------------------------------- |
| Standard ID   | FRKP-IMP-001                          |
| Document Name | Implementation Documentation Standard |
| Version       | 1.0.0                                 |
| Status        | Active                                |
| Category      | Governance Standard                   |
| Created       | 2026-06-26                            |
| Last Updated  | 2026-06-26                            |
| Applies To    | All `IMP-*` Documents                 |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 모든 **Implementation Guide(IMP-xxx)** 문서에 공통적으로 적용되는 작성 기준을 정의한다.

목적은 다음과 같다.

* 구현 문서의 일관성 확보
* Formula와 Architecture 사이의 책임 명확화
* 구현 절차의 표준화
* 재사용 가능한 구현 패턴 구축
* Bundle 간 문서 품질 유지

본 문서는 모든 Implementation 문서의 상위 규격(Normative Standard)으로 적용된다.

---

# 2. Scope

본 표준은 다음 문서에 적용한다.

* IMP-4xx (Credit Risk)
* IMP-5xx (Market Risk)
* IMP-6xx (Liquidity Risk)
* IMP-7xx (Operational Risk)
* IMP-8xx (Mathematics)
* IMP-9xx (AI)

향후 생성되는 모든 `IMP-*` 문서에도 동일하게 적용한다.

---

# 3. Position in FRKP

Implementation Guide는 FRKP 6계층 구조의 다섯 번째 계층이다.

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

Implementation은 **Formula를 실행 절차로 변환**하며, Architecture는 이를 **시스템 구조**로 배치한다.

---

# 4. Responsibilities

Implementation Guide의 책임은 다음과 같다.

* Formula 실행 절차 정의
* Processing Pipeline 정의
* Module Decomposition 정의
* Input / Output Contract 정의
* Validation 절차 정의
* Error Handling 정의
* Performance Strategy 정의
* Traceability 확보

다음 내용은 포함하지 않는다.

* 업무 개념 설명
* 규제 배경 설명
* 수학적 증명
* 시스템 배포 구조
* 클래스 설계

---

# 5. Design Principles

모든 Implementation Guide는 다음 원칙을 따른다.

1. Formula와 Implementation을 분리한다.
2. Architecture와 Implementation을 분리한다.
3. 계산 순서를 변경하지 않는다.
4. 계산 결과는 결정적(Deterministic)이어야 한다.
5. 계산 과정은 추적 가능해야 한다.
6. 모듈은 단일 책임(Single Responsibility)을 가진다.
7. 구현은 규제 변경에 대응 가능해야 한다.

---

# 6. Standard Processing Pipeline

모든 구현 문서는 가능한 한 다음 파이프라인을 따른다.

```text
Input
    │
    ▼
Validation
    │
    ▼
Classification
    │
    ▼
Calculation
    │
    ▼
Aggregation
    │
    ▼
Post Processing
    │
    ▼
Output
```

도메인에 따라 일부 단계는 생략할 수 있다.

---

# 7. Standard Module Structure

모듈은 다음 구조를 권장한다.

```text
Validator

Classifier

PreProcessor

Calculator

Aggregator

PostProcessor

OutputBuilder
```

각 모듈은 하나의 책임만 가진다.

---

# 8. Mandatory Sections

모든 `IMP-*` 문서는 최소한 다음 장(Section)을 포함해야 한다.

1. Purpose
2. Implementation Scope
3. Processing Pipeline
4. Implementation Layers
5. Input Contract
6. Validation Stage
7. Core Calculation Process
8. Output Contract
9. Module Decomposition
10. Error Handling Strategy
11. Performance Strategy
12. Traceability
13. Relationship with FRKP
14. Summary
15. Revision History

필요한 경우 도메인 특화 장을 추가할 수 있다.

---

# 9. Input Contract Standard

입력 계약은 다음을 정의해야 한다.

* 입력 데이터
* 데이터 형식
* 필수 여부
* 검증 조건
* 출처

예시

| Input       | Required | Description |
| ----------- | :------: | ----------- |
| Portfolio   |     ✔    | 거래 포트폴리오    |
| Market Data |     ✔    | 시장 데이터      |
| Parameters  |     ✔    | 규제 파라미터     |

---

# 10. Output Contract Standard

출력 계약은 다음을 정의해야 한다.

* 출력 값
* 의미
* 계산 완료 조건
* 후속 문서와의 연결

예시

| Output | Description               |
| ------ | ------------------------- |
| EAD    | Exposure at Default       |
| RC     | Replacement Cost          |
| PFE    | Potential Future Exposure |

---

# 11. Validation Standard

Validation은 계산 전에 수행한다.

최소 검증 항목

* Null 검사
* 데이터 형식
* 중복
* 범위
* 업무 규칙
* 규제 파라미터

Validation 실패 시 계산을 중단하고 오류를 반환한다.

---

# 12. Error Handling Standard

오류는 다음 유형으로 구분한다.

| Type                | Example      |
| ------------------- | ------------ |
| Validation Error    | Null, Format |
| Business Error      | 계약 불일치       |
| Configuration Error | 규제 파라미터 누락   |
| Calculation Error   | 계산 불능        |
| System Error        | 런타임 오류       |

각 오류는 원인과 발생 단계를 함께 기록한다.

---

# 13. Performance Standard

모든 Implementation Guide는 다음 항목을 검토한다.

* 캐싱(Caching)
* 병렬 처리(Parallel Processing)
* 증분 계산(Incremental Calculation)
* 불변 객체(Immutable Object)
* 메모리 사용
* 대량 데이터 처리

적용 대상이 없으면 "해당 없음"으로 명시한다.

---

# 14. Traceability Standard

모든 구현은 입력부터 출력까지 추적 가능해야 한다.

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

중간 산출물도 조회 가능해야 한다.

---

# 15. Relationship Rules

Implementation 문서는 반드시 다음 문서를 참조해야 한다.

```text
Reference

↓

Knowledge

↓

Analysis

↓

Formula

↓

Implementation

↓

Architecture
```

Formula 없이 Implementation을 정의해서는 안 된다.

---

# 16. Naming Convention

모듈 이름은 다음 패턴을 권장한다.

```text
SomethingValidator

SomethingClassifier

SomethingCalculator

SomethingAggregator

SomethingProcessor

SomethingBuilder
```

역할이 이름에서 명확히 드러나야 한다.

---

# 17. Non-functional Requirements

모든 구현은 다음 특성을 고려한다.

* Deterministic
* Reproducible
* Testable
* Maintainable
* Extensible
* Traceable
* Configurable

---

# 18. Review Checklist

Implementation Review 시 다음 항목을 확인한다.

| Check                 | Required |
| --------------------- | :------: |
| Formula Separation    |     ✔    |
| Pipeline Defined      |     ✔    |
| Input Contract        |     ✔    |
| Output Contract       |     ✔    |
| Validation            |     ✔    |
| Error Handling        |     ✔    |
| Performance           |     ✔    |
| Traceability          |     ✔    |
| Architecture Boundary |     ✔    |

---

# 19. Compliance

모든 `IMP-*` 문서는 본 표준을 준수해야 한다.

표준에서 벗어나는 경우에는 문서 내에 예외 사유를 명시해야 한다.

---

# 20. Future Evolution

향후 다음 표준과 연계한다.

* FRKP-ARC-001_ARCHITECTURE_STANDARD
* FRKP-FORM-001_FORMULA_STANDARD
* FRKP-KB-001_KNOWLEDGE_STANDARD
* FRKP-DOC-001_DOCUMENT_STANDARD

---

# 21. Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-06-26 | Initial Standard |
