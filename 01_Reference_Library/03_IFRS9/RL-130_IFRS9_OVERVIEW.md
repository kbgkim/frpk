# RL-130 — IFRS 9 Overview

---

# Document Information

| Item            | Value             |
| --------------- | ----------------- |
| Document ID     | RL-130            |
| Document Name   | IFRS 9 Overview   |
| Version         | 1.0.0             |
| Status          | Draft             |
| Category        | Reference Library |
| Parent Document | RL-110            |
| Created         | 2026-06-26        |
| Last Updated    | 2026-06-26        |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) > [Reference Library](../README.md) > [RL-130 — IFRS 9 Overview](RL-130_IFRS9_OVERVIEW.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-003](../../08_Bundles/BUNDLE-003_IFRS9_REVIEW.md) |
| ⬆ Parent Layer | [Reference Library](../README.md) |
| ➡ Next | None |

### Related Documents

- [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md)
- [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)
- [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)
- [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md)
- [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 국제회계기준 **IFRS 9 Financial Instruments**의 목적, 도입 배경 및 전체 구조를 설명하는 Reference Library 문서이다.

IFRS 9는 금융자산의 분류(Classification), 측정(Measurement), 손상(Impairment), 위험회피회계(Hedge Accounting)를 정의하는 국제회계기준이며, 특히 **Expected Credit Loss(ECL)** 기반의 손상모형을 도입하여 금융기관의 신용손실 인식 방식을 근본적으로 변경하였다.

본 문서는 IFRS 9의 전체 개요를 제공하며, 세부 내용은 Knowledge Base, Analysis, Formula Catalog, Implementation Guide 및 Architecture Guide에서 다룬다.

---

# 2. Background

기존 국제회계기준(IAS 39)은 **발생손실(Incurred Loss)** 모형을 사용하였다.

이 모형에서는 객관적인 손상사건(Objective Evidence)이 발생한 이후에만 손실을 인식할 수 있었다.

2007~2008년 글로벌 금융위기에서는 다음과 같은 문제가 드러났다.

* 손실 인식이 지나치게 늦었다.
* 금융기관의 실제 위험을 적시에 반영하지 못했다.
* 경기 침체 시 대규모 손실이 한꺼번에 인식되었다.
* 회계정보의 예측 가능성이 낮았다.

이를 개선하기 위해 IFRS 9는 **Expected Credit Loss(ECL)** 모형을 도입하였다.

---

# 3. Objectives

IFRS 9의 주요 목표는 다음과 같다.

* 미래 예상 신용손실의 조기 인식
* 금융자산의 합리적인 분류 및 측정
* 회계정보의 투명성 향상
* 신용위험 증가의 지속적인 모니터링
* 회계와 위험관리의 정합성 강화

---

# 4. IFRS 9 Framework

```text
Financial Instruments
        │
        ▼
IFRS 9
        │
 ┌──────┼───────────────┐
 ▼      ▼               ▼
Classification   Impairment   Hedge Accounting
& Measurement        │
                     ▼
          Expected Credit Loss (ECL)
```

IFRS 9는 크게 다음 세 영역으로 구성된다.

* Classification and Measurement
* Impairment
* Hedge Accounting

FRKP에서는 **Impairment(ECL)** 를 중심으로 다룬다.

---

# 5. Scope of FRKP

FRKP에서 IFRS 9는 다음 범위를 중심으로 구성한다.

* Credit Risk
* Expected Credit Loss (ECL)
* Probability of Default (PD)
* Loss Given Default (LGD)
* Exposure at Default (EAD)
* Staging (Stage 1 / 2 / 3)
* Lifetime ECL
* 12-Month ECL

분류·측정 및 위험회피회계는 개요 수준으로 설명하고, 핵심은 신용손실 측정 체계에 둔다.

---

# 6. Major Changes from IAS 39

| IAS 39        | IFRS 9               |
| ------------- | -------------------- |
| Incurred Loss | Expected Credit Loss |
| 과거 사건 중심      | 미래 전망 포함             |
| 손상 발생 후 인식    | 예상 손실 선제 인식          |
| 단일 손상 접근      | Stage 기반 접근          |
| 손실 인식 지연      | 조기 손실 인식             |

---

# 7. Core Concepts

| Concept                                    | Description            |
| ------------------------------------------ | ---------------------- |
| Expected Credit Loss (ECL)                 | 예상 신용손실                |
| Probability of Default (PD)                | 부도확률                   |
| Loss Given Default (LGD)                   | 부도 시 손실률               |
| Exposure at Default (EAD)                  | 부도 시 익스포저              |
| Stage 1                                    | 정상자산 (12개월 ECL)        |
| Stage 2                                    | 신용위험 증가 (Lifetime ECL) |
| Stage 3                                    | 손상자산 (Lifetime ECL)    |
| Significant Increase in Credit Risk (SICR) | 신용위험 유의적 증가 판단 기준      |

---

# 8. ECL Calculation Flow

```text
Financial Asset
        │
        ▼
Credit Risk Assessment
        │
        ▼
Stage Classification
        │
        ▼
PD / LGD / EAD
        │
        ▼
Expected Credit Loss
        │
        ▼
Impairment Allowance
```

ECL은 금융자산의 장부금액(Carrying Amount)을 조정하는 손상충당금(Impairment Allowance) 계산에 사용된다.

---

# 9. Relationship with Basel III

| Basel III                      | IFRS 9                  |
| ------------------------------ | ----------------------- |
| Regulatory Capital             | Financial Reporting     |
| Capital Adequacy               | Financial Statements    |
| Unexpected Loss 중심             | Expected Loss 중심        |
| Market/Credit/Operational Risk | Credit Loss Recognition |
| RWA 계산                         | 손상충당금 계산                |

두 체계는 목적은 다르지만, 모두 신용위험 데이터를 활용하며 PD, LGD, EAD 등의 공통 요소를 공유한다.

---

# 10. Relationship with FRKP

| FRKP Layer     | Related Document |
| -------------- | ---------------- |
| Reference      | [RL-130](RL-130_IFRS9_OVERVIEW.md)           |
| Knowledge      | [KB-231](../../02_Knowledge_Base/03_IFRS9/KB-231_CREDIT_RISK_OVERVIEW.md), [KB-232](../../02_Knowledge_Base/03_IFRS9/KB-232_IFRS9_FRAMEWORK.md)   |
| Analysis       | [AN-231](../../03_Analysis/03_IFRS9/AN-231_WHY_INCURRED_LOSS_FAILED.md)           |
| Formula        | [FC-431](../../04_Formula_Catalog/03_IFRS9/FC-431_PROBABILITY_OF_DEFAULT.md) ~ [FC-434](../../04_Formula_Catalog/03_IFRS9/FC-434_EXPECTED_CREDIT_LOSS.md)  |
| Implementation | [IMP-431](../../06_Implementation_Guide/03_IFRS9/IMP-431_EXPECTED_CREDIT_LOSS_IMPLEMENTATION.md)          |
| Architecture   | [ARCH-731](../../07_Architecture/03_IFRS9/ARCH-731_IFRS9_CALCULATION_ARCHITECTURE.md)         |

---

# 11. Knowledge Graph

```text
Financial Instruments
        │
        ▼
IFRS 9
        │
        ▼
Credit Risk
        │
        ▼
Stage Assessment
        │
        ▼
PD
LGD
EAD
        │
        ▼
Expected Credit Loss
        │
        ▼
Impairment
```

---

# 12. Learning Path

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

# 13. Summary

IFRS 9는 금융위기 이후 금융자산의 손상 인식을 개선하기 위해 도입된 국제회계기준이다.

기존 IAS 39의 발생손실(Incurred Loss) 모형을 예상신용손실(Expected Credit Loss) 모형으로 대체함으로써 미래 정보를 반영한 조기 손실 인식을 가능하게 하였다.

FRKP에서는 IFRS 9를 단순한 회계기준이 아니라 **Credit Risk → Stage Assessment → PD/LGD/EAD → Expected Credit Loss → Impairment**로 이어지는 통합 신용위험 관리 프레임워크로 정의한다.

---

# 14. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
