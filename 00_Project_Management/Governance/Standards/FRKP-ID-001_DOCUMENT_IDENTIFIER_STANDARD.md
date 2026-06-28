# FRKP-ID-001 — Document Identifier Standard

---

# Document Information

| Item            | Value                        |
| --------------- | ---------------------------- |
| Document ID     | FRKP-ID-001                  |
| Document Name   | Document Identifier Standard |
| Version         | 1.0.0                        |
| Status          | Frozen                       |
| Category        | Governance Standard          |
| Owner           | FRKP Governance              |
| Created         | 2026-06-27                   |
| Last Updated    | 2026-06-27                   |
| Parent Standard | [FRKP-DOC-001](FRKP-DOC-001_DOCUMENT_STANDARD.md)                 |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../../README.md) > [Home](../../../README.md) > [Project Management](../../README.md) > [Governance](../FRKP-001_PROJECT_CHARTER.md) > [FRKP-ID-001 — Document Identifier Standard](FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FRKP-DOC-001](FRKP-DOC-001_DOCUMENT_STANDARD.md) |
| ⬆ Parent Bundle | None |
| ⬆ Parent Layer | [Governance](../../README.md) |
| ➡ Next | [FRKP-FORM-001](FRKP-FORM-001_FORMULA_STANDARD.md) |

### Related Documents

