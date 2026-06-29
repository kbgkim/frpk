# KB-271 - Operational Risk Framework

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | KB-271                          |
| Document Name | Operational Risk Framework      |
| Version       | 1.0.0                           |
| Status        | Active                          |
| Category      | Knowledge Base                  |
| Parent Bundle | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Knowledge Base](../README.md) > [KB-271 - Operational Risk Framework](KB-271_OPERATIONAL_RISK_FRAMEWORK.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | [KB-272](KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md) |

### Related Documents

- [RL-170](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-272](KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [AN-271](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [FC-471](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [MF-471](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [ARCH-771](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
- [IMP-471](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Operational Risk의 핵심 개념, 관리 프레임워크 및 FRKP Bundle-007의 Knowledge Base 구조를 정의한다.

운영리스크는 금융기관의 내부 통제, 운영 안정성, 손실 데이터 관리, 자본 산출을 함께 고려해야 하므로 개념적 프레임워크가 중요하다.

---

# 2. Background

운영리스크는 전통적으로 신용리스크나 시장리스크보다 정량화가 어려운 영역으로 간주되었다.

그 이유는 다음과 같다.

* 손실 사건이 비정형적이다.
* 원인이 복합적이다.
* 통제 환경의 영향이 크다.
* 데이터 품질이 기관마다 다르다.

이러한 특성 때문에 운영리스크는 단순한 회계 항목이 아니라, 거버넌스와 규제자본을 동시에 요구하는 위험으로 발전했다.

---

# 3. Objectives

Operational Risk Framework의 목적은 다음과 같다.

* 운영리스크의 범주를 정의한다.
* 손실 사건과 통제 체계의 관계를 설명한다.
* 규제 자본 산출의 상위 구조를 제시한다.
* SMA로의 전환 논리를 이해할 수 있게 한다.
* 구현과 아키텍처의 상위 개념을 제공한다.

---

# 4. Operational Risk Model

운영리스크는 다음 세 가지 축으로 이해할 수 있다.

| Axis         | Description |
| ------------ | ----------- |
| Event        | 실제 손실 사건과 그 빈도 |
| Control      | 예방 및 탐지 통제 체계 |
| Capital      | 손실 흡수를 위한 규제자본 |

세 축은 독립적이지 않으며, 서로 상호작용한다.

---

# 5. Core Definitions

## Risk Event

손실 또는 손실 가능성을 유발하는 개별 사건.

## Loss Data

운영리스크 손실을 식별, 측정, 추적하기 위한 사건 기록.

## Control Failure

프로세스, 사람, 시스템 또는 외부 대응 체계가 기대 기능을 수행하지 못하는 상태.

## Risk Governance

운영리스크를 식별, 측정, 통제, 모니터링하는 조직적 체계.

---

# 6. Framework Structure

```text
Operational Risk
        |
        +-- Risk Events
        |
        +-- Loss Data
        |
        +-- Control Environment
        |
        +-- Regulatory Capital
```

운영리스크 프레임워크는 위 네 요소를 하나의 관리 체계로 묶는다.

---

# 7. Historical Context

운영리스크 규제는 초기에는 비교적 단순한 접근법에 의존했으나, 시간이 지나면서 기관 규모와 손실 경험을 더 잘 반영하는 방식으로 진화했다.

핵심 변화는 다음과 같다.

* 단순 수익 기반 측정에서 벗어남
* 내부 손실 경험의 반영 강화
* 기관 규모에 따른 차등화
* 규제 비교 가능성 강화

---

# 8. Relationship with Control Environment

운영리스크는 자본만으로 해결되지 않는다.

통제 환경은 다음 역할을 수행한다.

* 손실 예방
* 손실 조기 탐지
* 재발 방지
* 데이터 품질 개선

따라서 운영리스크 프레임워크는 자본 산출과 통제 운영을 동시에 다룬다.

---

# 9. Relationship with Bundle-007

```text
RL-170
   |
   v
KB-271
   |
   +-- KB-272
   |
   +-- AN-271
   |
   +-- MF-471
   |
   +-- FC-471
   |
   +-- IMP-471
   |
   +-- ARCH-771
```

본 문서는 Bundle-007의 Knowledge Base 중심 문서이며, 이후 세부 문서의 상위 개념을 제공한다.

---

# 10. Cross References

| Category                | Document |
| ----------------------- | -------- |
| Reference               | [RL-170_OPERATIONAL_RISK_OVERVIEW](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md) |
| Knowledge               | [KB-272_STANDARDIZED_MEASUREMENT_APPROACH](KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md) |
| Analysis                | [AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md) |
| Mathematical Foundation | [MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md) |
| Formula                 | [FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md) |
| Implementation          | [IMP-471_OPERATIONAL_RISK_IMPLEMENTATION](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md) |
| Architecture            | [ARCH-771_OPERATIONAL_RISK_ARCHITECTURE](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md) |

---

# 11. Summary

Operational Risk Framework는 운영리스크를 사건, 통제, 자본의 세 축으로 해석하는 상위 구조를 제공한다.

본 문서는 Bundle-007의 핵심 Knowledge Base로서, 이후 SMA 설명, 분석 문서, 수학적 기반, Formula 및 구현 아키텍처를 연결하는 기준점이 된다.

---

# 12. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-271 Operational Risk Framework | Event, loss data, control, governance, and capital framework |
| Candidate Capability | CAP-KNW-003 Terminology Management | Canonical operational risk vocabulary |
| Candidate Capability | CAP-KNW-005 Knowledge Layering | Knowledge Base bridge from reference to downstream layers |
| Candidate Evidence | EVD-000340 Operational Risk | Operational risk framework basis |
| Candidate Evidence | EVD-000341 Historical Basel Operational Risk Evolution | Basel evolution context |
| Candidate Evidence | EVD-000347 Operational Loss Data | Loss data and event record basis |

---

# 13. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Added candidate traceability references and related document metadata |
