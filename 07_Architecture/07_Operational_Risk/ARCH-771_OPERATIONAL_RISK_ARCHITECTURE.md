# ARCH-771 - Operational Risk Architecture

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | ARCH-771                        |
| Document Name | Operational Risk Architecture   |
| Version       | 1.0.0                           |
| Status        | Active                          |
| Category      | Architecture Guide              |
| Parent Bundle | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Architecture Guide](../README.md) > [ARCH-771 - Operational Risk Architecture](ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Architecture Guide](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-170](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-271](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [KB-272](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [AN-271](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [MF-471](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [FC-471](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [IMP-471](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Operational Risk 자본 계산을 지원하는 시스템 아키텍처를 정의한다.

아키텍처는 데이터 수집, 손실 관리, 규제 계산, 결과 추적을 하나의 일관된 처리 흐름으로 연결해야 한다.

---

# 2. Scope

본 문서는 다음 기능을 포함한다.

* Business Indicator data flow
* Loss event ingestion
* Capital calculation pipeline
* Audit trail and traceability
* Reporting output

---

# 3. Architectural Principles

본 아키텍처는 다음 원칙을 따른다.

1. Layered processing
2. Separation of concerns
3. Deterministic calculation
4. Traceability
5. Technology neutrality
6. Reusability
7. Governance alignment

---

# 4. Logical Architecture

```text
Business Data
      |
      v
BI Engine
      |
      v
Loss Event Engine
      |
      v
Loss Component Engine
      |
      v
ILM Engine
      |
      v
Capital Engine
      |
      v
Reporting and Audit
```

각 컴포넌트는 단일 책임을 가지며 상호 의존을 최소화한다.

---

# 5. Component Responsibilities

| Component | Responsibility |
| --------- | -------------- |
| BI Engine | Business Indicator 계산 |
| Loss Event Engine | 운영손실 사건 수집 및 정규화 |
| Loss Component Engine | LC 산출 |
| ILM Engine | 내부 손실 조정계수 산출 |
| Capital Engine | 최종 자본 계산 |
| Reporting and Audit | 결과 제공 및 추적 정보 저장 |

---

# 6. Data Flow

```text
Source Data
      |
      v
Normalized Inputs
      |
      v
Intermediate Measures
      |
      v
Operational Risk Capital
      |
      v
Reports / Audit Logs
```

데이터는 단방향으로 흐르며, 계산 단계는 이전 단계의 결과를 기반으로 수행된다.

---

# 7. Formula Integration

```text
FC-471
Operational Risk Capital Formula
        |
        v
Capital Engine
```

Formula는 구현 세부사항과 분리되지만, 아키텍처는 Formula의 입력과 출력을 명확히 수용해야 한다.

---

# 8. Traceability Architecture

모든 계산은 추적 가능해야 한다.

```text
Input Data
      |
      v
Formula Execution
      |
      v
Intermediate Result
      |
      v
Final Capital
```

감사, 검증, 재현성을 위해 각 단계는 기록 가능해야 한다.

---

# 9. Quality Attributes

| Attribute | Description |
| --------- | ----------- |
| Accuracy | Formula와 일치하는 계산 결과 |
| Scalability | 대용량 손실 및 BI 데이터 처리 |
| Traceability | 계산 이력 추적 가능 |
| Maintainability | 규제 변경 시 영향 최소화 |
| Reusability | 다른 리스크 도메인에서도 재사용 가능한 구조 |

---

# 10. Relationship with FRKP

```text
Reference Library
        |
        v
Knowledge Base
        |
        v
Analysis
        |
        v
Mathematical Foundation
        |
        v
Formula Catalog
        |
        v
Implementation Guide
        |
        v
Architecture Guide
```

본 문서는 Bundle-007의 최종 설계 계층이다.

---

# 11. Cross References

| Category                | Document |
| ----------------------- | -------- |
| Reference               | [RL-170_OPERATIONAL_RISK_OVERVIEW](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md) |
| Knowledge               | [KB-271_OPERATIONAL_RISK_FRAMEWORK](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md) |
| Knowledge               | [KB-272_STANDARDIZED_MEASUREMENT_APPROACH](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md) |
| Analysis                | [AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md) |
| Mathematical Foundation | [MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md) |
| Formula                 | [FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md) |
| Implementation          | [IMP-471_OPERATIONAL_RISK_IMPLEMENTATION](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md) |

---

# 12. Summary

Operational Risk Architecture defines a deterministic and traceable system structure for turning operational loss data and business indicator inputs into regulatory capital outputs.

The architecture is technology neutral and designed to support governance, auditability, and future extensibility.

---

# 13. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-771 Operational Risk Architecture | Capital engine, reporting, audit, and traceability architecture |
| Candidate Capability | CAP-EXE-008 Architecture Enforcement | Architecture consistency and component separation |
| Candidate Capability | CAP-KNW-006 Cross-Reference Linking | Architecture linkage to formula and implementation layers |
| Candidate Evidence | EVD-000348 Implementation Considerations | Implementation-to-architecture basis |
| Candidate Evidence | EVD-000349 Architecture Considerations | Architecture design basis |

---

# 14. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Added candidate traceability references and related document metadata |
