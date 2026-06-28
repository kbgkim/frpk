# BUNDLE-001 — Basel III Bundle Review

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../README.md) > [Home](../README.md) > [Bundle-001](BUNDLE-001_BASEL_III_REVIEW.md) > [Bundle Review](README.md) > [BUNDLE-001 — Basel III Bundle Review](BUNDLE-001_BASEL_III_REVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-001](BUNDLE-001_BASEL_III_REVIEW.md) |
| ⬆ Parent Layer | [Bundle Review](README.md) |
| ➡ Next | None |

### Related Documents

- [RL-001](../01_Reference_Library/01_Basel_III/RL-001_BASEL_III_OVERVIEW.md)
- [KB-201](../02_Knowledge_Base/01_Basel_III/KB-201_FINANCIAL_RISK_OVERVIEW.md)
- [KB-301](../02_Knowledge_Base/01_Basel_III/KB-301_BASEL_III_FRAMEWORK.md)
- [FC-401](../04_Formula_Catalog/01_Basel_III/FC-401_CAPITAL_ADEQUACY_RATIO.md)
- [FC-402](../04_Formula_Catalog/01_Basel_III/FC-402_RISK_WEIGHTED_ASSETS.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item         | Value        |
| ------------ | ------------ |
| Bundle ID    | BUNDLE-001   |
| Bundle Name  | Basel III    |
| Version      | 1.0.0        |
| Status       | Review       |
| Owner        | Project Lead |
| Created      | 2026-06-26   |
| Last Updated | 2026-06-26   |

---

# 1. Purpose

본 문서는 Basel III Bundle의 완성도와 품질을 검토하고, 다음 Bundle(FRTB)으로 진행하기 전에 누락 사항과 개선 사항을 확인하기 위한 공식 Review 문서이다.

Bundle Review는 프로젝트의 품질 게이트(Quality Gate) 역할을 수행하며, Bundle의 Freeze 여부를 결정하는 기준으로 사용한다.

---

# 2. Bundle Scope

본 Bundle의 목표는 Basel III 규제자본 체계의 전체 구조를 이해하고, 규제자본 계산을 위한 지식과 산식 및 시스템 아키텍처를 연결하는 것이다.

### 포함 문서

| Document | Name                             | Status    |
| -------- | -------------------------------- | --------- |
| RL-110   | Basel III Overview               | Completed |
| KB-201   | Financial Risk Overview          | Completed |
| KB-301   | Basel III Framework              | Completed |
| FC-401   | Capital Adequacy Ratio           | Completed |
| FC-402   | Risk Weighted Assets             | Completed |
| ARCH-701 | Capital Calculation Architecture | Completed |

---

# 3. Coverage Assessment

| Area              | Coverage | Result |
| ----------------- | -------- | ------ |
| Basel III 목적      | Complete | ✅      |
| Three Pillars     | Complete | ✅      |
| Capital Structure | Complete | ✅      |
| RWA 개념            | Complete | ✅      |
| Capital Ratio     | Complete | ✅      |
| 계산 흐름             | Complete | ✅      |
| 시스템 아키텍처          | Complete | ✅      |
| FRKP 연결 구조        | Complete | ✅      |

---

# 4. Document Relationship Review

```text
RL-110
Basel III Overview
        │
        ▼
KB-201
Financial Risk Overview
        │
        ▼
KB-301
Basel III Framework
        │
        ▼
FC-401
Capital Adequacy Ratio
        │
        ▼
FC-402
Risk Weighted Assets
        │
        ▼
ARCH-701
Capital Calculation Architecture
```

문서 간 의존성과 학습 순서는 일관되게 유지되고 있으며, 중복 설명은 최소화되어 있다.

---

# 5. Quality Assessment

## Consistency

* 문서 번호 체계 일관성 유지
* 용어 사용 일관성 유지
* 계층 구조 일관성 유지

**Result:** PASS

---

## Completeness

Basel III를 이해하기 위한 핵심 내용은 모두 포함되었다.

다만 세부 규제(FRTB, SA-CCR, CVA 등)는 별도 Bundle에서 상세히 다룬다.

**Result:** PASS

---

## Traceability

Reference → Knowledge → Formula → Architecture로의 추적이 가능하다.

**Result:** PASS

---

## Implementation Readiness

아키텍처와 Formula Engine의 연결 구조가 정의되었으며, Risk Engine 구현을 위한 기반이 마련되었다.

**Result:** PASS

---

# 6. Gap Analysis

현재 Bundle에서 의도적으로 제외한 항목은 다음과 같다.

| Topic          | Planned Bundle |
| -------------- | -------------- |
| FRTB           | Bundle-002     |
| IFRS 9         | Bundle-003     |
| SA-CCR         | Bundle-004     |
| CVA            | Bundle-005     |
| Liquidity Risk | Bundle-006     |
| Stress Testing | Bundle-007     |

이는 Bundle 간 책임을 명확히 하기 위한 설계 결정이다.

---

# 7. Lessons Learned

이번 Bundle을 통해 다음과 같은 원칙을 확정하였다.

1. 규제(Reference)와 시스템 구현(Architecture)을 직접 연결한다.
2. Formula는 독립적인 계산 단위로 관리한다.
3. Risk Engine은 Formula Engine을 조합하여 업무 계산을 수행한다.
4. RWA는 모든 규제자본 계산의 중심 개념이다.
5. Bundle 단위 작성이 문서 간 일관성을 높인다.

---

# 8. Improvement Opportunities

다음 Bundle부터는 다음 계층을 추가 적용한다.

## Analysis

규제와 수식 사이의 비교·해석 문서

예시

* Why VaR Failed
* Basel II vs Basel III
* Delta vs Gamma vs Vega

---

## Implementation

실제 시스템 구현 문서

예시

* Java Object Model
* Pseudo Code
* Runtime Flow
* Test Strategy

---

# 9. Bundle Metrics

| Metric                 | Value |
| ---------------------- | ----: |
| Reference Documents    |     1 |
| Knowledge Documents    |     2 |
| Formula Documents      |     2 |
| Architecture Documents |     1 |
| Total Documents        |     6 |

---

# 10. Exit Criteria

Bundle 종료 기준

| Item            | Result |
| --------------- | ------ |
| Reference 완료    | ✅      |
| Knowledge 완료    | ✅      |
| Formula 완료      | ✅      |
| Architecture 완료 | ✅      |
| Review 완료       | ✅      |

모든 종료 조건을 충족하였다.

---

# 11. Bundle Verdict

**Verdict: GO**

Basel III Bundle은 다음 Bundle(FRTB)을 진행하기 위한 기반으로 충분한 수준이다.

본 Bundle는 **Frozen Candidate**로 지정한다.

Frozen 전환은 향후 Bundle 간 교차 검토 이후 수행한다.

---

# 12. Next Bundle

다음 Bundle은 Market Risk(FRTB)이다.

### Bundle-002

| Order | Document                                     |
| ----- | -------------------------------------------- |
| 1     | RL-120_FRTB_OVERVIEW.md                      |
| 2     | KB-221_MARKET_RISK_OVERVIEW.md               |
| 3     | AN-221_WHY_VAR_FAILED.md                     |
| 4     | KB-222_FRTB_FRAMEWORK.md                     |
| 5     | FC-421_EXPECTED_SHORTFALL.md                 |
| 6     | IMP-421_EXPECTED_SHORTFALL_IMPLEMENTATION.md |
| 7     | ARCH-721_FRTB_CALCULATION_ARCHITECTURE.md    |
| 8     | BUNDLE-002_FRTB_REVIEW.md                    |

---

# 13. Revision History

| Version | Date       | Description           |
| ------- | ---------- | --------------------- |
| 1.0.0   | 2026-06-26 | Initial Bundle Review |
