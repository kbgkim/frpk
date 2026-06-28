# FRKP Bundle Index

---

# Document Information

| Item          | Value              |
| ------------- | ------------------ |
| Document ID   | FRKP-PM-010        |
| Document Name | FRKP Bundle Index  |
| Version       | 1.0.0              |
| Status        | Draft              |
| Category      | Project Management |
| Created       | 2026-06-26         |
| Last Updated  | 2026-06-26         |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 전체 Bundle 구성과 진행 현황을 관리하기 위한 프로젝트 인덱스이다.

모든 Bundle의 상태, 진행률, 주요 산출물 및 의존 관계를 관리하는 공식 관리 문서로 사용한다.

---

# 2. Bundle Lifecycle

모든 Bundle은 다음 생명주기를 따른다.

```text
Planned
    │
    ▼
Draft
    │
    ▼
Review
    │
    ▼
Frozen Candidate
    │
    ▼
Frozen
    │
    ▼
Published
```

---

# 3. Bundle Dashboard

| Bundle     | Topic                         |    Phase   | Progress | Status             |
| ---------- | ----------------------------- | :--------: | :------: | ------------------ |
| Bundle-000 | Project Foundation            | Foundation |   100%   | ✅ Complete         |
| Bundle-001 | Basel III Foundation          |      1     |   100%   | ✅ Frozen Candidate |
| Bundle-002 | FRTB (Market Risk)            |      1     |   100%   | ✅ Frozen Candidate |
| Bundle-003 | IFRS 9 (Expected Credit Loss) |      1     |   100%   | ✅ Frozen Candidate |
| Bundle-004 | SA-CCR                        |      2     |   100%   | ✅ Frozen Candidate |
| Bundle-005 | CVA Risk                      |      2     |    0%    | ⏳ Planned          |
| Bundle-006 | Market Risk Standardized Approach |   2     |    0%    | ⏳ Planned          |
| Bundle-007 | Operational Risk (SMA)        |      3     |    0%    | ⏳ Planned          |
| Bundle-008 | Liquidity Risk (LCR / NSFR)   |      3     |    0%    | ⏳ Planned          |
| Bundle-009 | IRRBB                         |      3     |    0%    | ⏳ Planned          |
| Bundle-010 | ICAAP / Capital Management    |      3     |    0%    | ⏳ Planned          |
| Bundle-011 | Stress Testing                |      3     |    0%    | ⏳ Planned          |
| Bundle-012 | XVA Framework                 |      4     |    0%    | ⏳ Planned          |
| Bundle-013 | Financial Instruments         |      4     |    0%    | ⏳ Planned          |
| Bundle-014 | Fixed Income Analytics        |      4     |    0%    | ⏳ Planned          |
| Bundle-015 | Portfolio Risk                |      4     |    0%    | ⏳ Planned          |
| Bundle-016 | Derivatives Pricing           |      4     |    0%    | ⏳ Planned          |
| Bundle-017 | Mathematical Foundation       |      5     |    0%    | ⏳ Planned          |
| Bundle-018 | Statistics & Risk Modeling    |      5     |    0%    | ⏳ Planned          |
| Bundle-019 | AI for Financial Risk         |      5     |    0%    | ⏳ Planned          |

---

# 4. Phase Overview

## Foundation

* Bundle-000

---

## Phase 1 — Regulatory Foundation

* Bundle-001
* Bundle-002
* Bundle-003

---

## Phase 2 — Credit Risk Expansion

* Bundle-004
* Bundle-005
* Bundle-006

---

## Phase 3 — Banking Risk Management

* Bundle-007
* Bundle-008
* Bundle-009
* Bundle-010
* Bundle-011

---

## Phase 4 — Quantitative Finance

* Bundle-012
* Bundle-013
* Bundle-014
* Bundle-015
* Bundle-016

---

## Phase 5 — Mathematical & AI Foundation

* Bundle-017
* Bundle-018
* Bundle-019

---

# 5. Bundle Dependency Map

```text
Foundation
      │
      ▼
Bundle-001
Basel III
      │
 ┌────┴───────────────┐
 ▼                    ▼
Bundle-002        Bundle-003
FRTB              IFRS 9
 │                    │
 ├─────────────┐      │
 ▼             ▼      ▼
Bundle-004   Bundle-006
SA-CCR       Market Risk SA
 │
 ▼
Bundle-005
CVA
```

---

# 6. Bundle Composition Standard

모든 Bundle은 동일한 핵심 계층 구조를 따른다.

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

Bundle 종료 시에는 반드시 Bundle Review 문서를 작성한다.

---

# 7. Bundle Status Summary

| Status           | Count |
| ---------------- | ----: |
| Complete         |     1 |
| Frozen Candidate |     3 |
| Planned          |    16 |

---

# 8. Progress Metrics

| Metric                | Value |
| --------------------- | ----: |
| Total Planned Bundles |    20 |
| Completed Bundles     |     4 |
| Planned Bundles       |    16 |
| Overall Progress      |   20% |

---

# 9. Completed Bundles

## Bundle-000

Project Foundation

주요 산출물

* Project Bootstrap
* Project Charter
* Metadata Standard
* Project Index
* Roadmap
* Backlog

---

## Bundle-001

Basel III Foundation

핵심 내용

* Basel III 개요
* Regulatory Capital
* Risk Weighted Assets
* Capital Calculation Architecture

---

## Bundle-002

FRTB

핵심 내용

* Market Risk
* Expected Shortfall
* Liquidity Horizon
* SBM
* Delta
* Vega
* Curvature

---

## Bundle-003

IFRS 9

핵심 내용

* Credit Risk
* Stage
* PD
* LGD
* EAD
* Expected Credit Loss
* IFRS 9 Architecture

---

# 10. Next Bundle

다음 진행 대상

## Bundle-004

**SA-CCR**

주요 내용

* Counterparty Credit Risk
* Replacement Cost
* Potential Future Exposure
* Alpha
* EAD (SA-CCR)
* Netting
* Collateral
* Margin

---

# 11. Long-term Vision

```text
Financial Risk Knowledge Platform

          │
          ▼

Regulation

Market Risk

Credit Risk

Liquidity Risk

Operational Risk

Mathematics

AI

Architecture

Knowledge Base

Reference Library

Implementation Guide
```

FRKP는 단순한 문서 저장소가 아니라 금융 리스크 관리 이론, 규제, 수학, 시스템 설계를 통합하는 종합 지식 플랫폼을 목표로 한다.

---

# 12. Maintenance Rules

본 문서는 다음 경우 반드시 갱신한다.

* 새로운 Bundle 생성
* Bundle 상태 변경
* Bundle 완료
* Bundle Frozen
* 신규 Phase 추가

모든 변경은 Revision History에 기록한다.

---

# 13. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-26 | Initial Version |
