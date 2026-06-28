# RL-160 — Market Risk Standardized Approach Overview

---

# Document Information

| Item          | Value                                      |
| ------------- | ------------------------------------------ |
| Document ID   | RL-160                                     |
| Document Name | Market Risk Standardized Approach Overview |
| Version       | 1.0.0                                      |
| Status        | Active                                     |
| Category      | Reference Library                          |
| Parent Bundle | [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)                                 |
| Domain        | Market Risk                                |
| Created       | 2026-06-27                                 |
| Last Updated  | 2026-06-27                                 |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) > [Reference Library](../README.md) > [RL-160 — Market Risk Standardized Approach Overview](RL-160_MARKET_RISK_STANDARDIZED_APPROACH_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md) |
| ⬆ Parent Layer | [Reference Library](../README.md) |
| ➡ Next | None |

### Related Documents

- [KB-261](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-261_MARKET_RISK_STANDARDIZED_APPROACH.md)
- [KB-262](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-262_SENSITIVITY_BASED_METHOD.md)
- [KB-263](../../02_Knowledge_Base/06_Market_Risk_Standardized_Approach/KB-263_RISK_FACTOR_CATEGORIES.md)
- [AN-261](../../03_Analysis/06_Market_Risk_Standardized_Approach/AN-261_WHY_FRTB_REPLACED_VAR.md)
- [MF-461](../../05_Mathematical_Foundation/06_Market_Risk_Standardized_Approach/MF-461_COVARIANCE_MATRIX.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III Fundamental Review of the Trading Book(FRTB)의 **Market Risk Standardized Approach(SA)** 에 대한 개요를 제공한다.

Market Risk Standardized Approach는 Trading Book에서 발생하는 시장위험을 규제자본으로 산출하기 위한 표준 접근법(Standardized Capital Framework)이며, 본 문서는 이후 Knowledge Base, Analysis, Mathematical Foundation, Formula Catalog, Implementation Guide 및 Architecture Guide의 상위 Reference 문서로 사용된다.

---

# 2. Background

2008년 글로벌 금융위기 이후 Basel Committee는 기존 Basel 2.5 시장위험 체계의 한계를 보완하기 위해 FRTB(Fundamental Review of the Trading Book)를 도입하였다.

기존 규제의 주요 한계는 다음과 같다.

* VaR 중심 위험측정의 한계
* Trading Book과 Banking Book 간 경계의 모호성
* 유동성 위험 반영 부족
* Tail Risk 반영 부족
* 위험요인 간 상관관계 왜곡

FRTB는 이러한 문제를 해결하기 위해 Trading Book 규제를 전면 개편하였다.

---

# 3. Objectives

Market Risk Standardized Approach의 목적은 다음과 같다.

* 시장위험의 일관된 규제자본 산출
* 위험 민감도(Risk Sensitivity) 기반 평가
* Trading Book 위험의 표준화
* 금융기관 간 비교 가능성 확보
* 내부모형 접근법(IMA)의 대체 및 기준 제공

---

# 4. Scope

본 문서는 다음 내용을 포함한다.

* Trading Book
* Market Risk
* Sensitivity-based Method (SBM)
* Delta Risk
* Vega Risk
* Curvature Risk
* Default Risk Charge (DRC)
* Residual Risk Add-on (RRAO)
* Capital Aggregation

다음 내용은 별도 문서에서 상세히 다룬다.

* Internal Models Approach (IMA)
* Expected Shortfall
* P&L Attribution Test
* Backtesting
* Modellability Assessment

---

# 5. Position within Basel III

```text
Basel III
      │
      ▼
Market Risk
      │
      ▼
Fundamental Review of the Trading Book (FRTB)
      │
      ├── Standardized Approach (SA)
      │
      └── Internal Models Approach (IMA)
```

본 Bundle은 Standardized Approach(SA)를 중심으로 구성한다.

---

# 6. High-Level Framework

Market Risk Standardized Approach는 크게 다섯 개의 구성요소로 이루어진다.

```text
Trading Book
        │
        ▼
Sensitivity-based Method
        │
        ├── Delta
        ├── Vega
        └── Curvature
        │
        ▼
Default Risk Charge
        │
        ▼
Residual Risk Add-on
        │
        ▼
Capital Aggregation
```

---

# 7. Core Concepts

## Trading Book

단기 매매 목적 또는 헤지 목적의 금융상품 포트폴리오.

## Risk Sensitivity

시장 변수 변화에 대한 금융상품 가치의 민감도.

## Capital Requirement

시장위험을 흡수하기 위해 보유해야 하는 최소 규제자본.

## Risk Factor

금리, 환율, 주가, 신용스프레드, 상품가격 등 시장가격을 변화시키는 요인.

---

# 8. Major Risk Classes

Market Risk Standardized Approach는 다음 Risk Class를 대상으로 한다.

| Risk Class            | Description |
| --------------------- | ----------- |
| Interest Rate Risk    | 금리 위험       |
| Credit Spread Risk    | 신용스프레드 위험   |
| Equity Risk           | 주식 위험       |
| Foreign Exchange Risk | 환율 위험       |
| Commodity Risk        | 상품 위험       |

---

# 9. Relationship with Other Bundles

```text
Bundle-001
Basel III
        │
        ▼
Bundle-002
FRTB
        │
        ▼
Bundle-006
Market Risk Standardized Approach
```

또한 Bundle-006은 향후 다음 Bundle과도 연계된다.

* Bundle-009 (ICAAP)
* Bundle-010 (Stress Testing)
* Bundle-011 (Model Risk Management)

---

# 10. Relationship with FRKP

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
Mathematical Foundation
        │
        ▼
Formula Catalog
        │
        ▼
Implementation Guide
        │
        ▼
Architecture Guide
```

본 문서는 [Bundle-006](../../08_Bundles/BUNDLE-006_MARKET_RISK_STANDARDIZED_APPROACH_REVIEW.md)의 최상위 Reference 문서이다.

---

# 11. Bundle-006 Deliverables

예정 산출물은 다음과 같다.

| Layer  | Planned Document                                  |
| ------ | ------------------------------------------------- |
| RL     | RL-160 Market Risk Standardized Approach Overview |
| KB     | KB-261 Market Risk Standardized Approach          |
| KB     | KB-262 Sensitivity-based Method                   |
| KB     | KB-263 Risk Factor Categories                     |
| AN     | AN-261 Why FRTB Replaced VaR                      |
| AN     | AN-262 Delta, Vega and Curvature                  |
| MF     | MF-461 Covariance Matrix                          |
| MF     | MF-462 Principal Component Analysis               |
| MF     | MF-463 Eigenvalue and Eigenvector                 |
| FC     | FC-461 Delta Capital Formula                      |
| FC     | FC-462 Vega Capital Formula                       |
| FC     | FC-463 Curvature Capital Formula                  |
| FC     | FC-464 Capital Aggregation                        |
| IMP    | IMP-461 FRTB-SA Implementation                    |
| ARCH   | ARCH-761 Market Risk SA Architecture              |
| REVIEW | BUNDLE-006 Market Risk SA Review                  |

---

# 12. References

본 문서는 다음 자료를 기반으로 한다.

* Basel III Framework
* FRTB Standards
* Basel Committee Publications
* Supervisory Guidelines

---

# 13. Summary

Market Risk Standardized Approach는 Basel III FRTB의 핵심 규제체계로서, Trading Book의 시장위험을 민감도 기반(Sensitivity-based Method)으로 측정하고 규제자본을 산출하기 위한 표준 접근법이다.

본 문서는 Bundle-006의 최상위 Reference Library 문서이며, 이후 Knowledge Base, Mathematical Foundation, Formula Catalog, Implementation Guide 및 Architecture Guide의 공통 기반을 제공한다.

---

# 14. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
