# AN-231 — Why Incurred Loss Failed

---

# Document Information

| Item            | Value                    |
| --------------- | ------------------------ |
| Document ID     | AN-231                   |
| Document Name   | Why Incurred Loss Failed |
| Version         | 1.0.0                    |
| Status          | Draft                    |
| Category        | Analysis                 |
| Parent Document | RL-130                   |
| Created         | 2026-06-26               |
| Last Updated    | 2026-06-26               |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Analysis](../README.md) > [AN-231 — Why Incurred Loss Failed](AN-231_WHY_INCURRED_LOSS_FAILED.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Analysis](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)
- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
- [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)
- [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)
- [FC-432](../../04_Formula_Catalog/03_IFRS9/FC-432_LOSS_GIVEN_DEFAULT.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 IAS 39의 **발생손실(Incurred Loss)** 모형이 금융위기에서 드러낸 한계를 분석하고, IFRS 9의 **기대신용손실(Expected Credit Loss, ECL)** 모형이 도입된 배경과 설계 의도를 설명한다.

본 문서는 회계 기준의 변화뿐 아니라 신용위험 관리 방식의 변화와 시스템 설계 관점에서의 의미를 함께 분석한다.

---

# 2. Background

IAS 39에서는 금융자산의 손실을 인식하기 위해 **손상사건(Loss Event)** 이 발생해야 했다.

즉,

* 연체
* 부도
* 파산
* 계약 위반

과 같은 객관적인 증거가 있어야만 충당금을 설정할 수 있었다.

이 접근법을 **Incurred Loss Model**이라고 한다.

---

# 3. Core Problem

발생손실 모형의 가장 큰 문제는 다음과 같다.

> **손실을 예측하지 않고, 손실이 발생한 이후에만 회계에 반영한다.**

즉,

```text
Risk Increase
      │
      │
      │
      ▼
Loss Event
      │
      ▼
Provision Recognition
```

위험은 이미 증가했지만 회계는 이를 반영하지 못한다.

---

# 4. What Happened During the Financial Crisis?

2007~2008년 글로벌 금융위기에서는 많은 차주의 신용상태가 빠르게 악화되었다.

그러나 상당수 금융기관은 손상사건이 발생하기 전까지 손실을 인식하지 않았다.

그 결과,

* 재무제표상 자산가치가 실제보다 높게 유지되었다.
* 손실이 특정 시점에 집중적으로 반영되었다.
* 투자자와 감독당국이 위험을 늦게 인지하였다.
* 경기 침체기에 충당금이 급증하며 경기 변동성이 확대되었다.

이를 **"Too Little, Too Late"** 문제라고 한다.

---

# 5. Timeline Comparison

### IAS 39 (Incurred Loss)

```text
정상
 │
 │
신용위험 증가
 │
 │
 │
손상사건 발생
 │
 ▼
충당금 인식
```

손실 인식이 위험 변화보다 뒤따른다.

---

### IFRS 9 (Expected Credit Loss)

```text
정상
 │
 ▼
신용위험 증가
 │
 ▼
Expected Credit Loss 계산
 │
 ▼
충당금 조정
```

위험 변화가 시작되면 손실 추정을 즉시 반영한다.

---

# 6. Root Causes

IAS 39의 구조적 한계는 다음과 같다.

| Limitation              | Description |
| ----------------------- | ----------- |
| Reactive Model          | 사후 대응 중심    |
| Historical Information  | 과거 정보 중심    |
| Delayed Recognition     | 손실 인식 지연    |
| Binary Decision         | 손상 여부만 판단   |
| Limited Forward Looking | 미래 정보 활용 부족 |

---

# 7. Design Goals of IFRS 9

IFRS 9는 다음 목표를 달성하기 위해 설계되었다.

* 미래 전망(Forward-looking Information) 반영
* 조기 손실 인식
* 경기순응성(Procyclicality) 완화
* 신용위험 증가의 지속적 모니터링
* 회계와 리스크 관리의 정합성 강화

---

# 8. From Loss Event to Credit Quality

IAS 39는 **손상사건**을 중심으로 판단하였다.

IFRS 9는 **신용 품질(Credit Quality)** 의 변화를 중심으로 판단한다.

```text
IAS 39

Loss Event
      │
      ▼
Provision

────────────────────

IFRS 9

Credit Quality
      │
      ▼
Stage
      │
      ▼
Expected Credit Loss
```

핵심 판단 기준이 변경되었다.

---

# 9. System Perspective

시스템 구조도 크게 달라졌다.

### IAS 39

```text
Accounting Event
      │
      ▼
Provision
```

---

### IFRS 9

```text
Credit Data
      │
      ▼
PD
LGD
EAD
      │
      ▼
Stage Assessment
      │
      ▼
Expected Credit Loss
      │
      ▼
Provision
```

회계 시스템이 신용위험 모델과 직접 연결되기 시작했다.

---

# 10. Impact on Financial Institutions

IFRS 9 도입으로 금융기관은 다음 기능을 구축해야 했다.

* PD 모델
* LGD 모델
* EAD 모델
* Stage 분류
* 미래 거시경제 시나리오
* ECL 계산 엔진
* 충당금 관리

즉, 회계 시스템이 리스크 엔진과 통합되었다.

---

# 11. Relationship with Basel III

```text
Credit Risk
      │
      ├───────────────┐
      ▼               ▼
IFRS 9           Basel III
      │               │
Expected Loss    Unexpected Loss
      │               │
Provision        Regulatory Capital
```

두 체계는 목적은 다르지만 동일한 신용위험 데이터를 활용한다.

---

# 12. Lessons Learned

금융위기는 다음 사실을 보여주었다.

> **손실은 갑자기 발생하는 것이 아니라, 신용 품질이 점진적으로 악화되는 과정에서 축적된다.**

따라서 회계는 결과만 기록하는 것이 아니라 **위험의 진행 과정**을 반영해야 한다.

---

# 13. Relationship with FRKP

| Layer          | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-130](../../01_Reference_Library/03_IFRS9/RL-130_IFRS9_OVERVIEW.md)           |
| Knowledge      | [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md), [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)   |
| Analysis       | [AN-231](AN-231_WHY_INCURRED_LOSS_FAILED.md)           |
| Formula        | [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md) ~ [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)  |
| Implementation | [IMP-431](../../06_Implementation_Guide/03_IFRS9/IMP-431_EXPECTED_CREDIT_LOSS_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-731](../../07_Architecture/03_IFRS9/ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)         |

