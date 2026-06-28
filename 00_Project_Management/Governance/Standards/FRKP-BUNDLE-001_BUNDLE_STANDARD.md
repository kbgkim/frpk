# FRKP-BUNDLE-001 — Bundle Standard

---

# Document Information

| Item          | Value                |
| ------------- | -------------------- |
| Standard ID   | FRKP-BUNDLE-001      |
| Document Name | Bundle Standard      |
| Version       | 1.1.0                |
| Status        | Active               |
| Category      | Governance Standard  |
| Created       | 2026-06-26           |
| Last Updated  | 2026-06-27           |
| Applies To    | All Bundle Documents |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../../README.md) > [Home](../../../README.md) > [Project Management](../../README.md) > [Governance](../FRKP-001_PROJECT_CHARTER.md) > [FRKP-BUNDLE-001 — Bundle Standard](FRKP-BUNDLE-001_BUNDLE_STANDARD.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FRKP-FORM-001](FRKP-FORM-001_FORMULA_STANDARD.md) |
| ⬆ Parent Bundle | None |
| ⬆ Parent Layer | [Governance](../../README.md) |
| ➡ Next | [FRKP-TPL-001](../Templates/FRKP-TPL-001_DOCUMENT_TEMPLATE.md) |

### Related Documents

- [FRKP-DOC-100](../FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md)
- [FRKP-DOC-001](FRKP-DOC-001_DOCUMENT_STANDARD.md)
- [FRKP-ID-001](FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md)
- [FRKP-FORM-001](FRKP-FORM-001_FORMULA_STANDARD.md)
- [FRKP-TPL-001](../Templates/FRKP-TPL-001_DOCUMENT_TEMPLATE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 Bundle 구성 원칙, 개발 절차, 산출물 기준, 품질 게이트 및 완료 조건을 정의한다.

Bundle은 FRKP의 기본 개발 단위(Unit of Delivery)이자 지식 생산 단위(Unit of Knowledge Production)이다.

모든 Bundle은 하나의 금융 리스크 도메인을 **Reference부터 Architecture까지 완결된 형태로 구성**하는 것을 목표로 한다.

---

# 2. Scope

본 표준은 다음에 적용한다.

* Bundle Planning
* Bundle Development
* Bundle Review
* Bundle Completion
* Bundle Freeze
* Bundle Maintenance

---

# 3. Bundle Definition

Bundle은 하나의 업무 영역을 다음 계층으로 완성하는 단위이다.

```text
Reference
    │
Knowledge
    │
Analysis
    │
Framework
    │
Formula
    │
Implementation
    │
Architecture
    │
Bundle Review
```

---

# 4. Bundle Objectives

각 Bundle은 다음 목표를 달성해야 한다.

* 하나의 금융 도메인을 완전하게 설명한다.
* 규제와 이론을 연결한다.
* Formula를 정의한다.
* 구현 절차를 정의한다.
* 시스템 구조를 정의한다.
* Bundle 단위로 독립적인 학습이 가능해야 한다.

---

# 5. Standard Deliverables

| Layer          | Prefix | Required |
| -------------- | ------ | :------: |
| Reference      | RL     |     ✔    |
| Knowledge      | KB     |     ✔    |
| Analysis       | AN     |     ✔    |
| Formula        | FC     |     ✔    |
| Implementation | IMP    |     ✔    |
| Architecture   | ARCH   |     ✔    |
| Bundle Review  | BUNDLE |     ✔    |

---

# 6. Optional Deliverables

Bundle 특성에 따라 다음 문서를 선택적으로 추가할 수 있다.

| Prefix | Description             |
| ------ | ----------------------- |
| MF     | Mathematical Foundation |
| EX     | Worked Example          |
| LAB    | Practical Laboratory    |
| CASE   | Case Study              |

선택 산출물은 Bundle의 성격에 따라 포함 여부를 결정한다.

---

# 7. Just-in-Time Mathematical Foundation

Mathematical Foundation(MF)은 모든 Bundle에 의무적으로 포함하지 않는다.

새로운 핵심 수학 개념이 최초로 등장하는 경우에만 작성한다.

개발 절차는 다음과 같다.

```text
Formula 작성

↓

새로운 수학 개념인가?

↓

YES

↓

MF 문서 작성

↓

Implementation 진행
```

예시

| Bundle     | MF Document                         |
| ---------- | ----------------------------------- |
| Bundle-005 | MF-451_HAZARD_RATE                  |
| Bundle-005 | MF-452_SURVIVAL_FUNCTION            |
| Bundle-005 | MF-453_DISCOUNT_FACTOR              |
| Bundle-006 | MF-461_PRINCIPAL_COMPONENT_ANALYSIS |

---

# 8. Bundle Lifecycle

모든 Bundle은 다음 생명주기를 따른다.

```text
Planned

↓

In Progress

↓

Internal Review

↓

Completed

↓

Frozen

↓

Maintenance
```

Frozen 상태에서는 규제 변경 또는 승인된 개선 요청이 없는 한 구조를 변경하지 않는다.

---

# 9. Bundle Development Workflow

```text
Reference

↓

Knowledge

↓

Analysis

↓

Framework

↓

Formula

↓

Need Mathematical Foundation?

↓

YES → MF 작성

↓

Implementation

↓

Architecture

↓

Bundle Review

↓

Freeze
```

---

# 10. Completion Criteria

Bundle은 다음 조건을 모두 만족해야 완료된다.

* 모든 필수 Deliverable 작성
* Cross Reference 연결
* Formula Coverage 확보
* Architecture 정의 완료
* Bundle Review 완료
* Governance Standard 준수

---

# 11. Quality Gates

Bundle 종료 시 다음 항목을 검증한다.

| Check                    | Required |
| ------------------------ | :------: |
| Deliverable Completeness |     ✔    |
| Traceability             |     ✔    |
| Formula Consistency      |     ✔    |
| Architecture Consistency |     ✔    |
| Governance Compliance    |     ✔    |
| Cross References         |     ✔    |

---

# 12. Governance Compliance

모든 Bundle은 다음 표준을 준수해야 한다.

* FRKP-DOC-001
* FRKP-TERM-001
* FRKP-ABBR-001
* FRKP-SYM-001
* FRKP-FORM-001
* FRKP-IMP-001
* FRKP-ARCH-001

---

# 13. Bundle Dependency

Bundle 간 의존성은 단방향으로 관리한다.

```text
Bundle-001

↓

Bundle-002

↓

Bundle-003

↓

Bundle-004

↓

Bundle-005
```

순환 의존성(Circular Dependency)은 허용하지 않는다.

---

# 14. Bundle Maintenance

Bundle이 완료된 이후에는 다음 항목만 유지보수 대상으로 한다.

* 규제 변경
* 오탈자 수정
* Worked Example 추가
* Cross Reference 보완
* Domain Dictionary 연결

---

# 15. Resource Allocation Guideline

프로젝트 전체 권장 비율은 다음과 같다.

| Activity               | Target |
| ---------------------- | -----: |
| Bundle Production      |    80% |
| Governance             |    10% |
| Dictionary Maintenance |     5% |
| Planning               |     5% |

Bundle 생산을 최우선으로 하며 Governance는 이를 지원하는 역할을 수행한다.

---

# 16. Relationship with Master Roadmap

Bundle은 Master Roadmap의 관리 단위이다.

Roadmap은 Bundle 단위로 진행 상황을 추적하며, 각 Bundle은 독립적인 완료 기준과 품질 게이트를 가진다.

---

# 17. Future Evolution

향후 Bundle 체계는 다음 영역으로 확장한다.

* Credit Valuation Adjustment (CVA)
* Market Risk Standardized Approach
* Operational Risk
* Liquidity Risk
* ICAAP
* Stress Testing
* Model Risk Management
* Climate Risk

---

# 18. Summary

Bundle은 FRKP의 핵심 개발 단위이며, 하나의 금융 리스크 도메인을 Reference부터 Architecture까지 완결된 지식 체계로 구성한다.

프로젝트는 **Bundle First**, **Governance Second**, **Mathematical Foundation On Demand** 전략을 채택하며, 이를 통해 지속적인 콘텐츠 생산과 장기적인 품질 유지의 균형을 확보한다.

---

# 19. Revision History

| Version | Date       | Description                                                                                                                  |
| ------- | ---------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1.0.0   | 2026-06-26 | Initial Bundle Standard                                                                                                      |
| 1.1.0   | 2026-06-27 | Added Just-in-Time Mathematical Foundation, Optional Deliverables, Bundle Production Strategy, Resource Allocation Guideline |
