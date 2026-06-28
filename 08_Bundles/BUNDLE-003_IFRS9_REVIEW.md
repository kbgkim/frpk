# BUNDLE-003 — IFRS 9 Review

---

# Document Information

| Item         | Value                                 |
| ------------ | ------------------------------------- |
| Bundle ID    | BUNDLE-003                            |
| Bundle Name  | IFRS 9 Expected Credit Loss Framework |
| Version      | 1.0.0                                 |
| Status       | Review                                |
| Category     | Bundle Review                         |
| Created      | 2026-06-26                            |
| Last Updated | 2026-06-26                            |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../README.md) > [Home](../README.md) > [Bundle-003](BUNDLE-003_IFRS9_REVIEW.md) > [Bundle Review](README.md) > [BUNDLE-003 — IFRS 9 Review](BUNDLE-003_IFRS9_REVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-003](BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Bundle Review](README.md) |
| ➡ Next | None |

### Related Documents

- [RL-130](../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
- [KB-232](../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)
- [AN-231](../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)
- [FC-431](../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Bundle-003 (IFRS 9 Expected Credit Loss Framework)** 의 완성도와 품질을 검증하기 위한 공식 Review 문서이다.

Bundle Review는 FRKP의 품질 게이트(Quality Gate)로서 다음 사항을 검증한다.

* 문서 완성도
* 계층 간 일관성
* 문서 추적성(Traceability)
* Formula와 Implementation의 연결성
* Implementation과 Architecture의 연결성
* Bundle Freeze 준비 상태

---

# 2. Bundle Scope

본 Bundle은 IFRS 9 손상(Impairment) 프레임워크를 중심으로 구성된다.

포함 범위는 다음과 같다.

* Credit Risk
* IFRS 9
* Stage Assessment
* Probability of Default (PD)
* Loss Given Default (LGD)
* Exposure at Default (EAD)
* Expected Credit Loss (ECL)
* Discounting
* Forward-looking Information
* Multiple Scenario
* Provision Calculation Architecture

다음 항목은 본 Bundle의 범위에 포함하지 않는다.

* Classification & Measurement
* Hedge Accounting
* Internal Rating Model Development
* PD/LGD/EAD 모델 학습
* Accounting Journal Posting
* Capital Adequacy Calculation

이 항목들은 별도 Bundle에서 다룬다.

---

# 3. Document Inventory

## Reference

| ID     | Document        | Status   |
| ------ | --------------- | -------- |
| RL-130 | IFRS 9 Overview | Complete |

---

## Knowledge

| ID     | Document             | Status   |
| ------ | -------------------- | -------- |
| KB-231 | Credit Risk Overview | Complete |
| KB-232 | IFRS 9 Framework     | Complete |

---

## Analysis

| ID     | Document                 | Status   |
| ------ | ------------------------ | -------- |
| AN-231 | Why Incurred Loss Failed | Complete |

---

## Formula

| ID     | Document               | Status   |
| ------ | ---------------------- | -------- |
| FC-431 | Probability of Default | Complete |
| FC-432 | Loss Given Default     | Complete |
| FC-433 | Exposure at Default    | Complete |
| FC-434 | Expected Credit Loss   | Complete |

---

## Implementation

| ID      | Document                            | Status   |
| ------- | ----------------------------------- | -------- |
| IMP-431 | Expected Credit Loss Implementation | Complete |

---

## Architecture

| ID       | Document                        | Status   |
| -------- | ------------------------------- | -------- |
| ARCH-731 | IFRS 9 Calculation Architecture | Complete |

---

# 4. Coverage Assessment

| Area                 | Coverage | Result |
| -------------------- | -------- | ------ |
| IFRS 9 Overview      | Complete | ✅      |
| Credit Risk          | Complete | ✅      |
| Stage Classification | Complete | ✅      |
| PD                   | Complete | ✅      |
| LGD                  | Complete | ✅      |
| EAD                  | Complete | ✅      |
| Expected Credit Loss | Complete | ✅      |
| Discounting          | Complete | ✅      |
| Scenario Processing  | Complete | ✅      |
| Architecture         | Complete | ✅      |

---

# 5. Bundle Architecture

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

모든 문서는 상위 계층의 지식을 기반으로 하며 하위 계층의 구현 기준을 제공한다.

---

# 6. Traceability Review

```text
RL-130
      │
      ▼
KB-231
      │
      ▼
AN-231
      │
      ▼
KB-232
      │
      ▼
FC-431
      │
      ▼
FC-432
      │
      ▼
FC-433
      │
      ▼
FC-434
      │
      ▼
IMP-431
      │
      ▼
ARCH-731
```

Reference부터 Architecture까지의 문서 추적성이 확보되었다.

---

# 7. Formula Review

Formula Catalog는 다음 원칙을 일관되게 적용하였다.

* Calculation Contract 중심
* Input / Computation / Output Contract 정의
* Formula와 Implementation의 책임 분리
* Stage 기반 계산 모델
* Discount 및 Scenario 반영

평가 결과

**PASS**

---

# 8. Implementation Review

Implementation Layer는 다음 원칙을 준수하였다.

* Stateless Calculator
* Immutable Value Object
* Pipeline Processing
* Validation First
* Parallel Processing Ready

평가 결과

**PASS**

---

# 9. Architecture Review

Architecture Layer는 다음 책임을 명확히 구분하였다.

* Formula Engine
* Implementation Layer
* Credit Risk Engine
* Accounting Layer
* Application Layer

계산과 실행, 오케스트레이션, 회계 처리가 명확히 분리되었다.

평가 결과

**PASS**

---

# 10. Consistency Review

검토 결과

* 문서 번호 체계 일관성 유지
* Bundle 구조 일관성 유지
* Formula Catalog 형식 통일
* Implementation Guide 형식 통일
* Architecture Guide 형식 통일

평가 결과

**PASS**

---

# 11. Design Decisions

Bundle-003에서 확정된 설계 원칙

## AD-001

Expected Credit Loss를 중심으로 손상 모델을 구성한다.

---

## AD-002

Stage 분류와 ECL 계산을 분리한다.

---

## AD-003

PD, LGD, EAD는 독립적인 계산 계약으로 정의한다.

---

## AD-004

Formula, Implementation, Architecture의 책임을 분리한다.

---

## AD-005

Forward-looking Information을 반영한다.

---

## AD-006

Multiple Scenario를 기본 지원 구조로 설계한다.

---

## AD-007

Discounting을 ECL 계산의 필수 요소로 정의한다.

---

## AD-008

Immutable Contract 기반의 데이터 흐름을 유지한다.

---

# 12. Lessons Learned

IFRS 9는 단순한 회계 기준이 아니라 **신용위험 관리 프레임워크**이다.

가장 중요한 변화는 다음과 같다.

* 손실 발생 후 인식(Incurred Loss)
* ↓
* 미래 손실 예측(Expected Credit Loss)

즉, 위험을 사후 기록하는 것이 아니라 **미래 위험을 현재 시점에서 측정**하는 방식으로 전환되었다.

---

# 13. Future Improvements

향후 확장 예정

## Formula

* FC-435 Significant Increase in Credit Risk (SICR)
* FC-436 Discount Factor
* FC-437 Probability-weighted Scenario

---

## Implementation

* IMP-432 Stage Classification Engine
* IMP-433 Scenario Processing Engine

---

## Architecture

* Real-time ECL Processing
* Climate Risk Integration
* Distributed Credit Risk Engine

---

# 14. Bundle Metrics

| Metric         | Count |
| -------------- | ----: |
| Reference      |     1 |
| Knowledge      |     2 |
| Analysis       |     1 |
| Formula        |     4 |
| Implementation |     1 |
| Architecture   |     1 |

**총 문서 수: 10**

---

# 15. Quality Gate

| Check                   | Result |
| ----------------------- | ------ |
| Reference Complete      | ✅      |
| Knowledge Complete      | ✅      |
| Analysis Complete       | ✅      |
| Formula Complete        | ✅      |
| Implementation Complete | ✅      |
| Architecture Complete   | ✅      |
| Traceability            | ✅      |
| Consistency             | ✅      |

---

# 16. Bundle Verdict

## Overall Result

**GO**

Bundle-003은 FRKP에서 정의한 품질 기준을 충족하였다.

Reference부터 Architecture까지 모든 계층이 완성되었으며 문서 간 추적성과 책임 분리가 확보되었다.

본 Bundle은 **Frozen Candidate**로 지정한다.

최종 Frozen 전환은 전체 Credit Risk 영역과의 교차 검토 이후 수행한다.

---

# 17. Relationship with Other Bundles

```text
Bundle-001
Basel III Overview
        │
        ▼
Bundle-002
FRTB
        │
        ▼
Bundle-003
IFRS 9
        │
        ├──────────────┐
        ▼              ▼
SA-CCR             Credit Risk IRB
        │              │
        ▼              ▼
CVA          Regulatory Capital
```

Bundle-003은 Credit Risk 영역의 중심 Bundle이며, 이후 SA-CCR, IRB, CVA 및 Basel III 규제자본 계산과 직접 연결된다.

---

# 18. Next Bundle

다음 권장 Bundle

**Bundle-004 — SA-CCR (Counterparty Credit Risk)**

예정 문서

```text
RL-140  SA-CCR Overview

KB-241 Counterparty Credit Risk

KB-242 SA-CCR Framework

AN-241 Why CEM Failed

FC-441 Replacement Cost

FC-442 Potential Future Exposure

FC-443 Alpha

FC-444 Exposure at Default (SA-CCR)

IMP-441 SA-CCR Implementation

ARCH-741 SA-CCR Architecture

BUNDLE-004_SA_CCR_REVIEW
```

---

# 19. Revision History

| Version | Date       | Description    |
| ------- | ---------- | -------------- |
| 1.0.0   | 2026-06-26 | Initial Review |