---

# 14. Knowledge Graph

```text
IAS 39
      │
      ▼
Incurred Loss
      │
      ▼
Delayed Recognition
      │
      ▼
Financial Crisis
      │
      ▼
IFRS 9
      │
      ▼
Credit Quality
      │
      ▼
Expected Credit Loss
```

---

# 15. Learning Path

```text
RL-130 IFRS 9 Overview
        │
        ▼
KB-231 Credit Risk Overview
        │
        ▼
AN-231 Why Incurred Loss Failed
        │
        ▼
KB-232 IFRS 9 Framework
        │
        ▼
FC-431 Probability of Default
        │
        ▼
FC-432 Loss Given Default
        │
        ▼
FC-433 Exposure at Default
        │
        ▼
FC-434 Expected Credit Loss
        │
        ▼
IMP-431 Expected Credit Loss Implementation
        │
        ▼
ARCH-731 IFRS 9 Calculation Architecture
```

---

# 16. Summary

IAS 39의 발생손실 모형은 손상사건이 발생한 이후에만 손실을 인식하는 구조였기 때문에 금융위기에서 위험을 적시에 반영하지 못했다.

IFRS 9는 이러한 한계를 극복하기 위해 **신용 품질의 변화**를 지속적으로 평가하고, PD·LGD·EAD를 활용한 **Expected Credit Loss(ECL)** 모형을 도입하였다.

FRKP에서는 이를 단순한 회계 기준의 변경이 아니라 **사후 기록 중심 시스템에서 미래 예측 기반 신용위험 관리 시스템으로의 전환**으로 정의한다.

---

# 17. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
