# FRKP-001 — Project Charter

---

## Document Information

| Item | Value |
|------|-------|
| Document ID | FRKP-001 |
| Document Name | Project Charter |
| Version | 1.0.0 |
| Status | Draft |
| Owner | Project Lead |
| Parent Document | FRKP-000 |
| Created | 2026-06-26 |
| Last Updated | 2026-06-26 |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 공식 프로젝트 운영 헌장(Project Charter)이다.

FRKP-000(Project Bootstrap)에서 정의한 프로젝트의 비전과 목표를 실현하기 위한 운영 원칙과 프로젝트 관리 기준을 정의한다.

본 문서는 프로젝트 운영에 관한 기준만을 다루며, 프로젝트의 비전과 범위는 FRKP-000을 따른다.

---

# 2. Governance

FRKP는 Project Management 기반으로 운영한다.

모든 작업은 다음 계층으로 관리한다.

```text
Project
    ├── Epic
    │     ├── Feature
    │     │      ├── Sprint
    │     │      │      ├── Task
    │     │      │      └── Deliverable
```

각 Deliverable은 독립적인 산출물이며, 고유한 문서 번호와 버전을 가진다.

---

# 3. Roles and Responsibilities

## Project Lead

프로젝트의 최종 의사결정 권한을 가진다.

주요 역할은 다음과 같다.

- 프로젝트 방향 결정
- 우선순위 결정
- Deliverable 승인
- 품질 검토
- 프로젝트 종료 승인

---

## AI Assistant

프로젝트의 기술 문서 작성과 설계를 지원한다.

주요 역할은 다음과 같다.

- 문서 작성
- Knowledge Base 구축
- Formula Catalog 작성
- Architecture 설계
- 문서 검토
- 상호 참조 관리

---

## OpenCode

프로젝트 저장소를 관리한다.

주요 역할은 다음과 같다.

- Markdown 파일 생성
- Git 관리
- 프로젝트 구조 유지
- 자동화 지원
- 문서 저장

---

# 4. Document Lifecycle

모든 문서는 동일한 생명주기를 따른다.

```text
Draft
    ↓
Review
    ↓
Approved
    ↓
Frozen
```

각 상태의 의미는 다음과 같다.

| Status | Description |
|---------|-------------|
| Draft | 최초 작성 상태 |
| Review | 검토 및 수정 진행 |
| Approved | 공식 승인 완료 |
| Frozen | 기준 문서로 확정 |

Frozen 문서는 직접 수정하지 않으며, 변경이 필요한 경우 새로운 버전으로 관리한다.

---

# 5. Document Management Principles

모든 문서는 다음 원칙을 따른다.

- 하나의 문서는 하나의 주제만 다룬다.
- 상위 문서의 내용을 반복하지 않는다.
- 관련 문서를 적극 참조한다.
- Markdown을 원본(Source of Truth)으로 사용한다.
- 문서는 항상 최신 상태를 유지한다.

---

# 6. Version Management

모든 문서는 Semantic Versioning을 적용한다.

| Version | Description |
|----------|-------------|
| Major | 구조 또는 범위 변경 |
| Minor | 내용 추가 |
| Patch | 오탈자 및 경미한 수정 |

예시

- 1.0.0
- 1.1.0
- 1.1.1

---

# 7. Quality Policy

모든 Deliverable은 다음 기준을 만족해야 한다.

- 목적이 명확하다.
- 내용이 정확하다.
- 문서 구조가 일관된다.
- 중복 설명이 없다.
- 관련 문서와 연결된다.
- Markdown 문법 오류가 없다.

---

# 8. Change Management

문서 변경은 다음 절차를 따른다.

```text
Change Request
        ↓
Impact Review
        ↓
Document Update
        ↓
Review
        ↓
Approval
```

모든 변경은 Revision History에 기록한다.

---

# 9. Definition of Done

문서는 다음 조건을 만족하면 완료된 것으로 간주한다.

- 초안 작성 완료
- 자체 검토 완료
- 저장소 반영
- Revision History 작성
- 다음 문서와 연결 관계 확인

Approved와 Frozen은 프로젝트 진행 상황에 따라 결정한다.

---

# 10. Working Rules

프로젝트는 다음 원칙을 따른다.

- 실무 중심으로 작성한다.
- Knowledge First 원칙을 따른다.
- 중복 문서를 만들지 않는다.
- 기존 문서를 지속적으로 개선한다.
- 프로젝트는 지속적으로 발전한다.

---

# 11. Communication Rules

모든 공식 산출물은 Markdown으로 관리한다.

문서를 작성할 때는 항상 다음 정보를 함께 제공한다.

- 저장 디렉토리
- 파일명
- 버전
- 상태

이를 통해 프로젝트 저장소와 문서를 항상 동일한 상태로 유지한다.

---

# 12. Next Steps

Project Charter 승인 후 다음 문서를 작성한다.

1. FRKP-002 — Document Metadata Standard
2. FRKP-003 — Project Index
3. FRKP-004 — Roadmap
4. FRKP-005 — Backlog
5. FRKP-006 — Current Work

Foundation 단계가 완료되면 Knowledge Base 구축을 시작한다.

---

## Revision History

| Version | Date | Description |
|---------|------|-------------|
| 1.0.0 | 2026-06-26 | Initial Draft |