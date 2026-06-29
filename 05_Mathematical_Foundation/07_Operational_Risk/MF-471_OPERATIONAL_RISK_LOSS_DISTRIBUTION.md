# MF-471 - Operational Risk Loss Distribution

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | MF-471                          |
| Document Name | Operational Risk Loss Distribution |
| Version       | 1.0.0                           |
| Status        | Active                          |
| Category      | Mathematical Foundation         |
| Parent Bundle | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Mathematical Foundation](../README.md) > [MF-471 - Operational Risk Loss Distribution](MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Mathematical Foundation](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-170](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-271](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [KB-272](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [AN-271](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)
- [FC-471](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [IMP-471](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
- [ARCH-771](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 운영리스크 손실 분포의 수학적 구조를 설명한다.

운영리스크는 사건 빈도와 사건 심각도가 복합적으로 작용하므로, 손실 분포는 규제자본 산출과 시나리오 분석의 핵심 수학적 기반이 된다.

---

# 2. Background

운영리스크 손실은 일반적인 단일 정규분포 가정으로 충분히 설명되지 않는다.

주요 이유는 다음과 같다.

* 사건 빈도는 희소하다.
* 손실 심각도는 꼬리가 두껍다.
* 대형 사고가 전체 손실을 지배할 수 있다.
* 데이터가 불완전하거나 비대칭적이다.

---

# 3. Aggregate Loss Model

운영리스크의 연간 총손실은 일반적으로 다음 구조로 표현한다.

```text
L = sum(i = 1 to N) X_i
```

여기서:

| Symbol | Description |
| ------ | ----------- |
| L      | 연간 총손실 |
| X_i    | i번째 손실 사건 |
| N      | 연간 사건 수 |

보다 일반적으로는 빈도와 심각도를 분리하여 해석한다.

```text
Annual Loss = aggregate of N loss severities over the observation period
```

---

# 4. Frequency-Severity Decomposition

운영리스크는 다음 두 구성요소로 분해할 수 있다.

| Component | Description |
| --------- | ----------- |
| Frequency | 일정 기간 내 손실 사건 발생 횟수 |
| Severity | 개별 사건의 손실 금액 |

이 분해는 손실 데이터 모델링, 시나리오 분석, 자본 민감도 해석에 유용하다.

---

# 5. Loss Distribution Properties

운영리스크 손실 분포는 다음 특성을 가진다.

* Positive support
* Right skewness
* Heavy tail behavior
* Data sparsity

따라서 운영리스크는 극단값과 드문 사건을 고려한 모델링이 필요하다.

---

# 6. Mathematical Interpretation

손실 분포는 단순 평균보다 다음 관점이 중요하다.

* tail behavior
* loss aggregation
* scenario sensitivity
* data truncation impact

이러한 특성은 운영리스크 자본이 손실 경험에 민감해야 하는 이유를 수학적으로 설명한다.

---

# 7. Relationship with SMA

```text
Loss Events
      |
      v
Loss Distribution
      |
      v
Loss Component
      |
      v
Internal Loss Multiplier
      |
      v
Operational Risk Capital
```

운영리스크 손실 분포는 SMA의 Loss Component 및 Internal Loss Multiplier 해석을 뒷받침한다.

For Bundle-007 formula interpretation, LC is the SMA loss component derived from internal loss experience, while ILM is the Basel multiplier that relates LC to BIC.

---

# 8. Modeling Use Cases

손실 분포는 다음 용도에 사용된다.

* 내부 손실 데이터 분석
* 시나리오 손실 추정
* 꼬리위험 검토
* 자본 민감도 해석
* 통제 효과 검증

---

# 9. Relationship with Bundle-007

본 문서는 Bundle-007의 Formula 및 Implementation에 필요한 수학적 토대를 제공한다.

```text
MF-471
   |
   v
FC-471
   |
   v
IMP-471
   |
   v
ARCH-771
```

---

# 10. Cross References

| Category                | Document |
| ----------------------- | -------- |
| Reference               | [RL-170_OPERATIONAL_RISK_OVERVIEW](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md) |
| Knowledge               | [KB-271_OPERATIONAL_RISK_FRAMEWORK](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md) |
| Knowledge               | [KB-272_STANDARDIZED_MEASUREMENT_APPROACH](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md) |
| Analysis                | [AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED](../../03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md) |
| Formula                 | [FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md) |
| Implementation Guide    | [IMP-471_OPERATIONAL_RISK_IMPLEMENTATION](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md) |
| Architecture            | [ARCH-771_OPERATIONAL_RISK_ARCHITECTURE](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md) |

---

# 11. Summary

운영리스크 손실 분포는 빈도와 심각도의 결합으로 이해해야 하며, 희소성과 꼬리위험을 동시에 고려해야 한다.

본 문서는 Bundle-007의 수학적 기반을 제공하며, 자본 공식과 구현 절차가 손실 경험을 어떻게 반영해야 하는지 설명한다.

---

# 12. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-471M Operational Risk Loss Distribution | Frequency-severity and aggregate loss interpretation |
| Candidate Capability | CAP-KNW-002 Evidence Registration & Mapping | Evidence mapping for LC and loss data claims |
| Candidate Capability | CAP-KNW-005 Knowledge Layering | Mathematical Foundation support for formula interpretation |
| Candidate Evidence | EVD-000345 Loss Component | LC interpretation basis |
| Candidate Evidence | EVD-000347 Operational Loss Data | Operational loss data basis |

---

# 13. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Improved aggregate loss notation and added candidate traceability references |
