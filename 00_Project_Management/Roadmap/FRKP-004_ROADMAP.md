# FRKP-004 — Roadmap

---

## Document Information

| Item            | Value        |
| --------------- | ------------ |
| Document ID     | FRKP-004     |
| Document Name   | Roadmap      |
| Version         | 1.0.0        |
| Status          | Draft        |
| Owner           | Project Lead |
| Parent Document | FRKP-001     |
| Created         | 2026-06-26   |
| Last Updated    | 2026-06-26   |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 전체 개발 로드맵을 정의한다.

로드맵은 프로젝트의 단계별 목표와 주요 산출물을 제시하며, 프로젝트 진행의 기준으로 활용한다.

---

# 2. Roadmap Principles

FRKP는 다음 원칙에 따라 단계적으로 구축한다.

* Foundation를 먼저 구축한다.
* Knowledge를 우선 축적한다.
* Formula를 표준화한다.
* Volume은 Knowledge를 기반으로 작성한다.
* Architecture는 실제 구현 가능한 수준까지 작성한다.

각 단계는 이전 단계의 산출물을 기반으로 진행한다.

---

# 3. Overall Roadmap

```text
Foundation
      │
      ▼
Reference Library
      │
      ▼
Knowledge Base
      │
      ▼
Formula Catalog
      │
      ▼
Glossary
      │
      ▼
Volumes
      │
      ▼
Architecture Guide
      │
      ▼
Publication
```

---

# 4. Phase 1 — Foundation

## Objective

프로젝트 운영 기반 구축

## Deliverables

* Project Bootstrap
* Project Charter
* Document Metadata Standard
* Project Index
* Roadmap
* Backlog
* Current Work

## Completion Criteria

* 프로젝트 운영 체계 확립
* 문서 표준 확정
* 프로젝트 구조 확정

---

# 5. Phase 2 — Reference Library

## Objective

공식 참고 자료를 체계적으로 정리한다.

## Deliverables

* Basel III
* FRTB
* IFRS 9
* NCR
* Market Risk
* OpenEyes
* Internal Reference

## Completion Criteria

* 모든 참고 문서 분류 완료
* 참조 기준 확립

---

# 6. Phase 3 — Knowledge Base

## Objective

금융 리스크 핵심 지식을 체계적으로 구축한다.

## 주요 분야

* Financial Market
* Financial Instruments
* Market Risk
* Credit Risk
* Liquidity Risk
* Operational Risk
* Regulatory Capital
* Portfolio Theory
* Fixed Income
* Derivatives

## Completion Criteria

* 핵심 Knowledge Base 작성 완료
* 상호 참조 구조 확립

---

# 7. Phase 4 — Formula Catalog

## Objective

금융 수식을 표준화한다.

## 주요 분야

* Financial Mathematics
* Statistics
* Probability
* Linear Algebra
* Optimization
* Portfolio Theory
* Pricing
* Risk Measures
* Basel Formula

## Completion Criteria

* Formula Catalog 구축 완료
* Knowledge Base와 연결 완료

---

# 8. Phase 5 — Glossary

## Objective

프로젝트 전체 용어를 표준화한다.

## 주요 분야

* Financial Terms
* Risk Terms
* Regulatory Terms
* Mathematical Terms
* Technical Terms

## Completion Criteria

* 용어 표준 확립
* 문서 간 용어 일관성 확보

---

# 9. Phase 6 — Volumes

## Objective

Knowledge Base를 기반으로 Handbook을 집필한다.

## Planned Volumes

* Volume 1 — Financial Market & Instruments
* Volume 2 — Risk Measurement
* Volume 3 — Regulatory Capital
* Volume 4 — Risk Engine Architecture

## Completion Criteria

* 모든 Volume 초안 작성
* 교차 검토 완료

---

# 10. Phase 7 — Architecture Guide

## Objective

Risk Engine 구현을 위한 기술 가이드를 작성한다.

## 주요 분야

* Formula Engine
* Risk Engine
* Java Architecture
* Database Design
* Data Flow
* Integration Guide

## Completion Criteria

* 구현 가능한 수준의 Architecture Guide 완성

---

# 11. Phase 8 — Publication

## Objective

프로젝트 결과물을 배포 가능한 형태로 정리한다.

## Deliverables

* Markdown Repository
* PDF Handbook
* DOCX Handbook
* Reference Index

## Completion Criteria

* Release Version 발행
* 문서 품질 검토 완료

---

# 12. Milestones

| Milestone | Description             |
| --------- | ----------------------- |
| M1        | Foundation 완료           |
| M2        | Reference Library 정리 완료 |
| M3        | Knowledge Base 구축 완료    |
| M4        | Formula Catalog 구축 완료   |
| M5        | Glossary 구축 완료          |
| M6        | Volume 초안 완료            |
| M7        | Architecture Guide 완료   |
| M8        | Version 1.0 Release     |

---

# 13. Current Position

현재 프로젝트는 다음 단계에 위치한다.

```text
Foundation
    │
    ├── Bootstrap          ✔
    ├── Charter            ✔
    ├── Metadata           ✔
    ├── Project Index      ✔
    ├── Roadmap            ◀ Current
    ├── Backlog
    └── Current Work
```

---

# 14. Next Steps

Roadmap 완료 후 다음 문서를 작성한다.

1. FRKP-005 — Backlog
2. FRKP-006 — Current Work

Foundation 완료 후 Phase 2(Reference Library)와 Phase 3(Knowledge Base)를 병행하여 진행한다.

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
