# AN-221 — Why VaR Failed

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Bundle-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) > [Analysis](../README.md) > [AN-221 — Why VaR Failed](AN-221_WHY_VAR_FAILED.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | [BUNDLE-002](../../08_Bundles/BUNDLE-002_FRTB_REVIEW.md) |
| ⬆ Parent Layer | [Analysis](../README.md) |
| ➡ Next | None |

### Related Documents

- [RL-120](../../01_Reference_Library/02_FRTB/RL-120_FRTB_OVERVIEW.md)
- [KB-221](../../02_Knowledge_Base/02_FRTB/KB-221_MARKET_RISK_OVERVIEW.md)
- [KB-222](../../02_Knowledge_Base/02_FRTB/KB-222_FRTB_FRAMEWORK.md)
- [FC-421](../../04_Formula_Catalog/02_FRTB/FC-421_EXPECTED_SHORTFALL.md)
- [FC-422](../../04_Formula_Catalog/02_FRTB/FC-422_LIQUIDITY_HORIZON.md)
<!-- FRKP-NAV-END -->

---

## Document Information

| Item            | Value          |
| --------------- | -------------- |
| Document ID     | AN-221         |
| Document Name   | Why VaR Failed |
| Version         | 1.0.0          |
| Status          | Draft          |
| Owner           | Project Lead   |
| Category        | Analysis       |
| Parent Document | KB-221         |
| Created         | 2026-06-26     |
| Last Updated    | 2026-06-26     |

---

# 1. Purpose

본 문서는 Value at Risk(VaR)의 한계를 분석하고, Basel III FRTB가 Expected Shortfall(ES)을 채택한 배경을 설명한다.

Reference Library가 규제를 설명하고, Knowledge Base가 개념을 설명한다면, Analysis는 **왜 이러한 변화가 필요했는지를 분석**하는 역할을 수행한다.

---

# 2. The Success of VaR

1990년대 이후 VaR는 시장위험 관리의 표준 지표가 되었다.

VaR는 다음과 같은 장점을 가지고 있었다.

* 계산이 비교적 단순하다.
* 하나의 숫자로 위험을 표현할 수 있다.
* 다양한 자산군에 적용 가능하다.
* 규제와 내부 위험관리 모두에서 활용 가능하다.

예를 들어,

> "99% 신뢰수준에서 하루 VaR가 10억 원"

이라는 의미는

> **99%의 경우 하루 손실이 10억 원을 초과하지 않는다.**

는 것이다.

---

# 3. The Fundamental Limitation of VaR

VaR는 **손실이 발생하는 경계값(Threshold)** 만 알려준다.

하지만 경계값을 넘어선 이후의 손실 규모는 설명하지 못한다.

예를 들어 두 포트폴리오가 있다고 가정한다.

| Portfolio | 99% VaR | 최악의 손실 |
| --------- | ------: | -----: |
| A         |     100 |    120 |
| B         |     100 | 10,000 |

두 포트폴리오는 VaR가 동일하다.

그러나 실제 위험은 완전히 다르다.

VaR는 이러한 차이를 표현하지 못한다.

---

# 4. Tail Risk Problem

```text
Loss Distribution

                Tail
                  │
                  ▼

────────────┬───────────────►

          VaR

          ▲

VaR는 여기까지만 본다.

Tail은 보지 않는다.
```

VaR는 **손실분포의 꼬리(Tail)** 를 무시한다.

하지만 금융위기의 대부분은 바로 이 Tail에서 발생한다.

---

# 5. Financial Crisis Lessons

2007~2008년 금융위기에서 나타난 특징은 다음과 같다.

* 시장 유동성 급감
* 자산 간 상관관계 급증
* 극단적인 가격 변동
* 대규모 동시 손실

평상시에는 거의 발생하지 않던 사건이 동시에 발생하였다.

VaR는 이러한 상황을 충분히 반영하지 못했다.

---

# 6. Why Expected Shortfall?

Expected Shortfall는

> **VaR를 초과한 손실들의 평균**

을 계산한다.

수식으로 표현하면

[
ES_\alpha
=========

E[L \mid L > VaR_\alpha]
]

즉,

VaR 이후의 손실까지 모두 고려한다.

---

# 7. Comparison: VaR vs Expected Shortfall

| Item           | VaR     | Expected Shortfall |
| -------------- | ------- | ------------------ |
| 측정 대상          | 손실 경계   | 꼬리 손실 평균           |
| Tail 반영        | ✗       | ✓                  |
| 위험 민감도         | 낮음      | 높음                 |
| 극단 상황          | 과소평가 가능 | 상대적으로 잘 반영         |
| Basel III FRTB | 사용하지 않음 | 사용                 |

---

# 8. Mathematical Perspective

VaR는 **분위수(Quantile)** 를 계산한다.

```text
99%

↓

VaR
```

Expected Shortfall는

```text
99%

↓

VaR 초과 영역

↓

평균
```

즉,

VaR는 한 점(Point)을 계산하지만,

Expected Shortfall는 **영역(Area)** 을 계산한다.

---

# 9. Business Perspective

은행이 실제로 궁금한 것은

> "99%까지 얼마 손실이 나는가?"

보다

> **"정말 위기가 오면 얼마나 크게 손실이 나는가?"**

이다.

Expected Shortfall는 두 번째 질문에 답한다.

---

# 10. System Perspective

Risk Engine에서는

VaR

```text
Scenario

↓

P&L

↓

99% Quantile
```

Expected Shortfall

```text
Scenario

↓

P&L

↓

Tail Selection

↓

Tail Average
```

Expected Shortfall는 Tail 데이터를 추가로 처리해야 하므로 계산량이 증가한다.

---

# 11. Why Liquidity Horizon Was Added

금융위기에서는

> 자산을 즉시 매도할 수 없다.

이를 반영하기 위해 FRTB는

**Liquidity Horizon** 을 도입하였다.

즉,

Risk Factor마다

* 10일
* 20일
* 40일
* 60일
* 120일

의 청산기간을 적용한다.

---

# 12. Lessons for FRKP

FRKP에서는 VaR를 폐기하지 않는다.

그 이유는 다음과 같다.

* 내부 위험관리에서는 여전히 활용된다.
* Historical VaR는 Backtesting에 사용된다.
* Monte Carlo VaR는 모델 검증에 활용된다.

다만 규제자본 계산은 Expected Shortfall를 중심으로 구성한다.

---

# 13. Design Implications

Risk Engine 설계 시 고려사항

* VaR Engine과 ES Engine을 분리한다.
* Tail Selection 알고리즘을 독립 모듈로 구현한다.
* Liquidity Horizon을 Risk Factor 단위로 적용한다.
* Expected Shortfall는 병렬 계산이 가능하도록 설계한다.

---

# 14. Knowledge Graph

```text
VaR
      │
      ▼
Tail Risk
      │
      ▼
Expected Shortfall
      │
      ▼
Liquidity Horizon
      │
      ▼
FRTB
      │
      ▼
Market RWA
```

---

# 15. Related Documents

## Reference

* RL-120 — FRTB Overview

## Knowledge

* KB-221 — Market Risk Overview
* KB-222 — FRTB Framework

## Formula

* FC-421 — Expected Shortfall
* FC-422 — Liquidity Horizon

## Architecture

* ARCH-721 — FRTB Calculation Architecture

---

# 16. Summary

VaR는 시장위험 관리의 발전에 큰 기여를 했지만, 극단적 손실(Tail Risk)을 충분히 설명하지 못하는 구조적 한계를 가지고 있다.

Basel III FRTB는 이러한 한계를 보완하기 위해 Expected Shortfall를 도입하였으며, Liquidity Horizon과 Risk Factor 기반 접근을 추가하여 실제 시장위험을 더욱 현실적으로 반영하도록 개선하였다.

FRKP에서는 이러한 변화를 단순한 규제 변경으로 보지 않고, **위험을 바라보는 관점이 '경계값(Threshold)'에서 '분포(Distribution)'로 확장된 패러다임 전환**으로 정의한다.

---

# 17. Revision History

| Version | Date       | Description   |
| ------- | ---------- | ------------- |
| 1.0.0   | 2026-06-26 | Initial Draft |