- [FRKP-DOC-100](../FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md)
- [FRKP-DOC-001](FRKP-DOC-001_DOCUMENT_STANDARD.md)
- [FRKP-FORM-001](FRKP-FORM-001_FORMULA_STANDARD.md)
- [FRKP-BUNDLE-001](FRKP-BUNDLE-001_BUNDLE_STANDARD.md)
- [FRKP-TPL-001](../Templates/FRKP-TPL-001_DOCUMENT_TEMPLATE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에서 사용하는 **Document Identifier(문서 식별자)** 의 공식 표준을 정의한다.

Document Identifier는 프로젝트 전체에서 **유일(Unique)** 해야 하며, 문서의 유형, 목적 및 계층을 식별하는 공식 식별자로 사용한다.

본 문서는 Repository 전체의 Document Identifier Authority로 사용된다.

---

# 2. Scope

본 표준은 다음 문서에 적용된다.

* Governance Documents
* Project Management Documents
* Reference Library
* Knowledge Base
* Analysis
* Formula Catalog
* Mathematical Foundation
* Implementation Guide
* Architecture Guide
* Bundle Review
* Future Extensions

---

# 3. Design Principles

Document Identifier는 다음 원칙을 따른다.

1. **Uniqueness**
   하나의 Document ID는 Repository 전체에서 단 한 번만 사용한다.

2. **Stability**
   한 번 부여된 Document ID는 변경하지 않는다.

3. **Readability**
   Prefix만으로 문서의 성격을 식별할 수 있어야 한다.

4. **Extensibility**
   새로운 문서 유형이 추가되어도 기존 체계를 변경하지 않는다.

5. **Machine Friendliness**
   AI, 검색 시스템 및 자동화 도구가 쉽게 해석할 수 있어야 한다.

---

# 4. Identifier Format

모든 Document Identifier는 다음 형식을 따른다.

```text
<PREFIX>-<NUMBER>
```

또는 Governance Namespace의 경우

```text
FRKP-<CATEGORY>-<NUMBER>
```

예시

```text
KB-251
FC-443
ARCH-741
BUNDLE-005

FRKP-DOC-001
FRKP-ARCH-001
FRKP-ID-001
```

---

# 5. Governance Namespace

Governance 문서는 `FRKP` Namespace를 사용한다.

| Namespace   | Purpose                | Example         |
| ----------- | ---------------------- | --------------- |
| FRKP        | Project Governance     | FRKP-001        |
| FRKP-DOC    | Document Standards     | FRKP-DOC-001    |
| FRKP-ID     | Identifier Standards   | FRKP-ID-001     |
| FRKP-ARCH   | Architecture Standards | FRKP-ARCH-001   |
| FRKP-FORM   | Formula Standards      | FRKP-FORM-001   |
| FRKP-TERM   | Terminology Standards  | FRKP-TERM-001   |
| FRKP-SYM    | Symbol Standards       | FRKP-SYM-001    |
| FRKP-ABBR   | Abbreviation Standards | FRKP-ABBR-001   |
| FRKP-BUNDLE | Bundle Standards       | FRKP-BUNDLE-001 |
| FRKP-TPL    | Document Templates     | FRKP-TPL-001    |
| FRKP-RMAP   | Master Roadmap         | FRKP-RMAP-001   |

---

# 6. Knowledge Namespace

Knowledge 생산 문서는 다음 Prefix를 사용한다.

| Prefix | Layer                   | Example    |
| ------ | ----------------------- | ---------- |
| RL     | Reference Library       | RL-150     |
| KB     | Knowledge Base          | KB-251     |
| AN     | Analysis                | AN-251     |
| FC     | Formula Catalog         | FC-451     |
| MF     | Mathematical Foundation | MF-451     |
| IMP    | Implementation Guide    | IMP-451    |
| ARCH   | Architecture Guide      | ARCH-751   |
| BUNDLE | Bundle Review           | BUNDLE-005 |

---

# 7. Numbering Policy

## Governance Documents

Governance 문서는 독립적인 Namespace별 번호를 사용한다.

예시

```text
FRKP-001
FRKP-002

FRKP-DOC-001
FRKP-DOC-002

FRKP-ID-001

FRKP-RMAP-001
```

---

## Knowledge Documents

Knowledge 문서는 Bundle 기반 번호 체계를 사용한다.

예시

```text
Bundle-002

RL-120
KB-221
AN-221
FC-421
ARCH-721
```

```text
Bundle-003

RL-130
KB-231
AN-231
FC-431
ARCH-731
```

```text
Bundle-004

RL-140
KB-241
AN-241
FC-441
ARCH-741
```

```text
Bundle-005

RL-150
KB-251
AN-251
MF-451
FC-451
ARCH-751
```

---

# 8. Uniqueness Rules

다음 규칙은 반드시 준수한다.

* 하나의 Document ID는 Repository 전체에서 유일해야 한다.
* 동일한 Document ID를 두 개 이상의 문서에서 사용할 수 없다.
* 파일명 변경 없이 Document ID만 변경하는 것은 허용되지 않는다.
* Document ID와 파일명의 식별자는 항상 일치해야 한다.

예시

```text
KB-251_CREDIT_VALUATION_ADJUSTMENT.md

Document ID

KB-251
```

---

# 9. Reserved Namespaces

다음 Namespace는 예약되어 있으며 임의 생성할 수 없다.

| Namespace   | Reserved For             |
| ----------- | ------------------------ |
| FRKP        | Project Governance       |
| FRKP-DOC    | Documentation Governance |
| FRKP-ID     | Identifier Governance    |
| FRKP-ARCH   | Architecture Governance  |
| FRKP-FORM   | Formula Governance       |
| FRKP-TERM   | Terminology Governance   |
| FRKP-SYM    | Symbol Governance        |
| FRKP-ABBR   | Abbreviation Governance  |
| FRKP-BUNDLE | Bundle Governance        |
| FRKP-TPL    | Templates                |
| FRKP-RMAP   | Master Roadmap           |

---

# 10. Identifier Lifecycle

```text
Document Created
        │
        ▼
Identifier Assigned
        │
        ▼
Repository Validation
        │
        ▼
Published
        │
        ▼
Frozen
```

Document Identifier는 Repository Validation 이후 변경하지 않는다.

---

# 11. Validation Rules

Repository Freeze 이전 다음 항목을 검사한다.

* Duplicate Document IDs
* Filename ↔ Document ID 일치
* Prefix 규칙 준수
* Bundle 번호 일치
* Cross Reference의 Document ID 유효성

---

# 12. Responsibilities

| Role                  | Responsibility         |
| --------------------- | ---------------------- |
| Author                | 신규 Document ID 요청 및 적용 |
| Reviewer              | 중복 여부 검토               |
| Repository Maintainer | Repository 전체 유일성 관리   |
| Governance Owner      | Namespace 정책 관리        |

---

# 13. Cross References

| Category   | Document                            |
| ---------- | ----------------------------------- |
| Governance | [FRKP-DOC-001_DOCUMENT_STANDARD](FRKP-DOC-001_DOCUMENT_STANDARD.md)      |
| Governance | [FRKP-ARCH-001_ARCHITECTURE_STANDARD](FRKP-ARCH-001_ARCHITECTURE_STANDARD.md) |
| Governance | [FRKP-BUNDLE-001_BUNDLE_STANDARD](FRKP-BUNDLE-001_BUNDLE_STANDARD.md)     |
| Governance | [FRKP-TPL-001_DOCUMENT_TEMPLATE](../Templates/FRKP-TPL-001_DOCUMENT_TEMPLATE.md)      |
| Roadmap    | [FRKP-RMAP-001_MASTER_ROADMAP](../../Roadmap/FRKP_MASTER_ROADMAP.md)        |

---

# 14. Summary

본 표준은 FRKP Repository에서 사용하는 모든 Document Identifier의 공식 규칙을 정의한다.

Document Identifier는 Repository 전체에서 유일해야 하며, 문서의 유형과 목적을 명확히 표현해야 한다. Governance 문서는 `FRKP-*` Namespace를 사용하고, Knowledge 문서는 `RL`, `KB`, `AN`, `FC`, `MF`, `IMP`, `ARCH`, `BUNDLE` Prefix를 사용한다.

본 문서는 FRKP Repository의 **Document Identifier Authority**로서 모든 신규 문서와 Repository 검증의 기준이 된다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial release |
