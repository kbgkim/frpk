# KB-241 — Counterparty Credit Risk

---

# Document Information

| Item            | Value                    |
| --------------- | ------------------------ |
| Document ID     | KB-241                   |
| Document Name   | Counterparty Credit Risk |
| Version         | 1.0.0                    |
| Status          | Draft                    |
| Category        | Knowledge Base           |
| Parent Document | RL-140                   |
| Created         | 2026-06-26               |
| Last Updated    | 2026-06-26               |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Knowledge Base](../README.md) > [KB-241 — Counterparty Credit Risk](KB-241_COUNTERPARTY_CREDIT_RISK.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Knowledge Base](../README.md) |
| ➡ Next | [KB-242](KB-242_SA_CCR_FRAMEWORK.md) |

### Related Documents

- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-242](KB-242_SA_CCR_FRAMEWORK.md)
- [AN-241](../../03_Analysis/04_SA_CCR/AN-241_WHY_CEM_FAILED.md)
- [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md)
- [FC-442](../../04_Formula_Catalog/04_SA_CCR/FC-442_POTENTIAL_FUTURE_EXPOSURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Counterparty Credit Risk(CCR, 거래상대방 신용위험)** 의 개념, 발생 원인, 일반 신용위험과의 차이, 주요 위험 특성 및 Basel III에서의 역할을 설명한다.

FRKP에서는 CCR을 **시장가격 변동에 따라 노출금액이 지속적으로 변화하는 금융계약에서 발생하는 동적 신용위험(Dynamic Credit Risk)** 으로 정의한다.

---

# 2. What is Counterparty Credit Risk?

Counterparty Credit Risk는 금융계약의 상대방이 계약 만기 이전에 의무를 이행하지 못하여 손실이 발생하는 위험이다.

일반적인 대출과 달리 CCR은 다음 특징을 가진다.

* 노출금액이 계속 변한다.
* 시장가격에 영향을 받는다.
* 양방향 계약(Bilateral Contract)이 많다.
* 담보와 상계(Netting)의 영향을 크게 받는다.

---

# 3. Traditional Credit Risk vs Counterparty Credit Risk

| Item        | Traditional Credit Risk | Counterparty Credit Risk |
| ----------- | ----------------------- | ------------------------ |
| 대표 상품       | 대출, 회사채                 | 스왑, 선도, 옵션, Repo         |
| 노출금액        | 대부분 고정                  | 시장가격에 따라 변동              |
| 부도 시점       | 차주 중심                   | 거래상대방 중심                 |
| 담보 영향       | 일부                      | 매우 큼                     |
| 상계(Netting) | 제한적                     | 매우 중요                    |
| 계산 방법       | IFRS 9 / IRB            | SA-CCR                   |

CCR의 핵심 차이는 **노출금액이 시간이 지남에 따라 변한다는 점**이다.

---

# 4. Why Does CCR Occur?

파생상품은 계약 체결 시점에는 계약가치가 거의 0일 수 있다.

그러나 시간이 지나면서 시장가격이 변하면 계약의 가치가 변한다.

```text
Contract Start

Market Value = 0

        │

Interest Rate Changes

FX Changes

Stock Price Changes

Commodity Price Changes

        │

        ▼

Positive Market Value

        │

Counterparty Default

        │

        ▼

Loss
```

이 과정에서 거래상대방이 부도나면 손실이 발생한다.

---

# 5. Dynamic Exposure

CCR에서는 노출금액이 계속 변한다.

```text
Time

T0 ───── T1 ───── T2 ───── T3

Exposure

10

40

25

70

15
```

대출과 달리 Exposure가 일정하지 않기 때문에 미래 노출을 추정해야 한다.

---

# 6. Sources of Counterparty Credit Risk

CCR은 다양한 금융상품에서 발생한다.

| Product            | CCR 발생 여부 |
| ------------------ | --------- |
| Interest Rate Swap | ✔         |
| Currency Swap      | ✔         |
| FX Forward         | ✔         |
| Commodity Swap     | ✔         |
| Options            | ✔         |
| Repo               | ✔         |
| Securities Lending | ✔         |
| Corporate Loan     | 일반 신용위험   |

---

# 7. Current Exposure vs Future Exposure

CCR은 현재 노출과 미래 노출을 모두 고려한다.

```text
Current Exposure

        │

        ▼

Potential Future Exposure

        │

        ▼

Total Counterparty Exposure
```

SA-CCR는 이 두 요소를 결합하여 Exposure at Default를 산출한다.

---

# 8. Netting

상계(Netting)는 여러 계약을 하나의 순노출(Net Exposure)로 계산하는 제도이다.

예를 들어

| 계약     |   가치 |
| ------ | ---: |
| Swap A | +100 |
| Swap B |  -80 |

상계가 가능하면 순노출은 20이다.

Netting은 CCR을 크게 감소시키는 요소이다.

---

# 9. Collateral

담보는 거래상대방 부도 시 손실을 줄인다.

대표적인 담보는 다음과 같다.

* 현금
* 국채
* 회사채
* 주식
* Initial Margin
* Variation Margin

담보는 Replacement Cost와 PFE 계산에 직접적인 영향을 준다.

---

# 10. Wrong-Way Risk

Wrong-Way Risk는 거래상대방의 신용상태가 악화될수록 익스포저도 함께 증가하는 현상이다.

```text
Counterparty Credit Quality ↓

Exposure ↑
```

예를 들어 에너지 회사와 원유 파생상품을 거래하는 경우, 원유 가격 급락과 회사의 부도 가능성이 동시에 증가할 수 있다.

---

# 11. Right-Way Risk

Right-Way Risk는 거래상대방의 신용상태가 악화될 때 익스포저가 감소하는 경우이다.

이는 Wrong-Way Risk와 반대의 특성을 가진다.

---

# 12. Relationship with SA-CCR

SA-CCR는 CCR을 정량화하기 위한 Basel III의 표준 접근법이다.

```text
Counterparty Credit Risk
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

# 13. Relationship with Other Frameworks

| Framework     | Relationship                   |
| ------------- | ------------------------------ |
| IFRS 9        | 신용손실 평가에 참고 가능한 Exposure 정보 제공 |
| Basel III IRB | SA-CCR 산출 EAD 활용               |
| CVA           | 거래상대방 신용가치조정의 입력               |
| FRTB          | 시장위험과 상호 보완 관계                 |

---

# 14. FRKP Knowledge Graph

```text
Financial Contract
        │
        ▼
Market Value
        │
        ▼
Exposure
        │
        ▼
Counterparty Credit Risk
        │
        ▼
Replacement Cost
        │
        ▼
Potential Future Exposure
        │
        ▼
Exposure at Default
```

---

# 15. Learning Path

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
        ▼
FC-441 Replacement Cost
        │
        ▼
FC-442 Potential Future Exposure
        │
        ▼
FC-443 Alpha
        │
        ▼
FC-444 SA-CCR EAD
        │
        ▼
IMP-441 SA-CCR Implementation
        │
        ▼
ARCH-741 SA-CCR Architecture
```

---

# 16. Summary

Counterparty Credit Risk는 시장가격 변동에 따라 노출금액이 지속적으로 변하는 금융계약에서 거래상대방의 부도로 인해 발생하는 신용위험이다.

일반적인 대출 신용위험과 달리 CCR은 미래 노출을 고려해야 하며, 담보, 상계(Netting), Initial Margin, Variation Margin, Wrong-Way Risk 등 다양한 요소가 위험 수준에 영향을 미친다.

FRKP에서는 CCR을 **동적인 노출금액(Dynamic Exposure)을 갖는 금융계약의 신용위험**으로 정의하며, SA-CCR는 이를 정량화하기 위한 표준 규제 프레임워크로 설명한다.

---

# 17. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
