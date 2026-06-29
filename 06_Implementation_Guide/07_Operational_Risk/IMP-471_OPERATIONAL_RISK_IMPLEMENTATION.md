# IMP-471 - Operational Risk Implementation Guide

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | IMP-471                         |
| Document Name | Operational Risk Implementation Guide |
| Version       | 1.0.0                           |
| Status        | Active                          |
| Category      | Implementation Guide            |
| Parent Bundle | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Implementation Guide](../README.md) > [IMP-471 - Operational Risk Implementation Guide](IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Implementation Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-170](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-271](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [KB-272](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [AN-271](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [MF-471](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [FC-471](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [ARCH-771](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Operational Risk Capital Formula를 구현하기 위한 기술 중립적 절차를 정의한다.

구현은 계산의 정확성, 추적성, 재현성을 유지하면서 데이터 수집, 손실 계산, 규제 계수 적용을 일관되게 수행해야 한다.

---

# 2. Scope

본 문서는 다음을 포함한다.

* Business Indicator calculation
* Loss data ingestion
* BIC calculation
* LC calculation
* ILM calculation
* Capital aggregation
* Audit trail generation

---

# 3. Implementation Objectives

구현 목표는 다음과 같다.

* 규제 Formula를 정확히 재현한다.
* 입력 데이터 품질을 검증한다.
* 계산 이력을 보존한다.
* 손실 데이터와 자본 결과를 연결한다.
* 기술 스택과 독립적인 계산 계약을 유지한다.

---

# 4. Processing Flow

```text
Business Data
      |
      v
Business Indicator Calculator
      |
      v
Loss Data Loader
      |
      v
Loss Component Calculator
      |
      v
Internal Loss Multiplier Calculator
      |
      v
Capital Calculator
      |
      v
Result Publisher
```

---

# 5. Logical Components

| Component | Responsibility |
| --------- | -------------- |
| Business Indicator Calculator | BI 계산 |
| Loss Data Loader | 손실 사건 데이터 수집 |
| Loss Component Calculator | LC 산출 |
| Internal Loss Multiplier Calculator | ILM 산출 |
| Capital Calculator | 최종 자본 계산 |
| Audit Trail Writer | 계산 이력 저장 |

---

# 6. Input Model

| Input | Description |
| ----- | ----------- |
| Financial statement data | BI 계산용 입력 |
| Operational loss events | 손실 사건 및 금액 |
| Observation window | 손실 관측 기간 |
| Regulatory coefficients | BIC 및 ILM 규칙 |

---

# 7. Output Model

| Output | Description |
| ------ | ----------- |
| BI | Business Indicator |
| BIC | Business Indicator Component |
| LC | Loss Component |
| ILM | Internal Loss Multiplier |
| Operational Risk Capital | 최종 자본 |
| Calculation Trace | 계산 추적 정보 |

---

# 8. Validation Strategy

검증은 다음 수준에서 수행한다.

| Level | Purpose |
| ----- | ------- |
| Input Validation | 필수 입력과 형식 확인 |
| Formula Validation | FC-471과 일치 여부 확인 |
| Data Quality Check | 손실 데이터 누락 및 이상치 확인 |
| Regression Test | 변경 영향 확인 |

---

# 9. Error Handling

| Error | Handling |
| ----- | -------- |
| Missing loss data | 정책 기반 처리 또는 오류 반환 |
| Invalid BI input | Validation error |
| Inconsistent observation period | 계산 중단 |
| Invalid regulatory coefficient | Configuration error |

---

# 10. Traceability Requirements

모든 계산은 다음 구조를 유지해야 한다.

```text
Input
   |
   v
Intermediate Result
   |
   v
Final Capital
```

감사 및 검증을 위해 중간 결과를 재현할 수 있어야 한다.

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

본 문서는 Formula Catalog를 실제 계산 절차로 연결한다.

---

# 12. Cross References

| Category                | Document |
| ----------------------- | -------- |
| Reference               | [RL-170_OPERATIONAL_RISK_OVERVIEW](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md) |
| Knowledge               | [KB-271_OPERATIONAL_RISK_FRAMEWORK](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md) |
| Knowledge               | [KB-272_STANDARDIZED_MEASUREMENT_APPROACH](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md) |
| Analysis                | [AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md) |
| Mathematical Foundation | [MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md) |
| Formula                 | [FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md) |
| Architecture            | [ARCH-771_OPERATIONAL_RISK_ARCHITECTURE](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md) |

---

# 13. Summary

Operational Risk Implementation Guide defines a deterministic and traceable procedure for turning the SMA capital formula into a reproducible calculation workflow.

The implementation remains technology neutral and focuses on data quality, validation, and auditability.

---

# 14. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-471I Operational Risk Implementation Workflow | Deterministic SMA calculation and trace workflow |
| Candidate Capability | CAP-EXE-002 Deterministic Runtime Execution | Deterministic calculation and reproducibility |
| Candidate Capability | CAP-EXE-010 Evidence-Gated Promotion | Validation and audit handoff relevance |
| Candidate Capability | CAP-KNW-002 Evidence Registration & Mapping | Calculation evidence and trace mapping |
| Candidate Evidence | EVD-000343 Business Indicator | BI implementation input basis |
| Candidate Evidence | EVD-000347 Operational Loss Data | Loss event input basis |
| Candidate Evidence | EVD-000348 Implementation Considerations | Implementation workflow basis |

---

# 15. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Added candidate traceability references |
