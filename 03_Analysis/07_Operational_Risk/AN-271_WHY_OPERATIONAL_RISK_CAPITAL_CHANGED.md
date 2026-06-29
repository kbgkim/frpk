# AN-271 - Why Operational Risk Capital Changed

---

# Document Information

| Item          | Value                           |
| ------------- | ------------------------------- |
| Document ID   | AN-271                          |
| Document Name | Why Operational Risk Capital Changed |
| Version       | 1.0.0                           |
| Status        | Active                          |
| Category      | Analysis                        |
| Parent Bundle | [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| Domain        | Operational Risk                |
| Created       | 2026-06-28                      |
| Last Updated  | 2026-06-29                      |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) > [Analysis](../README.md) > [AN-271 - Why Operational Risk Capital Changed](AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-007](../../08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md) |
| ⬆ Parent Layer | [Analysis](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-170](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md)
- [KB-271](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md)
- [KB-272](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md)
- [MF-471](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md)
- [FC-471](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md)
- [IMP-471](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md)
- [ARCH-771](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 운영리스크 자본 산출 방식이 왜 변화했는지 분석한다.

특히 수익 기반 또는 내부모형 중심 접근이 가진 한계와, 규모 및 내부 손실 경험을 함께 반영하는 표준 측정 접근으로의 전환 이유를 설명한다.

---

# 2. Historical Context

운영리스크 자본은 장기간에 걸쳐 여러 접근법을 거쳤다.

```text
Income Proxy
      |
      v
Standardized / Indicator Approaches
      |
      v
Internal Model Emphasis
      |
      v
Standardized Measurement Approach
```

이 변화는 운영리스크의 정량화 가능성과 규제 일관성에 대한 재평가 결과이다.

---

# 3. Limitations of Legacy Approaches

## 3.1 Income Proxy Weakness

수익 규모는 운영리스크 노출을 완전히 설명하지 못한다.

같은 수익을 가진 기관이라도 운영 프로세스, 통제 수준, 시스템 복잡성은 다를 수 있다.

## 3.2 Model Variability

내부모형 기반 접근은 기관별 가정, 데이터, 보정 방식의 차이로 인해 결과 비교가 어려웠다.

## 3.3 Loss Experience Gap

과거 손실 경험이 자본에 충분히 반영되지 않으면, 통제 개선의 인센티브가 약해진다.

---

# 4. Drivers of Change

운영리스크 자본 산출이 변화한 주요 이유는 다음과 같다.

| Driver | Impact |
| ------ | ------ |
| Comparability | 기관 간 규제 비교 가능성 강화 |
| Simplicity | 복잡한 내부모형 의존 축소 |
| Loss Sensitivity | 실제 손실 경험 반영 강화 |
| Governance | 내부통제 및 데이터 품질 개선 유도 |
| Supervisory Consistency | 감독기관의 일관된 적용 지원 |

---

# 5. Why SMA?

SMA는 다음 균형을 추구한다.

* 단순한 계산 구조
* 규모 반영
* 손실 경험 반영
* 비교 가능성
* 설명 가능성

즉, SMA는 운영리스크를 완전히 모델링하려는 것이 아니라, 규제자본 산출에 필요한 최소한의 강건성과 일관성을 확보하려는 접근이다.

---

# 6. Architectural Implications

자본 산출 기준이 바뀌면 시스템도 바뀐다.

운영리스크 아키텍처는 다음 기능을 요구한다.

* Business Indicator 계산
* Loss Data 관리
* Regulatory scaling
* Audit trail
* Exception handling

이는 단일 수치 계산이 아니라 데이터와 거버넌스를 포함한 엔드투엔드 파이프라인이다.

---

# 7. Risk Management Implications

자본 산출 변화는 관리 방식의 변화로 이어진다.

* 손실 이벤트 기록 체계 강화
* 내부통제 이력의 구조화
* 운영리스크 위원회와 보고 체계 정비
* 데이터 보존 및 품질 관리 강화

---

# 8. Relationship with Bundle-007

```text
RL-170
   |
   v
KB-271
   |
   v
KB-272
   |
   v
AN-271
   |
   +-- MF-471
   +-- FC-471
   +-- IMP-471
   +-- ARCH-771
```

본 문서는 Bundle-007의 설계 근거를 제공하는 분석 계층이다.

---

# 9. Summary

운영리스크 자본 산출 방식은 단순 수익 대리변수나 기관별 편차가 큰 내부모형에서 벗어나, 기관 규모와 내부 손실 경험을 함께 반영하는 방향으로 변화했다.

이 변화는 비교 가능성, 설명 가능성, 감독 일관성을 높이며, FRKP Bundle-007의 표준 측정 접근법과 후속 구현 설계를 정당화한다.

---

# 10. Cross References

| Category                | Document |
| ----------------------- | -------- |
| Reference               | [RL-170_OPERATIONAL_RISK_OVERVIEW](../../01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md) |
| Knowledge               | [KB-271_OPERATIONAL_RISK_FRAMEWORK](../../02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md) |
| Knowledge               | [KB-272_STANDARDIZED_MEASUREMENT_APPROACH](../../02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md) |
| Mathematical Foundation | [MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION](../../05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md) |
| Formula                 | [FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA](../../04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md) |
| Implementation Guide    | [IMP-471_OPERATIONAL_RISK_IMPLEMENTATION](../../06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md) |
| Architecture            | [ARCH-771_OPERATIONAL_RISK_ARCHITECTURE](../../07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md) |

---

# 11. Traceability References

| Type | Candidate Reference | Basis |
| ---- | ------------------- | ----- |
| Candidate KO | KO-OPR-271A Operational Risk Capital Change Rationale | Analysis of legacy approach limitations and SMA transition rationale |
| Candidate Capability | CAP-KNW-003 Terminology Management | Consistent historical and regulatory vocabulary |
| Candidate Capability | CAP-KNW-006 Cross-Reference Linking | Analysis-layer links to formula, implementation, and architecture |
| Candidate Evidence | EVD-000341 Historical Basel Operational Risk Evolution | Legacy approach and transition basis |
| Candidate Evidence | EVD-000342 Standardized Measurement Approach | SMA transition basis |
| Candidate Evidence | EVD-000347 Operational Loss Data | Loss experience rationale |

---

# 12. Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-28 | Initial version |
| 1.0.1   | 2026-06-29 | Added candidate traceability references |
