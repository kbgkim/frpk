# FRKP Master Roadmap

## Document Information

| Item | Value |
|------|-------|
| Document ID | FRKP-RMAP-001 |
| Document Name | FRKP Master Roadmap |
| Version | 1.1.0 |
| Status | Active |
| Category | Project Governance |
| Created | 2026-06-26 |
| Last Updated | 2026-06-27 |

---

# Revision History

| Version | Date | Description |
|---------|------|-------------|
| 1.0.0 | 2026-06-26 | Initial Version |
| 1.1.0 | 2026-06-27 | Governance Update |

---

# Knowledge Production Strategy

FRKP는 **Bundle First (Knowledge First)** 개발 전략을 채택한다.

Governance를 먼저 구축한 후, Bundle을 중심으로 지속적으로 지식을 생산한다.

```text
Governance
      │
      ▼
Bundle Production
      │
      ▼
Bundle Review
      │
      ▼
Knowledge Growth
```

Governance는 안정화(Frozen) 상태를 유지하며, 신규 지식 생산은 Bundle 단위로 진행한다.

---

# Just-in-Time Mathematical Foundation

Mathematical Foundation(MF)은 독립적인 선행 프로젝트로 작성하지 않는다.

새로운 핵심 수학 개념이 Bundle에서 최초로 등장하는 경우에만 생성한다.

```text
Bundle

↓

Need Mathematical Foundation?

↓

YES

↓

Create MF Document

↓

Continue Bundle
```

예시

| Bundle     | Mathematical Foundation             |
| ---------- | ----------------------------------- |
| Bundle-005 | MF-451_HAZARD_RATE                  |
| Bundle-005 | MF-452_SURVIVAL_FUNCTION            |
| Bundle-005 | MF-453_DISCOUNT_FACTOR              |
| Bundle-006 | MF-461_PRINCIPAL_COMPONENT_ANALYSIS |
| Bundle-006 | MF-462_COVARIANCE_MATRIX            |
| Bundle-006 | MF-463_EIGENVALUE                   |

---

# Updated Knowledge Architecture

FRKP Knowledge Stack은 다음 계층으로 구성한다.

```text
Reference Library
        │
        ▼
Knowledge Base
        │
        ▼
Analysis
        │
        ▼
Formula Catalog
        │
        ▼
Mathematical Foundation
(Optional)
        │
        ▼
Implementation Guide
        │
        ▼
Architecture Guide
        │
        ▼
Bundle Review
```

Mathematical Foundation은 Formula와 Implementation 사이의 보조 계층(Supporting Layer)이며, 새로운 핵심 수학 개념이 등장하는 경우에만 생성한다.

---

# Updated Bundle Roadmap

## Completed

```text
Bundle-001  Basel III
Bundle-002  FRTB
Bundle-003  IFRS 9
Bundle-004  SA-CCR
```

## Current

```text
Bundle-005  Credit Valuation Adjustment (CVA)
```

## Planned

```text
Bundle-006  Market Risk Standardized Approach
Bundle-007  Operational Risk
Bundle-008  Liquidity Risk
Bundle-009  ICAAP
Bundle-010  Stress Testing
Bundle-011  Model Risk Management
Bundle-012  Climate Risk
```

---

# Bundle Development Lifecycle

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
Framework
      │
      ▼
Formula
      │
      ▼
Need Mathematical Foundation?
      │
 ┌────┴────┐
 │         │
YES        NO
 │         │
 ▼         ▼
MF-*   Continue
      │
      ▼
Implementation
      │
      ▼
Architecture
      │
      ▼
Bundle Review
      │
      ▼
Freeze
```

---

# Project Resource Allocation

| Activity               | Recommended Allocation |
| ---------------------- | ---------------------: |
| Bundle Production      |                    80% |
| Governance Improvement |                    10% |
| Dictionary Maintenance |                     5% |
| Planning / Roadmap     |                     5% |

Bundle 생산을 프로젝트의 최우선 활동으로 한다.

---

# Long-Term Vision

FRKP는 다음 네 가지를 하나의 플랫폼으로 통합하는 것을 목표로 한다.

```text
Financial Risk Handbook

+

Financial Mathematics

+

Risk Engine Architecture

+

Knowledge Platform
```

이를 통해 금융 리스크 관리 이론, 규제, 수학, 구현 및 시스템 아키텍처를 하나의 통합된 지식 체계로 제공한다.

---

# Revision History

| Version | Date       | Description                                                                                                                                                                                |
| ------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.0.0   | 2026-06-26 | Initial Master Roadmap                                                                                                                                                                     |
| 1.1.0   | 2026-06-27 | Added Knowledge Production Strategy, Just-in-Time Mathematical Foundation, Updated Knowledge Architecture, Bundle Lifecycle, Updated Bundle Roadmap, Resource Allocation, Long-Term Vision |
