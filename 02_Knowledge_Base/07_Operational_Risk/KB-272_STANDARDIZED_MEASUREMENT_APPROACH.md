# KB-272 - Standardized Measurement Approach

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | KB-272                          |
| Document Name | Standardized Measurement Approach |
| Version       | 1.0.0                           |
| Status        | Active                          |
| Category      | Knowledge Base                  |
| Parent Bundle | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Knowledge Base](../README.md) > [KB-272 - Standardized Measurement Approach](KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [KB-271](KB-271_OPERATIONAL_RISK_FRAMEWORK.md) |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-170](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-271](KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [AN-271](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [FC-471](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [MF-471](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [IMP-471](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
- [ARCH-771](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Operational Risk의 Standardized Measurement Approach(SMA)를 설명한다.

SMA는 운영리스크 자본을 기관 규모와 내부 손실 경험에 연결하여 산출하는 표준 측정 접근법이며, Bundle-007의 핵심 규제 개념을 형성한다.

---

# 2. Background

과거의 운영리스크 접근법은 수익 규모만으로 자본을 산출하거나, 복잡한 내부모형에 의존하는 경향이 있었다.

SMA는 이를 보완하기 위해 다음 두 축을 결합한다.

* Business Indicator based scale measure
* Internal loss based adjustment

이 방식은 단순성과 비교 가능성을 동시에 추구한다.

---

# 3. Objectives

SMA의 목적은 다음과 같다.

* 기관 규모를 반영한다.
* 내부 손실 경험을 반영한다.
* 기관 간 비교 가능성을 높인다.
* 계산 구조를 표준화한다.
* 구현 및 감사 추적성을 높인다.

---

# 4. High-Level Structure

```text
Business Indicator
        |
        v
Business Indicator Component (BIC)
        |
        v
Loss Component (LC)
        |
        v
Internal Loss Multiplier (ILM)
        |
        v
Operational Risk Capital
```

SMA는 기관의 사업 규모와 손실 이력을 결합하여 최종 자본을 산출한다.

---

# 5. Business Indicator

Business Indicator(BI)는 운영리스크 노출의 규모를 나타내는 규제 지표이다.

BI는 일반적으로 다음 범주로 구성된다.

| Component | Description |
| --------- | ----------- |
| Interest, Lease and Dividend Component | 금융 수익 구조를 반영 |
| Services Component | 서비스 및 수수료 기반 활동 반영 |
| Financial Component | 금융거래 및 자산 운용 반영 |

BI는 기관의 영업 규모를 표준화된 방식으로 표현한다.

---

# 6. Business Indicator Component

Business Indicator Component(BIC)는 BI를 구간별 계수로 변환한 값이다.

개념적으로는 다음과 같이 표현된다.

```text
BI
   |
   v
Piecewise Regulatory Scaling
   |
   v
BIC
```

BI가 커질수록 더 높은 marginal coefficient가 적용된다.

Basel SMA applies marginal regulatory coefficients by BI bucket. Bundle-007 represents those coefficients in the Formula Catalog as the 12%, 15%, and 18% marginal coefficient structure.

---

# 7. Loss Component

Loss Component(LC)는 내부 손실 데이터를 기반으로 산출된다.

LC는 다음 특성을 가진다.

* 최근 10년 손실 이력을 반영한다.
* 측정 가능한 운영손실 이벤트를 사용한다.
* 이상치와 데이터 품질 이슈에 대한 관리가 필요하다.

LC는 SMA가 내부 경험을 자본에 반영하는 핵심 채널이다.

---

# 8. Internal Loss Multiplier

Internal Loss Multiplier(ILM)는 손실 경험과 BIC의 상대적 크기를 반영한다.

개념적으로 다음과 같이 표현한다.

```text
LC / BIC
   |
   v
Internal Loss Multiplier
```

내부 손실이 상대적으로 크면 ILM이 증가하고, 작으면 감소한다.

The corresponding Basel formula reference is expressed in FC-471 as:

```text
ILM = ln(e - 1 + (LC / BIC)^0.8)
```

---

# 9. Regulatory Significance

SMA는 다음 이유로 중요하다.

* 자본 요구량이 손실 경험과 연결된다.
* 대규모 기관의 운영리스크를 더 잘 반영한다.
* 내부모형보다 해석 가능성이 높다.
* 규제 산출 구조가 명확하다.

---

# 10. Relationship with Other Documents

```text
RL-170
   |
   v
KB-271
   |
   v
KB-272
   |
   +-- AN-271
   +-- MF-471
   +-- FC-471
   +-- IMP-471
   +-- ARCH-771
```

본 문서는 Bundle-007의 규제 계산 원리를 정리하는 핵심 문서이다.

---

# 11. Cross References

| Category                | Document |
| ----------------------- | -------- |
| Reference               | [RL-170_OPERATIONAL_RISK_OVERVIEW](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md) |
| Knowledge               | [KB-271_OPERATIONAL_RISK_FRAMEWORK](KB-271_OPERATIONAL_RISK_FRAMEWORK.md) |
| Analysis                | [AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md) |
| Mathematical Foundation | [MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md) |
| Formula                 | [FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md) |
| Implementation Guide    | [IMP-471_OPERATIONAL_RISK_IMPLEMENTATION](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md) |
| Architecture            | [ARCH-771_OPERATIONAL_RISK_ARCHITECTURE](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md) |

---

# 12. Summary

Standardized Measurement Approach는 운영리스크 자본을 기관 규모와 내부 손실 경험을 함께 반영해 산출하는 표준 구조이다.

본 문서는 Bundle-007의 핵심 측정 접근법을 정의하며, 이후 분석, 수학적 기반, Formula, 구현 및 아키텍처 문서의 입력 개념으로 사용된다.

---

# 13. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-272 Standardized Measurement Approach | SMA, BI, BIC, LC, ILM, and capital concept chain |
| Candidate Capability | CAP-KNW-002 Evidence Registration & Mapping | Evidence-backed SMA concept mapping |
| Candidate Capability | CAP-KNW-003 Terminology Management | Canonical SMA terminology |
| Candidate Capability | CAP-KNW-005 Knowledge Layering | Knowledge Base source for formula and implementation layers |
| Candidate Evidence | EVD-000342 Standardized Measurement Approach | SMA basis |
| Candidate Evidence | EVD-000343 Business Indicator | BI basis |
| Candidate Evidence | EVD-000344 Business Indicator Component | BIC basis |
| Candidate Evidence | EVD-000345 Loss Component | LC basis |
| Candidate Evidence | EVD-000346 Internal Loss Multiplier | ILM basis |

---

# 14. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Added Basel formula references and candidate traceability references |
