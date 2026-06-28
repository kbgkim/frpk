# FRKP-005 — Backlog

---

## Document Information

| Item            | Value        |
| --------------- | ------------ |
| Document ID     | FRKP-005     |
| Document Name   | Backlog      |
| Version         | 1.0.0        |
| Status          | Draft        |
| Owner           | Project Lead |
| Parent Document | FRKP-001     |
| Created         | 2026-06-26   |
| Last Updated    | 2026-06-26   |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 전체 작업 목록(Backlog)을 관리한다.

Backlog는 프로젝트에서 수행해야 할 모든 작업을 Epic, Feature, Deliverable 단위로 관리하며, 프로젝트 진행에 따라 지속적으로 갱신한다.

---

# 2. Backlog Management Rules

Backlog는 다음 원칙에 따라 관리한다.

* Epic 단위로 작업을 구분한다.
* Feature는 Epic을 구성하는 기능 또는 문서 그룹이다.
* Deliverable은 실제 작성하거나 구현하는 산출물이다.
* 완료된 항목은 삭제하지 않고 상태(Status)를 변경한다.
* 새로운 작업은 해당 Epic에 추가한다.

---

# 3. Status Definition

| Status      | Description |
| ----------- | ----------- |
| Planned     | 계획됨         |
| In Progress | 진행 중        |
| Review      | 검토 중        |
| Completed   | 완료          |
| Deferred    | 보류          |
| Cancelled   | 취소          |

---

# 4. Epic Overview

| Epic  | Name               | Status      |
| ----- | ------------------ | ----------- |
| EP-01 | Foundation         | In Progress |
| EP-02 | Reference Library  | Planned     |
| EP-03 | Knowledge Base     | Planned     |
| EP-04 | Formula Catalog    | Planned     |
| EP-05 | Glossary           | Planned     |
| EP-06 | Volumes            | Planned     |
| EP-07 | Architecture Guide | Planned     |
| EP-08 | Publication        | Planned     |

---

# 5. EP-01 — Foundation

## Objective

프로젝트 운영 기반 구축

| Deliverable | Description                | Status      |
| ----------- | -------------------------- | ----------- |
| FRKP-000    | Project Bootstrap          | Completed   |
| FRKP-001    | Project Charter            | Completed   |
| FRKP-002    | Document Metadata Standard | Completed   |
| FRKP-003    | Project Index              | Completed   |
| FRKP-004    | Roadmap                    | Completed   |
| FRKP-005    | Backlog                    | In Progress |
| FRKP-006    | Current Work               | Planned     |

---

# 6. EP-02 — Reference Library

## Objective

공식 참고 자료를 프로젝트 표준으로 정리한다.

| Deliverable | Description         | Status  |
| ----------- | ------------------- | ------- |
| RL-001      | Basel III           | Planned |
| RL-002      | FRTB                | Planned |
| RL-003      | IFRS 9              | Planned |
| RL-004      | Market Risk         | Planned |
| RL-005      | NCR                 | Planned |
| RL-006      | OpenEyes            | Planned |
| RL-007      | Internal References | Planned |

---

# 7. EP-03 — Knowledge Base

## Objective

금융 리스크 핵심 지식을 구축한다.

| Deliverable | Description             | Status  |
| ----------- | ----------------------- | ------- |
| KB-001      | Financial Risk Overview | Planned |
| KB-002      | Financial Markets       | Planned |
| KB-003      | Financial Instruments   | Planned |
| KB-004      | Market Risk             | Planned |
| KB-005      | Credit Risk             | Planned |
| KB-006      | Liquidity Risk          | Planned |
| KB-007      | Operational Risk        | Planned |
| KB-008      | Regulatory Capital      | Planned |

---

# 8. EP-04 — Formula Catalog

## Objective

금융 수식을 표준화한다.

| Deliverable | Description        | Status  |
| ----------- | ------------------ | ------- |
| FC-001      | Present Value      | Planned |
| FC-002      | Future Value       | Planned |
| FC-003      | Discount Factor    | Planned |
| FC-004      | Duration           | Planned |
| FC-005      | Convexity          | Planned |
| FC-006      | Portfolio Return   | Planned |
| FC-007      | Portfolio Variance | Planned |
| FC-008      | Value at Risk      | Planned |

---

# 9. EP-05 — Glossary

## Objective

프로젝트 용어를 표준화한다.

| Deliverable | Description        | Status  |
| ----------- | ------------------ | ------- |
| GL-001      | Financial Terms    | Planned |
| GL-002      | Risk Terms         | Planned |
| GL-003      | Mathematical Terms | Planned |
| GL-004      | Regulatory Terms   | Planned |
| GL-005      | Technical Terms    | Planned |

---

# 10. EP-06 — Volumes

## Objective

Knowledge Base를 기반으로 핸드북을 집필한다.

| Deliverable | Description                               | Status  |
| ----------- | ----------------------------------------- | ------- |
| VOL-001     | Volume 1 - Financial Market & Instruments | Planned |
| VOL-002     | Volume 2 - Risk Measurement               | Planned |
| VOL-003     | Volume 3 - Regulatory Capital             | Planned |
| VOL-004     | Volume 4 - Risk Engine Architecture       | Planned |

---

# 11. EP-07 — Architecture Guide

## Objective

Risk Engine 구현 가이드를 작성한다.

| Deliverable | Description                 | Status  |
| ----------- | --------------------------- | ------- |
| ARCH-001    | Formula Engine Architecture | Planned |
| ARCH-002    | Risk Engine Architecture    | Planned |
| ARCH-003    | Data Model Guide            | Planned |
| ARCH-004    | Java Implementation Guide   | Planned |
| ARCH-005    | Database Design Guide       | Planned |

---

# 12. EP-08 — Publication

## Objective

프로젝트 결과물을 출판 가능한 형태로 정리한다.

| Deliverable | Description         | Status  |
| ----------- | ------------------- | ------- |
| PUB-001     | Markdown Repository | Planned |
| PUB-002     | PDF Edition         | Planned |
| PUB-003     | DOCX Edition        | Planned |
| PUB-004     | Version 1.0 Release | Planned |

---

# 13. Current Priority

현재 우선순위는 다음과 같다.

| Priority | Deliverable                      |
| -------- | -------------------------------- |
| P1       | FRKP-006 — Current Work          |
| P2       | RL-001 — Basel III               |
| P3       | RL-002 — FRTB                    |
| P4       | KB-001 — Financial Risk Overview |

---

# 14. Maintenance

Backlog는 프로젝트 진행 상황에 따라 지속적으로 갱신한다.

다음 경우 반드시 수정한다.

* 신규 Deliverable 추가
* 작업 완료
* 우선순위 변경
* Epic 추가 또는 변경

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
