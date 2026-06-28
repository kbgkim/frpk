# FC-401 — Capital Adequacy Ratio

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) > [Formula Catalog](../README.md) > [FC-401 — Capital Adequacy Ratio](FC-401_CAPITAL_ADEQUACY_RATIO.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-001](../../08_Bundles/BUNDLE-001_BASEL_III_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | [FC-402](FC-402_RISK_WEIGHTED_ASSETS.md) |

### Related Documents

- [RL-001](../../01_Reference_Library/01_Basel_III/RL-001_BASEL_III_OVERVIEW.md)
- [KB-201](../../02_Knowledge_Base/01_Basel_III/KB-201_FINANCIAL_RISK_OVERVIEW.md)
- [KB-301](../../02_Knowledge_Base/01_Basel_III/KB-301_BASEL_III_FRAMEWORK.md)
- [FC-402](FC-402_RISK_WEIGHTED_ASSETS.md)
- [ARCH-701](../../07_Architecture/01_Basel_III/ARCH-701_CAPITAL_CALCULATION_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item          | Value                  |
| ------------- | ---------------------- |
| Document ID   | FC-401                 |
| Document Name | Capital Adequacy Ratio |
| Version       | 1.0.0                  |
| Status        | Draft                  |
| Owner         | Project Lead           |
| Category      | Formula Catalog        |
| Created       | 2026-06-26             |
| Last Updated  | 2026-06-26             |

---

# 1. Purpose

본 문서는 Basel III 규제에서 사용하는 Capital Adequacy Ratio(자본적정성비율)의 정의, 계산식, 데이터 요구사항 및 시스템 구현 관점을 정리한다.

Capital Adequacy Ratio는 금융기관의 건전성을 평가하는 가장 중요한 규제 지표 중 하나이며, Basel III, NCR 및 내부 자본관리 체계의 핵심 산식이다.

---

# 2. Business Purpose

은행은 예상치 못한 손실이 발생하더라도 예금자와 금융시스템을 보호할 수 있을 만큼 충분한 자본을 보유해야 한다.

Capital Adequacy Ratio는 다음 질문에 답하기 위한 지표이다.

> **현재 보유한 자본으로 위험자산을 충분히 감당할 수 있는가?**

비율이 높을수록 손실 흡수 능력이 우수하며, 규제 최소 기준을 충족하지 못하면 감독기관의 제재 대상이 될 수 있다.

---

# 3. Regulatory Background

Basel III에서는 자본을 다음과 같이 구분한다.

| Capital Type | Description          |
| ------------ | -------------------- |
| CET1         | Common Equity Tier 1 |
| AT1          | Additional Tier 1    |
| Tier 2       | Tier 2 Capital       |

이를 기반으로 다음 세 가지 비율을 계산한다.

| Ratio               | Formula               |
| ------------------- | --------------------- |
| CET1 Ratio          | CET1 / RWA            |
| Tier 1 Ratio        | (CET1 + AT1) / RWA    |
| Total Capital Ratio | (Tier1 + Tier2) / RWA |

---

# 4. Formula Definition

가장 일반적으로 사용하는 총자본비율(Total Capital Ratio)은 다음과 같다.

$$
\text{Capital Adequacy Ratio}
=============================

\frac{\text{Eligible Regulatory Capital}}
{\text{Risk Weighted Assets}}
\times100
$$

여기서

* Eligible Regulatory Capital = CET1 + AT1 + Tier2
* Risk Weighted Assets = Credit RWA + Market RWA + Operational RWA

---

# 5. Variable Definition

| Variable        | Description                      | Unit     |
| --------------- | -------------------------------- | -------- |
| CET1            | Common Equity Tier 1 Capital     | Currency |
| AT1             | Additional Tier 1 Capital        | Currency |
| Tier2           | Tier 2 Capital                   | Currency |
| Credit RWA      | Credit Risk Weighted Assets      | Currency |
| Market RWA      | Market Risk Weighted Assets      | Currency |
| Operational RWA | Operational Risk Weighted Assets | Currency |
| Total RWA       | Sum of all RWA                   | Currency |

---

# 6. Calculation Flow

```text
Accounting Data
        │
        ▼
Regulatory Capital
(CET1 / AT1 / Tier2)
        │
        ▼
Credit RWA
Market RWA
Operational RWA
        │
        ▼
Total RWA
        │
        ▼
Capital Adequacy Ratio
```

---

# 7. Input Data Model

필수 입력 데이터는 다음과 같다.

| Field           | Description |
| --------------- | ----------- |
| CET1 Amount     | 보통주자본       |
| AT1 Amount      | 기타기본자본      |
| Tier2 Amount    | 보완자본        |
| Credit RWA      | 신용위험 RWA    |
| Market RWA      | 시장위험 RWA    |
| Operational RWA | 운영위험 RWA    |

---

# 8. Output Data Model

| Field               | Description |
| ------------------- | ----------- |
| CET1 Ratio          |             |
| Tier1 Ratio         |             |
| Total Capital Ratio |             |
| Total Capital       |             |
| Total RWA           |             |

---

# 9. Example Calculation

예를 들어 다음과 같은 데이터가 있다고 가정한다.

| Item            | Amount |
| --------------- | -----: |
| CET1            |     80 |
| AT1             |     10 |
| Tier2           |     10 |
| Credit RWA      |    600 |
| Market RWA      |    200 |
| Operational RWA |    200 |

계산 과정은 다음과 같다.

Total Capital

= 80 + 10 + 10

= 100

Total RWA

= 600 + 200 + 200

= 1,000

Capital Adequacy Ratio

= 100 / 1,000 × 100

= **10.0%**

---

# 10. Regulatory Threshold

대표적인 Basel III 최소 기준은 다음과 같다.

| Ratio               | Minimum Requirement* |
| ------------------- | -------------------: |
| CET1 Ratio          |                 4.5% |
| Tier1 Ratio         |                 6.0% |
| Total Capital Ratio |                 8.0% |

* 실제 적용 기준은 Capital Conservation Buffer, Countercyclical Buffer, G-SIB Buffer 등 국가 및 기관별 추가 규제를 반영하여 달라질 수 있다.

---

# 11. Implementation Considerations

시스템 구현 시 고려해야 할 사항은 다음과 같다.

* 자본 항목은 규제 기준에 따라 검증되어야 한다.
* RWA는 위험 유형별 계산 엔진으로부터 집계한다.
* 비율 계산 전 통화 단위를 일관되게 맞춘다.
* 0 또는 음수 RWA에 대한 예외 처리가 필요하다.
* 규제 변경에 대비하여 최소 기준은 설정(Configuration)으로 관리한다.

---

# 12. FRKP Formula Engine Model

```text
CapitalInput
      │
      ├── CET1
      ├── AT1
      ├── Tier2
      │
      ▼
CapitalCalculator
      │
      ▼
TotalCapital
      │
      ▼
RWAAggregator
      │
      ▼
CapitalAdequacyRatioCalculator
      │
      ▼
CapitalResult
```

---

# 13. Related Documents

## Reference Library

* RL-110 — Basel III Overview
* RL-120 — FRTB Overview

## Knowledge Base

* KB-201 — Financial Risk Overview
* KB-301 — Basel III Framework

## Formula Catalog

* FC-402 — Risk Weighted Assets
* FC-421 — Value at Risk
* FC-422 — Expected Shortfall

## Architecture Guide

* ARCH-701 — Capital Calculation Architecture

---

# 14. Knowledge Path

```text
RL-110 Basel III Overview
        │
        ▼
KB-301 Basel III Framework
        │
        ▼
FC-401 Capital Adequacy Ratio
        │
        ▼
FC-402 Risk Weighted Assets
        │
        ▼
ARCH-701 Capital Calculation Architecture
```

---

# 15. Summary

Capital Adequacy Ratio는 Basel III 규제 체계의 핵심 지표이며, 금융기관의 손실 흡수 능력을 정량적으로 평가한다.

FRKP에서는 이 산식을 단순 계산식이 아닌 **규제 요구사항, 데이터 모델, 계산 로직 및 시스템 구현을 연결하는 핵심 Formula Catalog**로 정의한다.

---

## Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
