# FC-471 - Operational Risk Capital Formula

---

# Document Information

| Item            | Value                           |
| --------------- | ------------------------------- |
| Document ID     | FC-471                          |
| Document Name   | Operational Risk Capital Formula |
| Version         | 1.0.0                           |
| Status          | Active                          |
| Category        | Formula Catalog                 |
| Parent Bundle   | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain          | Operational Risk                |
| Created         | 2026-06-28                      |
| Last Updated    | 2026-06-29                      |
| Formula Standard | FRKP-FORM-001                   |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Formula Catalog](../README.md) > [FC-471 - Operational Risk Capital Formula](FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Formula Catalog](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-170](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-271](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [KB-272](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [AN-271](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [MF-471](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [ARCH-771](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
- [IMP-471](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Operational Risk Capital Formula를 정의한다.

본 Formula는 Standardized Measurement Approach(SMA)를 기반으로 운영리스크 규제자본을 계산하는 계산 계약이며, 구현 기술과 독립적으로 정의된다.

---

# 2. Formula Overview

Operational Risk Capital은 다음 구조로 표현한다.

```text
Operational Risk Capital = BIC * ILM
```

| Symbol | Meaning |
| ------ | ------- |
| BIC    | Business Indicator Component |
| ILM    | Internal Loss Multiplier |

This is the Basel SMA capital relationship used by Bundle-007.

---

# 3. Business Indicator Component

Business Indicator Component(BIC)는 BI의 구간별 규제 계수를 적용한 값이다.

Basel SMA 표현은 다음과 같다.

```text
BIC = f(BI)
```

BI가 커질수록 점증하는 marginal coefficient가 적용된다.

규제 구간은 다음과 같이 이해할 수 있다.

| BI Range | Regulatory Coefficient |
| -------- | ---------------------- |
| Lower range | 12% |
| Middle range | 15% |
| Upper range | 18% |

---

# 4. Internal Loss Multiplier

Internal Loss Multiplier(ILM)는 내부 손실과 BIC의 상대적 크기를 반영한다.

Basel SMA 표현은 다음과 같다.

```text
ILM = ln(e - 1 + (LC / BIC)^0.8)
```

| Symbol | Description |
| ------ | ----------- |
| LC     | Loss Component |
| BIC    | Business Indicator Component |

LC는 내부 손실 경험을 요약한 값이며, BIC와의 비율이 자본에 영향을 준다.

The expression assumes BIC is positive. BIC zero or low-value edge cases are implementation and validation concerns handled by IMP-471 input validation and error handling.

---

# 5. Loss Component

Loss Component(LC)는 내부 손실 데이터의 장기 평균을 반영한다.

개념적으로는 다음과 같이 볼 수 있다.

```text
Historical Loss Data
        |
        v
Loss Component
```

LC는 손실의 빈도와 심각도를 간접적으로 반영하는 입력값이다.

---

# 6. Computation Sequence

```text
Collect Business Indicator
        |
        v
Calculate BIC
        |
        v
Collect Loss Data
        |
        v
Calculate LC
        |
        v
Calculate ILM
        |
        v
Operational Risk Capital
```

계산은 결정론적이어야 하며, 동일 입력에 대해 동일 출력을 생성해야 한다.

---

# 7. Input Contract

| Input | Required | Description |
| ----- | :------: | ----------- |
| Business Indicator data | ✔ | 기관 규모 및 활동 측정값 |
| Internal loss data | ✔ | 운영리스크 손실 이력 |
| Regulatory coefficients | ✔ | 구간별 계수와 보정 규칙 |
| Loss observation window | ✔ | 손실 관측 기간 |

---

# 8. Output Contract

| Output | Description |
| ------ | ----------- |
| BIC | 규모 기반 자본 컴포넌트 |
| ILM | 손실 기반 조정계수 |
| Operational Risk Capital | 최종 운영리스크 자본 |

---

# 9. Formula Interpretation

Formula는 다음 의미를 가진다.

* 규모가 큰 기관은 더 큰 기본 자본을 가진다.
* 손실 경험이 큰 기관은 추가 조정이 발생한다.
* 자본은 규모와 손실 경험을 함께 반영한다.

이 구조는 운영리스크가 단순 평균 손실이 아니라, 기관의 운영 복잡성과 통제 수준을 함께 반영해야 함을 나타낸다.

---

# 10. Relationship with Mathematical Foundation

```text
MF-471
Operational Risk Loss Distribution
        |
        v
FC-471
Operational Risk Capital Formula
```

손실 분포의 이해는 LC와 ILM의 해석에 필요하다.

---

# 11. Relationship with FRKP

```text
Reference
      |
      v
Knowledge
      |
      v
Analysis
      |
      v
Mathematical Foundation
      |
      v
Formula
      |
      v
Implementation
      |
      v
Architecture
```

본 문서는 Bundle-007 Formula Catalog의 핵심 계산 계약이다.

---

# 12. Non-functional Requirements

본 Formula는 다음 특성을 만족해야 한다.

* Deterministic
* Traceable
* Reproducible
* Technology Neutral
* Immutable Definition
* Testable

---

# 13. Cross References

| Category                | Document |
| ----------------------- | -------- |
| Reference               | [RL-170_OPERATIONAL_RISK_OVERVIEW](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md) |
| Knowledge               | [KB-271_OPERATIONAL_RISK_FRAMEWORK](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md) |
| Knowledge               | [KB-272_STANDARDIZED_MEASUREMENT_APPROACH](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md) |
| Analysis                | [AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md) |
| Mathematical Foundation | [MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md) |
| Implementation          | [IMP-471_OPERATIONAL_RISK_IMPLEMENTATION](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md) |
| Architecture            | [ARCH-771_OPERATIONAL_RISK_ARCHITECTURE](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md) |

---

# 14. Summary

Operational Risk Capital Formula converts business scale and loss experience into a deterministic regulatory capital requirement.

The formula is intentionally technology neutral and serves as the input contract for implementation and architecture documents within Bundle-007.

---

# 15. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-471F Operational Risk Capital Formula | BIC, LC, ILM, and capital formula contract |
| Candidate Capability | CAP-EXE-003 Formula Governance Workflow | Formula lifecycle and validation relevance |
| Candidate Capability | CAP-EXE-014 Numeric Precision Governance | Numeric treatment and reproducibility expectations |
| Candidate Capability | CAP-KNW-002 Evidence Registration & Mapping | Evidence-backed formula references |
| Candidate Evidence | EVD-000342 Standardized Measurement Approach | SMA formula basis |
| Candidate Evidence | EVD-000343 Business Indicator | BI input basis |
| Candidate Evidence | EVD-000344 Business Indicator Component | BIC formula basis |
| Candidate Evidence | EVD-000345 Loss Component | LC formula basis |
| Candidate Evidence | EVD-000346 Internal Loss Multiplier | ILM formula basis |

---

# 16. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Improved Basel formula presentation and added candidate traceability references |
