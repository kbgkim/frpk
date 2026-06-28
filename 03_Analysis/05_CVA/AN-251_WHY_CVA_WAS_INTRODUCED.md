# AN-251 — Why Credit Valuation Adjustment (CVA) Was Introduced

---

# Document Information

| Item          | Value                                                |
| ------------- | ---------------------------------------------------- |
| Document ID   | AN-251                                               |
| Document Name | Why Credit Valuation Adjustment (CVA) Was Introduced |
| Version       | 1.0.0                                                |
| Status        | Active                                               |
| Category      | Analysis                                             |
| Parent Bundle | [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md)                                           |
| Created       | 2026-06-27                                           |
| Last Updated  | 2026-06-27                                           |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) > [Analysis](../README.md) > [AN-251 — Why Credit Valuation Adjustment (CVA) Was Introduced](AN-251_WHY_CVA_WAS_INTRODUCED.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-005](../../08_Bundles/BUNDLE-005_CVA_REVIEW.md) |
| ⬆ Parent Layer | [Analysis](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-150](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)
- [KB-251](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)
- [KB-252](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)
- [FC-451](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md)
- [FC-452](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 **Credit Valuation Adjustment(CVA)가 Basel III 규제체계에 도입된 배경과 필요성**을 분석한다.

CVA는 단순한 새로운 계산식이 아니라, 2007~2008년 글로벌 금융위기에서 드러난 거래상대방 신용위험 관리의 한계를 해결하기 위해 도입된 규제 프레임워크이다.

본 문서는 역사적 배경, 기존 접근법의 한계, 규제 변화 및 금융기관에 미친 영향을 중심으로 분석한다.

---

# 2. Executive Summary

금융위기 이전의 거래상대방 신용위험 관리에서는 **상대방의 실제 부도(Default)** 를 중심으로 위험을 평가하였다.

그러나 금융위기 과정에서 금융기관들은 거래상대방이 실제로 부도나지 않았음에도 불구하고 **신용스프레드(Credit Spread)의 급격한 확대**로 인해 대규모 평가손실(Mark-to-Market Loss)을 경험하였다.

이 경험은 거래상대방의 **부도 위험(Default Risk)** 뿐 아니라 **신용가치 변동(Credit Value Changes)** 자체도 자본규제 대상으로 관리해야 한다는 필요성을 제기하였다.

이에 따라 Basel III는 CVA와 CVA Capital Charge를 도입하였다.

---

# 3. Background

Basel II에서는 거래상대방 신용위험(CCR)을 관리하기 위해 주로 다음 요소를 고려하였다.

* Exposure at Default (EAD)
* Probability of Default (PD)
* Loss Given Default (LGD)

기본적인 사고방식은 다음과 같았다.

```text
Counterparty

↓

Default

↓

Loss

↓

Capital Requirement
```

즉, 손실은 거래상대방의 **실제 부도**가 발생할 때만 실현된다고 가정하였다.

---

# 4. What Happened During the Financial Crisis?

2007~2008년 글로벌 금융위기에서는 예상과 다른 현상이 나타났다.

많은 금융기관은 거래상대방이 부도나지 않았음에도 상당한 손실을 기록하였다.

원인은 다음과 같았다.

* CDS Spread 급등
* 신용등급 하락
* 시장 유동성 악화
* 파생상품 공정가치 하락

즉,

```text
Credit Spread Widening

↓

Derivative Value Declines

↓

Accounting Loss

↓

Capital Impact
```

라는 새로운 손실 경로가 확인되었다.

---

# 5. Default Was Not the Largest Source of Loss

금융위기 분석 결과, 거래상대방 신용위험 손실의 상당 부분은 **실제 부도(Default)** 보다 **신용스프레드 확대(Credit Spread Widening)** 에 의해 발생하였다.

이를 비교하면 다음과 같다.

| 구분          | Default Loss | Credit Spread Loss |
| ----------- | ------------ | ------------------ |
| 발생 시점       | 부도 발생 시      | 시장 신용도 악화 시        |
| 발생 빈도       | 상대적으로 낮음     | 상대적으로 높음           |
| 시장 영향       | 국지적          | 광범위                |
| 평가손실        | 제한적          | 매우 큼               |
| Basel II 반영 | 예            | 아니오                |

이러한 차이는 Basel II 규제의 중요한 공백으로 인식되었다.

---

# 6. Why Basel II Was Not Enough

Basel II는 다음과 같은 한계를 가지고 있었다.

### 1. Default-Centric View

거래상대방이 실제 부도날 경우만 손실을 고려하였다.

### 2. Mark-to-Market Risk Ignored

신용스프레드 변화로 인한 공정가치 변동을 충분히 반영하지 못하였다.

### 3. Dynamic Credit Quality Ignored

거래상대방의 신용도 변화가 실시간으로 가치에 미치는 영향을 자본규제에 반영하지 못하였다.

---

# 7. Basel III Response

Basel III는 이러한 문제를 해결하기 위해 CVA Framework를 도입하였다.

규제 변화는 다음과 같이 요약할 수 있다.

```text
Basel II

Counterparty Default

↓

Expected Loss

↓

Capital

────────────────────────────

Basel III

Counterparty Credit Quality

↓

Fair Value Change

↓

Credit Valuation Adjustment

↓

CVA Capital Charge
```

---

# 8. Why CVA Matters

CVA는 거래상대방의 **신용가치 변화**를 공정가치에 반영한다.

이를 통해 금융기관은 다음 위험을 보다 현실적으로 관리할 수 있게 되었다.

* 신용등급 하락
* CDS Spread 확대
* 시장 신뢰도 악화
* 거래상대방 위험 증가

즉,

```text
Credit Quality

↓

Market Value

↓

Accounting Value

↓

Regulatory Capital
```

라는 연결 구조를 구축하였다.

---

# 9. Relationship with SA-CCR

SA-CCR와 CVA는 서로 다른 역할을 수행한다.

```text
Trade Portfolio

↓

SA-CCR

↓

Exposure Profile (EAD)

↓

CVA

↓

Fair Value Adjustment

↓

CVA Capital Charge
```

SA-CCR는 **위험 노출(Exposure)** 을 계산하고, CVA는 그 노출이 **신용가치 변동에 의해 얼마나 영향을 받는지**를 평가한다.

---

# 10. Regulatory Impact

CVA의 도입은 금융기관의 리스크 관리 체계를 크게 변화시켰다.

주요 영향은 다음과 같다.

* 거래상대방 신용위험의 시장가치 반영
* 공정가치 평가의 현실성 향상
* 자본규제의 위험 민감도 증가
* CVA Desk 및 CVA Hedging 체계 확산
* CDS 및 신용파생상품 활용 증가

---

# 11. Lessons Learned

글로벌 금융위기는 다음 교훈을 남겼다.

1. 거래상대방이 부도나지 않아도 큰 손실이 발생할 수 있다.
2. 신용스프레드 변화는 자본에 직접적인 영향을 준다.
3. 공정가치는 신용위험을 반영해야 한다.
4. 거래상대방 신용위험은 Default Risk와 Credit Migration Risk를 함께 관리해야 한다.
5. 자본규제는 실제 시장가치 변동을 반영해야 한다.

---

# 12. Cross References

| Category     | Document                                  |
| ------------ | ----------------------------------------- |
| Reference    | [RL-150_CVA_OVERVIEW](../../01_Reference_Library/05_CVA/RL-150_CVA_OVERVIEW.md)                       |
| Knowledge    | [KB-251_CREDIT_VALUATION_ADJUSTMENT](../../02_Knowledge_Base/05_CVA/KB-251_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Knowledge    | [KB-252_CVA_FRAMEWORK](../../02_Knowledge_Base/05_CVA/KB-252_CVA_FRAMEWORK.md)                      |
| Formula      | [FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE](../../04_Formula_Catalog/05_CVA/FC-451_DEFAULT_PROBABILITY_TERM_STRUCTURE.md) |
| Formula      | [FC-452_EXPECTED_EXPOSURE](../../04_Formula_Catalog/05_CVA/FC-452_EXPECTED_EXPOSURE.md)                  |
| Formula      | [FC-453_CREDIT_VALUATION_ADJUSTMENT](../../04_Formula_Catalog/05_CVA/FC-453_CREDIT_VALUATION_ADJUSTMENT.md)        |
| Formula      | [FC-454_CVA_CAPITAL_CHARGE](../../04_Formula_Catalog/05_CVA/FC-454_CVA_CAPITAL_CHARGE.md)                 |
| Architecture | [ARCH-751_CVA_ARCHITECTURE](../../07_Architecture/05_CVA/ARCH-751_CVA_ARCHITECTURE.md)                 |

---

# 13. Summary

CVA는 단순한 가치조정 기법이 아니라, 글로벌 금융위기에서 드러난 거래상대방 신용위험 관리의 한계를 보완하기 위해 Basel III에 도입된 핵심 규제 개념이다.

Basel II가 **실제 부도(Default)** 에 초점을 맞추었다면, Basel III의 CVA는 **신용가치(Credit Quality)의 변화가 파생상품 공정가치와 규제자본에 미치는 영향**까지 관리 대상으로 확장하였다.

이로써 거래상대방 신용위험은 **부도 위험(Default Risk)** 과 **신용스프레드 위험(Credit Spread Risk)** 을 함께 고려하는 보다 현실적인 규제 체계로 발전하게 되었다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
