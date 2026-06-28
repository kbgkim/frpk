# BUNDLE-002 — FRTB Bundle Review

---

# Document Information

| Item         | Value                                         |
| ------------ | --------------------------------------------- |
| Bundle ID    | BUNDLE-002                                    |
| Bundle Name  | Fundamental Review of the Trading Book (FRTB) |
| Version      | 1.0.0                                         |
| Status       | Review                                        |
| Category     | Bundle Review                                 |
| Created      | 2026-06-26                                    |
| Last Updated | 2026-06-26                                    |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../README.md) > [Home](../README.md) > [Bundle-002](BUNDLE-002_FRTB_REVIEW.md) > [Bundle Review](README.md) > [BUNDLE-002 — FRTB Bundle Review](BUNDLE-002_FRTB_REVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-002](BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Bundle Review](README.md) |
| ➡ Next | None |

### Related Documents

- [RL-120](../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [AN-221](../03_Analysis/02_FRTB/AN-221_WHY_VAR_FAILED.md)
- [FC-421](../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 FRTB(Bundle-002)의 완성도와 품질을 평가하기 위한 공식 Review 문서이다.

Bundle Review는 FRKP의 품질 게이트(Quality Gate)로서 다음 사항을 검증한다.

* 문서 완성도
* 계층 간 일관성
* 문서 추적성(Traceability)
* 설계 일관성
* Formula와 Architecture의 연결성
* Bundle Freeze 준비 상태

---

# 2. Bundle Scope

본 Bundle은 Basel III 시장위험 규제(FRTB)의 핵심 구조를 설명한다.

범위는 다음과 같다.

* Market Risk
* Trading Book
* Expected Shortfall
* Liquidity Horizon
* Sensitivity-Based Method
* Delta
* Vega
* Curvature
* Risk Engine Architecture

다음 항목은 포함하지 않는다.

* Default Risk Charge (DRC)
* Residual Risk Add-On (RRAO)
* Internal Models Approval
* P&L Attribution
* RFET
* Non-Modellable Risk Factor (NMRF)

이 항목들은 후속 Bundle에서 상세히 다룬다.

---

# 3. Document Inventory

## Reference

| ID     | Document      | Status   |
| ------ | ------------- | -------- |
| RL-120 | FRTB Overview | Complete |

---

## Knowledge

| ID     | Document             | Status   |
| ------ | -------------------- | -------- |
| KB-221 | Market Risk Overview | Complete |
| KB-222 | FRTB Framework       | Complete |

---

## Analysis

| ID     | Document       | Status   |
| ------ | -------------- | -------- |
| AN-221 | Why VaR Failed | Complete |

---

## Formula

| ID     | Document                 | Status   |
| ------ | ------------------------ | -------- |
| FC-421 | Expected Shortfall       | Complete |
| FC-422 | Liquidity Horizon        | Complete |
| FC-423 | Sensitivity-Based Method | Complete |
| FC-424 | Delta Risk Charge        | Complete |
| FC-425 | Vega Risk Charge         | Complete |
| FC-426 | Curvature Risk Charge    | Complete |

---

## Implementation

| ID      | Document                          | Status   |
| ------- | --------------------------------- | -------- |
| IMP-421 | Expected Shortfall Implementation | Complete |

---

## Architecture

| ID       | Document                      | Status   |
| -------- | ----------------------------- | -------- |
| ARCH-721 | FRTB Calculation Architecture | Complete |

---

# 4. Coverage Assessment

| Area               | Coverage | Result |
| ------------------ | -------- | ------ |
| Market Risk        | Complete | ✅      |
| Trading Book       | Complete | ✅      |
| Expected Shortfall | Complete | ✅      |
| Liquidity Horizon  | Complete | ✅      |
| SBM                | Complete | ✅      |
| Delta              | Complete | ✅      |
| Vega               | Complete | ✅      |
| Curvature          | Complete | ✅      |
| Implementation     | Complete | ✅      |
| Architecture       | Complete | ✅      |

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

모든 문서는 상위 계층을 참조하며 하위 계층의 기반이 된다.

---

# 6. Traceability Review

```text
RL-120
      │
      ▼
KB-221
      │
      ▼
KB-222
      │
      ▼
AN-221
      │
      ▼
FC-421
      │
      ▼
FC-422
      │
      ▼
FC-423
      │
 ┌────┼─────┐
 ▼    ▼     ▼
424  425   426
      │
      ▼
IMP-421
      │
      ▼
ARCH-721
```

각 문서는 상위 문서와 명확한 참조 관계를 가진다.

---

# 7. Formula Review

Formula Catalog는 다음 계약을 일관되게 적용하였다.

* Input Contract
* Computation Contract
* Output Contract

또한 Formula Engine과 Risk Engine의 책임을 명확히 분리하였다.

평가 결과

**PASS**

---

# 8. Implementation Review

Implementation Layer는 다음 원칙을 따른다.

* Stateless Calculator
* Immutable Value Object
* Validation First
* Pipeline Processing
* Parallel Processing Ready

평가 결과

**PASS**

---

# 9. Architecture Review

Architecture Layer는 다음 책임을 정의하였다.

* Formula Engine
* Implementation Layer
* Risk Engine
* Application Layer

계산과 오케스트레이션의 책임이 명확히 분리되었다.

평가 결과

**PASS**

---

# 10. Consistency Review

검토 결과

* 문서 번호 일관성 유지
* Bundle 구조 일관성 유지
* 계층 구조 일관성 유지
* Formula 문서 템플릿 통일
* Implementation 문서 구조 통일

평가 결과

**PASS**

---

# 11. Design Decisions

Bundle-002에서 확정된 설계 원칙

## AD-001

Risk Factor 중심 설계

---

## AD-002

Formula와 Implementation 분리

---

## AD-003

Implementation과 Architecture 분리

---

## AD-004

Configuration 기반 규제 파라미터 관리

---

## AD-005

Immutable Contract 사용

---

## AD-006

Parallel-friendly 구조 채택

---

## AD-007

Formula Catalog는 Calculation Contract를 정의한다.

---

## AD-008

Implementation Guide는 Execution Contract를 정의한다.

---

## AD-009

Architecture Guide는 Orchestration Contract를 정의한다.

---

# 12. Lessons Learned

이번 Bundle에서 얻은 가장 중요한 교훈은 다음과 같다.

FRTB는 단순한 규제가 아니라

**Risk Factor 기반 계산 프레임워크**이다.

또한 Formula와 Implementation을 분리하면

* 유지보수성
* 재사용성
* 테스트 용이성

이 크게 향상된다.

---

# 13. Future Improvements

향후 추가 예정

## Formula

* FC-427 Bucket Aggregation
* FC-428 Risk Weight
* FC-429 Correlation Matrix

---

## Implementation

* IMP-422 Delta Calculator
* IMP-423 Vega Calculator
* IMP-424 Curvature Calculator

---

## Architecture

* Distributed Risk Engine
* GPU Processing
* Incremental Calculation

---

# 14. Bundle Metrics

| Metric         | Count |
| -------------- | ----: |
| Reference      |     1 |
| Knowledge      |     2 |
| Analysis       |     1 |
| Formula        |     6 |
| Implementation |     1 |
| Architecture   |     1 |

총 문서 수

**12 Documents**

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

Bundle-002는 FRKP에서 정의한 품질 기준을 충족하였다.

Reference부터 Architecture까지의 계층이 완성되었으며 문서 간 추적성과 일관성이 확보되었다.

본 Bundle은 **Frozen Candidate**로 지정한다.

최종 Frozen 전환은 상위 Bundle과의 교차 검토 이후 수행한다.

---

# 17. Next Bundle

다음 Bundle

**Bundle-003 — IFRS 9 Expected Credit Loss**

예정 문서

```text
RL-130  IFRS 9 Overview

KB-231  Credit Risk Overview

KB-232  IFRS 9 Framework

AN-231  Why Incurred Loss Failed

FC-431  Probability of Default

FC-432  Loss Given Default

FC-433  Exposure at Default

FC-434  Expected Credit Loss

IMP-431 Expected Credit Loss Implementation

ARCH-731 IFRS9 Calculation Architecture

BUNDLE-003_IFRS9_REVIEW
```

---

# 18. Revision History

| Version | Date       | Description    |
| ------- | ---------- | -------------- |
| 1.0.0   | 2026-06-26 | Initial Review |
