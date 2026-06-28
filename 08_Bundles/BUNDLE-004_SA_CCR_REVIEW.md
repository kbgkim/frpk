# BUNDLE-004 — SA-CCR Bundle Review

---

# Document Information

| Item            | Value                                                       |
| --------------- | ----------------------------------------------------------- |
| Bundle ID       | BUNDLE-004                                                  |
| Bundle Name     | Standardised Approach for Counterparty Credit Risk (SA-CCR) |
| Version         | 1.0.0                                                       |
| Status          | Completed                                                   |
| Category        | Bundle Review                                               |
| Parent Standard | [FRKP-BUNDLE-001](../00_Project_Management/Governance/Standards/FRKP-BUNDLE-001_BUNDLE_STANDARD.md)                                             |
| Created         | 2026-06-26                                                  |
| Last Updated    | 2026-06-26                                                  |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../README.md) > [Home](../README.md) > [Bundle-004](BUNDLE-004_SA_CCR_REVIEW.md) > [Bundle Review](README.md) > [BUNDLE-004 — SA-CCR Bundle Review](BUNDLE-004_SA_CCR_REVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-004](BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Bundle Review](README.md) |
| ➡ Next | None |

### Related Documents

- [RL-140](../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
- [KB-242](../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)
- [AN-241](../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)
- [FC-441](../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)의 **Bundle-004 (SA-CCR)** 에 대한 완료 검토(Closure Review) 문서이다.

본 Review는 Bundle의 완결성, 추적성, 거버넌스 준수 여부 및 다음 Bundle로의 인계 가능성을 평가한다.

---

# 2. Bundle Objective

Bundle-004의 목적은 Basel III SA-CCR(Standardised Approach for Counterparty Credit Risk)를 FRKP의 표준 문서 구조에 따라 체계적으로 정리하는 것이다.

구성 범위는 다음과 같다.

* SA-CCR 개요
* 거래상대방 신용위험
* CEM의 한계 분석
* SA-CCR Framework
* RC / PFE / Alpha / EAD Formula
* Implementation Guide
* Architecture Guide

---

# 3. Deliverables

## Reference

| Document               | Status |
| ---------------------- | ------ |
| RL-140_SA_CCR_OVERVIEW | ✅      |

---

## Knowledge

| Document                        | Status |
| ------------------------------- | ------ |
| KB-241_COUNTERPARTY_CREDIT_RISK | ✅      |
| KB-242_SA_CCR_FRAMEWORK         | ✅      |

---

## Analysis

| Document              | Status |
| --------------------- | ------ |
| AN-241_WHY_CEM_FAILED | ✅      |

---

## Formula

| Document                         | Status |
| -------------------------------- | ------ |
| FC-441_REPLACEMENT_COST          | ✅      |
| FC-442_POTENTIAL_FUTURE_EXPOSURE | ✅      |
| FC-443_ALPHA                     | ✅      |
| FC-444_SA_CCR_EAD                | ✅      |

---

## Implementation

| Document                      | Status |
| ----------------------------- | ------ |
| IMP-441_SA_CCR_IMPLEMENTATION | ✅      |

---

## Architecture

| Document                     | Status |
| ---------------------------- | ------ |
| ARCH-741_SA_CCR_ARCHITECTURE | ✅      |

---

# 4. Coverage Assessment

| Area                  | Coverage |
| --------------------- | -------- |
| Regulatory Background | Complete |
| Business Concepts     | Complete |
| Framework             | Complete |
| Formula Definition    | Complete |
| Processing Pipeline   | Complete |
| Architecture          | Complete |
| Traceability          | Complete |

Bundle 목표 범위를 모두 충족하였다.

---

# 5. Traceability Matrix

```text
RL-140
    │
    ▼
KB-241
    │
    ▼
KB-242
    │
    ▼
AN-241
    │
    ▼
FC-441
    │
    ▼
FC-442
    │
    ▼
FC-443
    │
    ▼
FC-444
    │
    ▼
IMP-441
    │
    ▼
ARCH-741
```

Reference부터 Architecture까지 단절 없이 연결된다.

---

# 6. Formula Coverage

Bundle에서 정의한 Formula는 다음과 같다.

| Formula                   | Status   |
| ------------------------- | -------- |
| Replacement Cost          | Complete |
| Potential Future Exposure | Complete |
| Alpha                     | Complete |
| Exposure at Default       | Complete |

Formula Coverage는 100%이다.

---

# 7. Architecture Assessment

Architecture Review 결과

| Item                      | Result |
| ------------------------- | ------ |
| Layer Separation          | PASS   |
| Responsibility Separation | PASS   |
| Dependency Rules          | PASS   |
| Stateless Calculation     | PASS   |
| Traceability              | PASS   |
| Technology Neutrality     | PASS   |

Architecture Standard를 충족한다.

---

# 8. Governance Compliance

Bundle는 다음 Governance Standard를 준수한다.

| Standard        | Result |
| --------------- | ------ |
| FRKP-DOC-001    | PASS   |
| FRKP-TERM-001   | PASS   |
| FRKP-ABBR-001   | PASS   |
| FRKP-SYM-001    | PASS   |
| FRKP-FORM-001   | PASS   |
| FRKP-IMP-001    | PASS   |
| FRKP-ARCH-001   | PASS   |
| FRKP-BUNDLE-001 | PASS   |

Governance Compliance는 100%이다.

---

# 9. Quality Gate Review

| Gate                     | Result |
| ------------------------ | ------ |
| Document Structure       | PASS   |
| Metadata                 | PASS   |
| Cross Reference          | PASS   |
| Formula Consistency      | PASS   |
| Architecture Consistency | PASS   |
| Bundle Completeness      | PASS   |

모든 품질 게이트를 통과하였다.

---

# 10. Lessons Learned

Bundle-004를 통해 다음 원칙이 확립되었다.

* Formula는 계산 계약(What)을 정의한다.
* Implementation은 처리 절차(How)를 정의한다.
* Architecture는 시스템 구조(Where)를 정의한다.
* Governance는 프로젝트 전반의 일관성을 유지한다.
* Dictionary는 의미 체계의 단일 기준(Single Source of Truth)을 제공한다.

이 원칙은 이후 Bundle에도 동일하게 적용한다.

---

# 11. Bundle Dependency

```text
Bundle-001
      │
      ▼
Bundle-002
      │
      ▼
Bundle-003
      │
      ▼
Bundle-004
      │
      ▼
Bundle-005 (CVA)
```

Bundle-004는 Bundle-005의 선행 작업이다.

---

# 12. Remaining Work

현재 Bundle-004에서 남아 있는 필수 산출물은 없다.

향후 개선 가능 항목

* 규제 개정 반영
* 예제 포트폴리오 추가
* 계산 사례(Worked Example) 확장
* 도메인 Glossary 연계 강화

이 항목들은 유지보수 대상이며 Bundle 완료에는 영향을 주지 않는다.

---

# 13. Bundle Completion Decision

| Evaluation Item         | Result |
| ----------------------- | ------ |
| Deliverables Complete   | YES    |
| Governance Compliance   | YES    |
| Traceability            | YES    |
| Architecture Complete   | YES    |
| Formula Complete        | YES    |
| Implementation Complete | YES    |

### Final Verdict

**BUNDLE-004 : COMPLETE**

Bundle-004는 FRKP Bundle Standard의 완료 기준을 모두 충족하였다.

본 Bundle은 **Frozen** 상태로 전환할 수 있으며, 이후 규제 변경 또는 승인된 개선 요청이 없는 한 구조적 변경은 수행하지 않는다.

---

# 14. Next Bundle

다음 작업은

```text
Bundle-005

Credit Valuation Adjustment (CVA)
```

이다.

예상 구성

```text
RL-150
KB-251
AN-251
KB-252

FC-451
FC-452
FC-453
FC-454

IMP-451

ARCH-751

BUNDLE-005
```

---

# 15. Summary

Bundle-004는 Basel III SA-CCR를 대상으로 하는 FRKP의 네 번째 Bundle로서, Reference Library부터 Architecture Guide까지의 전체 문서 체계를 완성하였다.

본 Bundle은 Formula, Implementation 및 Architecture의 역할을 명확히 분리하고, Governance Standard를 준수하는 구조를 확립하였다. 또한 상위 Bundle과의 추적성을 유지하면서 Bundle-005(CVA)로 자연스럽게 확장 가능한 기반을 마련하였다.

---

# 16. Revision History

| Version | Date       | Description           |
| ------- | ---------- | --------------------- |
| 1.0.0   | 2026-06-26 | Initial Bundle Review |
