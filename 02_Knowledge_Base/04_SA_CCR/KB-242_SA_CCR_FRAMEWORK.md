# KB-242 — SA-CCR Framework

---

# Document Information

| Item            | Value            |
| --------------- | ---------------- |
| Document ID     | KB-242           |
| Document Name   | SA-CCR Framework |
| Version         | 1.0.0            |
| Status          | Draft            |
| Category        | Knowledge Base   |
| Parent Document | RL-140           |
| Created         | 2026-06-26       |
| Last Updated    | 2026-06-26       |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Knowledge Base](../README.md) > [KB-242 — SA-CCR Framework](KB-242_SA_CCR_FRAMEWORK.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [KB-241](KB-241_COUNTERPARTY_CREDIT_RISK.md) |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](KB-241_COUNTERPARTY_CREDIT_RISK.md)
- [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)
- [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md)
- [FC-442](../../04_Formula_Catalog/04_SA_CCR/FC-442_POTENTIAL_FUTURE_EXPOSURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel III에서 정의한 **SA-CCR(Standardised Approach for Counterparty Credit Risk)** 의 전체 계산 프레임워크를 설명한다.

SA-CCR는 거래상대방 신용위험(Counterparty Credit Risk)을 정량화하기 위한 표준 접근법이며, 파생상품 및 증권금융거래에서 **부도 시 노출금액(Exposure at Default, EAD)** 을 산출하는 것을 목적으로 한다.

FRKP에서는 SA-CCR를 **Replacement Cost, Potential Future Exposure, Alpha를 결합하여 규제 목적의 EAD를 산출하는 통합 프레임워크**로 정의한다.

---

# 2. Framework Overview

SA-CCR의 전체 계산 흐름은 다음과 같다.

```text
Derivative Contract
        │
        ▼
Trade Information
        │
        ▼
Netting Set
        │
        ▼
Collateral Assessment
        │
        ▼
Replacement Cost (RC)
        │
        ▼
Potential Future Exposure (PFE)
        │
        ▼
Alpha
        │
        ▼
Exposure at Default (EAD)
```

각 단계는 독립적인 계산 계약을 가지며 최종적으로 규제자본 계산에 사용되는 EAD를 산출한다.

---

# 3. Scope of SA-CCR

SA-CCR는 다음 거래에 적용된다.

| Product                                | Included    |
| -------------------------------------- | ----------- |
| Interest Rate Derivatives              | ✔           |
| Foreign Exchange Derivatives           | ✔           |
| Credit Derivatives                     | ✔           |
| Equity Derivatives                     | ✔           |
| Commodity Derivatives                  | ✔           |
| Securities Financing Transactions(SFT) | 일부 별도 규정 적용 |

---

# 4. Core Components

SA-CCR는 네 개의 핵심 요소로 구성된다.

| Component                       | Purpose      |
| ------------------------------- | ------------ |
| Replacement Cost (RC)           | 현재 노출액 산정    |
| Potential Future Exposure (PFE) | 미래 잠재 노출액 추정 |
| Alpha                           | 규제 보정계수 적용   |
| Exposure at Default (EAD)       | 최종 규제 노출액 산출 |

---

# 5. Replacement Cost

Replacement Cost는 거래를 현재 시점에서 청산하거나 동일 조건으로 재체결할 때 발생하는 현재 노출액이다.

계산 시 다음 요소를 고려한다.

* 현재 시장가치(Mark-to-Market)
* Variation Margin
* Initial Margin
* 담보 인정 규칙
* Netting Agreement

Replacement Cost는 **현재 시점의 경제적 노출(Current Exposure)** 을 나타낸다.

---

# 6. Potential Future Exposure

Potential Future Exposure(PFE)는 계약 만기까지 시장가격이 변동하면서 발생할 수 있는 미래 노출액을 추정한다.

PFE는 다음 요소에 영향을 받는다.

* 자산군(Asset Class)
* 잔존만기(Maturity)
* 노셔널(Notional)
* 감독계수(Supervisory Factor)
* 상계(Netting)

PFE는 **미래 시점의 잠재적 위험**을 나타낸다.

---

# 7. Alpha

Alpha는 Basel III에서 정의한 규제 보정계수이다.

SA-CCR에서는 Replacement Cost와 Potential Future Exposure를 결합한 값에 Alpha를 적용하여 보수적인 EAD를 산출한다.

Alpha는 다음 목적을 가진다.

* 모델 불확실성 보완
* 규제 보수성 확보
* 시스템 간 일관성 유지

---

# 8. Exposure at Default

Exposure at Default(EAD)는 SA-CCR의 최종 산출물이다.

개념적으로 다음과 같이 표현할 수 있다.

```text
Replacement Cost
        │
        ├─────────────┐
        ▼             ▼
Potential Future Exposure
        │
        ▼
Alpha
        │
        ▼
Exposure at Default
```

EAD는 Basel III 신용위험 자본 계산의 입력값으로 사용된다.

---

# 9. Netting Framework

SA-CCR는 Netting Agreement를 핵심 요소로 반영한다.

```text
Trade A

Trade B

Trade C

        │

        ▼

Netting Set

        │

        ▼

Replacement Cost
```

법적 상계가 가능한 계약은 개별 거래가 아니라 **Netting Set 단위**로 평가한다.

---

# 10. Collateral Framework

담보는 현재 노출과 미래 노출 모두에 영향을 미친다.

대표적인 담보 요소는 다음과 같다.

* Cash Collateral
* Securities Collateral
* Variation Margin
* Initial Margin

담보는 Replacement Cost 계산에서 직접 반영되며, PFE에도 간접적인 영향을 준다.

---

# 11. Calculation Pipeline

```text
Trade Capture
        │
        ▼
Trade Validation
        │
        ▼
Netting Set Construction
        │
        ▼
Collateral Processing
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Alpha
        │
        ▼
Exposure at Default
```

이 파이프라인은 Formula와 Implementation 문서의 기반이 된다.

---

# 12. Relationship with Basel III

```text
Basel III
      │
      ▼
Counterparty Credit Risk
      │
      ▼
SA-CCR
      │
      ▼
Exposure at Default
      │
      ▼
Credit RWA
      │
      ▼
Regulatory Capital
```

SA-CCR는 거래상대방 신용위험을 규제자본 계산으로 연결하는 핵심 단계이다.

---

# 13. Relationship with Other FRKP Bundles

| Bundle     | Relationship                |
| ---------- | --------------------------- |
| Bundle-001 | Basel III Foundation        |
| Bundle-002 | 시장위험과 병행하여 파생상품 위험 관리       |
| Bundle-003 | IFRS 9와 함께 신용위험 영역 구성       |
| Bundle-005 | SA-CCR EAD를 IRB 규제자본 계산에 활용 |
| Bundle-006 | SA-CCR EAD를 CVA 계산의 입력으로 활용 |

---

# 14. Formula Roadmap

이 Framework를 기반으로 다음 Formula Catalog를 작성한다.

| Document | Purpose                    |
| -------- | -------------------------- |
| FC-441   | Replacement Cost           |
| FC-442   | Potential Future Exposure  |
| FC-443   | Alpha                      |
| FC-444   | SA-CCR Exposure at Default |

---

# 15. Knowledge Graph

```text
Derivative Contract
        │
        ▼
Counterparty Credit Risk
        │
        ▼
Netting
        │
        ▼
Collateral
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Alpha
        │
        ▼
Exposure at Default
```

---

# 16. Learning Path

```text
RL-140 SA-CCR Overview
        │
        ▼
KB-241 Counterparty Credit Risk
        │
        ▼
AN-241 Why CEM Failed
        │
        ▼
KB-242 SA-CCR Framework
        │
        ├── FC-441 Replacement Cost
        ├── FC-442 Potential Future Exposure
        ├── FC-443 Alpha
        └── FC-444 SA-CCR EAD
                 │
                 ▼
IMP-441 SA-CCR Implementation
                 │
                 ▼
ARCH-741 SA-CCR Architecture
```

---

# 17. Summary

SA-CCR는 Basel III에서 거래상대방 신용위험을 측정하기 위해 도입된 표준 접근법이다.

이 프레임워크는 현재 노출을 나타내는 Replacement Cost와 미래 잠재 노출을 나타내는 Potential Future Exposure를 결합하고, 규제 보정계수인 Alpha를 적용하여 최종 Exposure at Default를 산출한다.

FRKP에서는 SA-CCR를 **Trade → Netting → Collateral → Replacement Cost → Potential Future Exposure → Alpha → Exposure at Default**로 이어지는 계층형 계산 프레임워크로 정의하며, 이후 Formula, Implementation, Architecture 문서에서 각 단계의 계산 계약과 시스템 구조를 상세히 설명한다.

---

# 18. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
