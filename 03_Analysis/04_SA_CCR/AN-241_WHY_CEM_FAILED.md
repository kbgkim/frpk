# AN-241 — Why Current Exposure Method (CEM) Failed

---

# Document Information

| Item            | Value                                    |
| --------------- | ---------------------------------------- |
| Document ID     | AN-241                                   |
| Document Name   | Why Current Exposure Method (CEM) Failed |
| Version         | 1.0.0                                    |
| Status          | Draft                                    |
| Category        | Analysis                                 |
| Parent Document | RL-140                                   |
| Created         | 2026-06-26                               |
| Last Updated    | 2026-06-26                               |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) > [Analysis](../README.md) > [AN-241 — Why Current Exposure Method (CEM) Failed](AN-241_WHY_CEM_FAILED.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-004](../../08_Bundles/BUNDLE-004_SA_CCR_REVIEW.md) |
| ⬆ Parent Layer | [Analysis](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-140](../../01_Reference_Library/04_SA_CCR/RL-140_SA_CCR_OVERVIEW.md)
- [KB-241](../../02_Knowledge_Base/04_SA_CCR/KB-241_COUNTERPARTY_CREDIT_RISK.md)
- [KB-242](../../02_Knowledge_Base/04_SA_CCR/KB-242_SA_CCR_FRAMEWORK.md)
- [FC-441](../../04_Formula_Catalog/04_SA_CCR/FC-441_REPLACEMENT_COST.md)
- [FC-442](../../04_Formula_Catalog/04_SA_CCR/FC-442_POTENTIAL_FUTURE_EXPOSURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Basel II에서 사용되던 **Current Exposure Method(CEM)** 의 구조와 한계를 분석하고, Basel III에서 **SA-CCR(Standardised Approach for Counterparty Credit Risk)** 가 도입된 배경을 설명한다.

본 문서는 계산 공식을 설명하는 것이 아니라 **규제 변화의 이유와 위험 관리 관점의 개선 사항**을 분석하는 것을 목적으로 한다.

---

# 2. Background

Current Exposure Method(CEM)는 거래상대방 신용위험을 측정하기 위한 초기 규제 접근법이었다.

기본 개념은 다음과 같다.

```text
Current Exposure

+

Add-on

↓

Exposure
```

현재 시점의 익스포저(Current Exposure)에 미래 잠재 익스포저(Add-on)를 더하여 총 노출을 계산하였다.

이 방식은 구현이 단순하고 계산이 쉬웠지만, 금융시장의 발전과 파생상품의 복잡성을 충분히 반영하지 못했다.

---

# 3. Why CEM Was Introduced

CEM이 도입될 당시에는 다음과 같은 장점이 있었다.

* 계산이 단순하다.
* 규제 적용이 쉽다.
* 파생상품 시장 규모가 상대적으로 작았다.
* 시스템 구현 부담이 낮았다.

그러나 금융위기 이후 이러한 장점보다 구조적인 한계가 더 크게 드러났다.

---

# 4. Fundamental Limitations of CEM

CEM의 핵심 문제는 **실제 위험을 충분히 반영하지 못한다는 점**이다.

대표적인 한계는 다음과 같다.

* 위험 민감도 부족
* 상품 특성 반영 부족
* 담보 효과 과소 반영
* 상계(Netting) 효과 제한
* 시장 변동성 반영 부족
* 미래 익스포저 추정 단순화

---

# 5. Lack of Risk Sensitivity

CEM은 동일한 상품군에 대해 고정된 Add-on 계수를 적용하였다.

```text
Derivative Contract
        │
        ▼
Fixed Add-on
```

이 방식은 계약의 실제 위험 수준과 관계없이 동일한 규제 계수를 적용하기 때문에 위험 민감도가 낮았다.

---

# 6. Limited Recognition of Netting

실제 금융기관은 ISDA Master Agreement 등에 따라 여러 계약을 상계(Netting)한다.

예를 들어,

| 계약     | 시장가치 |
| ------ | ---: |
| Swap A | +120 |
| Swap B | -100 |

순노출(Net Exposure)은 20이지만, CEM은 상계 효과를 충분히 반영하지 못했다.

결과적으로 실제보다 큰 노출액이 계산되는 경우가 많았다.

---

# 7. Insufficient Treatment of Collateral

금융기관은 Variation Margin과 Initial Margin을 통해 거래상대방 위험을 지속적으로 관리한다.

그러나 CEM은 이러한 담보 구조를 제한적으로만 반영하였다.

따라서 담보가 충분히 제공되는 거래에서도 위험이 과대평가될 수 있었다.

---

# 8. Poor Representation of Future Exposure

미래 익스포저는 다음 요소에 따라 달라진다.

* 시장 변동성
* 계약 만기
* 자산군
* 옵션 특성
* 상관관계

그러나 CEM은 단순한 Add-on 방식만 사용하였다.

```text
Current Exposure

+

Fixed Add-on

↓

Future Exposure
```

실제 시장의 복잡성을 충분히 반영하기 어려웠다.

---

# 9. Lessons from the Global Financial Crisis

2007~2009년 글로벌 금융위기는 거래상대방 신용위험 관리의 중요성을 크게 부각시켰다.

주요 교훈은 다음과 같다.

* 거래상대방 부도는 시장가격 변동과 동시에 발생할 수 있다.
* 담보 관리가 자본 산정에 큰 영향을 준다.
* 단순한 고정 계수 방식으로는 위험을 설명하기 어렵다.
* 파생상품 포트폴리오 전체를 고려한 접근이 필요하다.

---

# 10. Why Basel III Introduced SA-CCR

Basel III는 다음 목표를 가지고 SA-CCR를 도입하였다.

| 개선 목표     | SA-CCR 접근                         |
| --------- | --------------------------------- |
| 위험 민감도 향상 | Replacement Cost + PFE            |
| 담보 반영     | Variation Margin / Initial Margin |
| 상계 반영     | Netting Set 기반 계산                 |
| 상품별 차별화   | 자산군별 규칙                           |
| 미래 노출 개선  | PFE 모델                            |

---

# 11. Conceptual Comparison

```text
Current Exposure Method

Current Exposure

+

Fixed Add-on

↓

Exposure
```

↓

```text
SA-CCR

Replacement Cost

+

Potential Future Exposure

↓

Alpha

↓

Exposure at Default
```

SA-CCR는 계산 구조 자체를 재설계하였다.

---

# 12. Benefits of SA-CCR

SA-CCR는 다음과 같은 개선을 제공한다.

* 실제 시장 위험 반영
* 담보 효과 반영
* Netting 효과 반영
* 자산군별 차별화
* 규제 일관성 향상
* Basel III와의 정합성 확보

---

# 13. Relationship with Other Frameworks

| Framework     | Relationship                   |
| ------------- | ------------------------------ |
| Basel III IRB | SA-CCR EAD를 규제자본 계산에 활용        |
| CVA           | SA-CCR 노출액을 기반으로 신용가치조정 수행     |
| IFRS 9        | 일부 Exposure 정보가 신용손실 분석에 활용 가능 |
| FRTB          | 시장위험 측정과 상호 보완                 |

---

# 14. Analysis Conclusion

CEM이 실패한 이유는 계산이 틀렸기 때문이 아니라 **시장 현실을 충분히 반영하지 못했기 때문**이다.

금융시장의 복잡성이 증가하면서 다음 요소를 함께 고려할 필요가 생겼다.

* 시장가치 변동
* 미래 익스포저
* 담보
* 상계
* 자산군 특성
* 규제 일관성

이러한 요구를 충족하기 위해 SA-CCR가 도입되었다.

---

# 15. Knowledge Graph

```text
Current Exposure Method
        │
        ▼
Risk Sensitivity 부족
        │
        ▼
Global Financial Crisis
        │
        ▼
Basel III Reform
        │
        ▼
SA-CCR
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

# 17. Summary

Current Exposure Method(CEM)는 거래상대방 신용위험을 단순하고 일관된 방식으로 측정하기 위해 도입되었지만, 금융시장과 파생상품 구조가 복잡해지면서 위험 민감도, 담보 반영, 상계 효과, 미래 익스포저 추정 측면에서 한계를 드러냈다.

Basel III는 이러한 한계를 해결하기 위해 SA-CCR를 도입하였으며, Replacement Cost, Potential Future Exposure, Alpha를 기반으로 보다 현실적인 Exposure at Default를 산출하도록 규제 체계를 개편하였다.

FRKP에서는 CEM의 실패를 **계산 방식의 오류가 아니라 금융시장의 발전과 규제 요구 변화에 따라 새로운 위험 측정 체계가 필요해진 결과**로 해석한다.

---

# 18. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
