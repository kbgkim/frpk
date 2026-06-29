# RL-170 - Operational Risk Overview

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | RL-170                          |
| Document Name | Operational Risk Overview       |
| Version       | 1.0.0                           |
| Status        | Active                          |
| Category      | Reference Library               |
| Parent Bundle | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Reference Library](../README.md) > [RL-170 - Operational Risk Overview](RL-170_OPERATIONAL_RISK_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Reference Library](../README.md) |
| ➡ Next | None |

### Related Documents

- [KB-271](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [KB-272](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [AN-271](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [FC-471](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [MF-471](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [ARCH-771](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
- [IMP-471](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Operational Risk의 개요와 FRKP Bundle-007의 상위 참조 역할을 정의한다.

Operational Risk는 내부 프로세스, 사람, 시스템의 실패 또는 외부 사건으로 인해 발생하는 손실 위험을 다루며, 본 문서는 이후 Knowledge Base, Analysis, Mathematical Foundation, Formula Catalog, Implementation Guide, Architecture Guide의 상위 레퍼런스로 사용된다.

---

# 2. Background

Operational Risk는 금융기관의 일상 운영과 직접 연결된 위험이다.

대표적인 원인은 다음과 같다.

* Process failure
* Human error
* System outage
* Fraud and misconduct
* External event

규제 관점에서는 운영리스크를 단순한 사고 관리가 아니라, 자본 적정성, 통제 체계, 데이터 품질, 거버넌스를 포함하는 포괄적 관리 대상으로 다룬다.

---

# 3. Objectives

Operational Risk Bundle의 목적은 다음과 같다.

* 운영리스크의 정의와 범위를 명확히 한다.
* 기존 접근법과 새로운 표준 측정법의 차이를 설명한다.
* 규제자본 산출 논리를 문서화한다.
* 내부손실 데이터와 자본 산출의 연결성을 정의한다.
* 구현 및 아키텍처 설계의 상위 기준을 제공한다.

---

# 4. Scope

본 문서는 다음 내용을 포함한다.

* Operational Risk definition
* Loss event concept
* Internal loss data
* Control environment
* Regulatory capital context
* Standardized Measurement Approach(SMA)

다음 내용은 별도 문서에서 상세히 다룬다.

* Legacy Basel II operational risk approaches
* Detailed business indicator mechanics
* Implementation workflow
* Engine architecture

---

# 5. Position within FRKP

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

본 문서는 Bundle-007 전체의 상위 진입점이다.

---

# 6. Core Concepts

## Operational Risk

내부 프로세스, 사람, 시스템의 실패 또는 외부 사건으로 인해 발생하는 손실 위험.

## Loss Event

운영리스크가 실제 손실로 실현된 사건.

## Control Environment

운영리스크를 예방, 탐지, 완화하기 위한 정책, 통제, 모니터링 체계.

## Capital Requirement

운영리스크 손실을 흡수하기 위해 보유해야 하는 규제자본.

---

# 7. Regulatory Direction

운영리스크 규제는 과거의 단순 수익 기반 측정에서 벗어나, 규모와 손실 경험을 함께 반영하는 방향으로 발전했다.

FRKP Bundle-007은 이러한 변화를 다음 구조로 정리한다.

```text
Operational Risk Definition
        |
        v
Loss Data and Control Context
        |
        v
Standardized Measurement Approach
        |
        v
Capital Formula
        |
        v
Implementation and Architecture
```

---

# 8. Relationship with Other Bundles

```text
Bundle-001
Basel III
        |
        v
Bundle-007
Operational Risk
```

Bundle-007은 Basel III 기반의 운영리스크 관리 체계를 FRKP 구조에 연결한다.

---

# 9. Bundle-007 Deliverables

예정 산출물은 다음과 같다.

| Layer  | Planned Document                              |
| ------ | --------------------------------------------- |
| RL     | RL-170 Operational Risk Overview              |
| KB     | KB-271 Operational Risk Framework             |
| KB     | KB-272 Standardized Measurement Approach      |
| AN     | AN-271 Why Operational Risk Capital Changed   |
| MF     | MF-471 Operational Risk Loss Distribution     |
| FC     | FC-471 Operational Risk Capital Formula       |
| IMP    | IMP-471 Operational Risk Implementation Guide |
| ARCH   | ARCH-771 Operational Risk Architecture        |
| REVIEW | BUNDLE-007 Operational Risk Review            |

---

# 10. Summary

Operational Risk는 금융기관의 운영 현실과 가장 직접적으로 연결되는 규제 위험 중 하나이며, 손실 이벤트와 통제 환경, 자본 요구량을 하나의 구조로 해석해야 한다.

본 문서는 Bundle-007의 상위 Reference로서, 이후 Knowledge Base, Analysis, Mathematical Foundation, Formula Catalog, Implementation Guide 및 Architecture Guide의 공통 출발점을 제공한다.

---

# 11. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-170 Operational Risk Overview | Operational Risk definition and Bundle-007 reference entry point |
| Candidate Capability | CAP-KNW-001 Canonical Knowledge Storage | Reference-layer knowledge anchor |
| Candidate Capability | CAP-KNW-006 Cross-Reference Linking | Bundle entry-point navigation and downstream references |
| Candidate Evidence | EVD-000340 Operational Risk | Operational Risk concept basis |
| Candidate Evidence | EVD-000341 Historical Basel Operational Risk Evolution | Basel operational risk context |
| Candidate Evidence | EVD-000342 Standardized Measurement Approach | SMA regulatory direction |

---

# 12. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Added candidate traceability references and related document metadata |
