# FRKP-TERM-100 — Master Glossary

---

# Document Information

| Item            | Value                          |
| --------------- | ------------------------------ |
| Document ID     | FRKP-TERM-100                  |
| Document Name   | Master Glossary                |
| Version         | 1.0.0                          |
| Status          | Active                         |
| Category        | Governance / Master Dictionary |
| Parent Standard | [FRKP-TERM-001](../FRKP-TERM-001_GLOSSARY_STANDARD.md)                  |
| Created         | 2026-06-26                     |
| Last Updated    | 2026-06-26                     |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에서 사용하는 모든 핵심 용어의 **대표 정의(Preferred Definition)** 를 관리하는 Master Glossary이다.

본 문서는

* 프로젝트 전체의 단일 용어 기준(Single Source of Truth)
* 도메인별 Glossary의 상위 인덱스
* 문서 간 의미 일관성 유지

를 목적으로 한다.

세부 설명은 도메인별 Glossary에서 관리한다.

---

# 2. Scope

본 문서는 다음 영역을 포함한다.

* Basel III
* FRTB
* IFRS 9
* SA-CCR
* CVA
* Liquidity Risk
* Operational Risk
* Financial Mathematics
* Portfolio Theory
* Artificial Intelligence

---

# 3. Glossary Architecture

```text
Master Glossary
        │
        ├── Credit Risk
        ├── Market Risk
        ├── Liquidity
        ├── Capital
        ├── Mathematics
        ├── Statistics
        ├── AI
        └── Technology
```

---

# 4. Definition Policy

모든 용어는 다음 원칙을 따른다.

* One Concept
* One Preferred Definition
* One Preferred English Term
* One Preferred Abbreviation

---

# 5. Master Glossary Index

| Domain      | Document      |
| ----------- | ------------- |
| Credit Risk | FRKP-TERM-101 |
| Market Risk | FRKP-TERM-201 |
| Liquidity   | FRKP-TERM-301 |
| Mathematics | FRKP-TERM-401 |
| AI          | FRKP-TERM-501 |

---

# 6. Core Financial Terms

## Capital

| Item           | Value                       |
| -------------- | --------------------------- |
| Preferred Term | Capital                     |
| Korean         | 자본                          |
| Definition     | 금융기관이 손실을 흡수하기 위해 보유하는 자기자본 |
| Category       | Capital                     |

---

## Regulatory Capital

| Item           | Value               |
| -------------- | ------------------- |
| Preferred Term | Regulatory Capital  |
| Korean         | 규제자본                |
| Definition     | 규제기관 기준에 따라 인정되는 자본 |
| Category       | Basel III           |

---

## Risk

| Item           | Value              |
| -------------- | ------------------ |
| Preferred Term | Risk               |
| Korean         | 위험                 |
| Definition     | 미래 결과가 기대와 달라질 가능성 |
| Category       | Common             |

---

## Exposure

| Item           | Value                 |
| -------------- | --------------------- |
| Preferred Term | Exposure              |
| Korean         | 익스포저                  |
| Definition     | 특정 위험요인에 노출된 금액 또는 가치 |
| Category       | Common                |

---

# 7. Credit Risk Terms

| Preferred                 | Abbreviation | Definition |
| ------------------------- | ------------ | ---------- |
| Probability of Default    | PD           | 부도확률       |
| Loss Given Default        | LGD          | 부도손실률      |
| Exposure at Default       | EAD          | 부도시익스포저    |
| Expected Credit Loss      | ECL          | 기대신용손실     |
| Counterparty Credit Risk  | CCR          | 거래상대방 신용위험 |
| Replacement Cost          | RC           | 현재 경제적 노출  |
| Potential Future Exposure | PFE          | 미래 잠재 노출   |

---

# 8. Market Risk Terms

| Preferred          | Abbreviation | Definition |
| ------------------ | ------------ | ---------- |
| Value at Risk      | VaR          | 위험가치       |
| Expected Shortfall | ES           | 기대손실       |
| Delta              | Δ            | 1차 민감도     |
| Gamma              | Γ            | 2차 민감도     |
| Vega               | ν            | 변동성 민감도    |
| Curvature          | -            | 곡률 위험      |

---

# 9. Capital Terms

| Preferred            | Abbreviation | Definition  |
| -------------------- | ------------ | ----------- |
| Risk Weighted Assets | RWA          | 위험가중자산      |
| Common Equity Tier 1 | CET1         | 기본자본        |
| Tier 1 Capital       | Tier1        | 기본자본(Tier1) |
| Total Capital Ratio  | CAR          | BIS 자기자본비율  |

---

# 10. Liquidity Terms

| Preferred                  | Abbreviation | Definition |
| -------------------------- | ------------ | ---------- |
| Liquidity Coverage Ratio   | LCR          | 유동성커버리지비율  |
| Net Stable Funding Ratio   | NSFR         | 순안정자금조달비율  |
| High Quality Liquid Assets | HQLA         | 고유동성자산     |

---

# 11. Mathematical Terms

| Preferred                     | Definition |
| ----------------------------- | ---------- |
| Matrix                        | 행렬         |
| Vector                        | 벡터         |
| Eigenvalue                    | 고유값        |
| Eigenvector                   | 고유벡터       |
| Covariance                    | 공분산        |
| Correlation                   | 상관계수       |
| Quadratic Form                | 이차형식       |
| Positive Semi-definite Matrix | 양의 준정부호 행렬 |

---

# 12. Statistics Terms

| Preferred          | Definition |
| ------------------ | ---------- |
| Mean               | 평균         |
| Variance           | 분산         |
| Standard Deviation | 표준편차       |
| Skewness           | 왜도         |
| Kurtosis           | 첨도         |

---

# 13. AI Terms

| Preferred            | Definition |
| -------------------- | ---------- |
| Embedding            | 임베딩        |
| Attention            | 어텐션        |
| Transformer          | 트랜스포머      |
| Diffusion Model      | 디퓨전 모델     |
| Large Language Model | 대규모 언어모델   |

---

# 14. Cross Reference

```text
FRKP-TERM-100
        │
        ├── FRKP-TERM-101 Credit Risk
        ├── FRKP-TERM-201 Market Risk
        ├── FRKP-TERM-301 Liquidity
        ├── FRKP-TERM-401 Mathematics
        └── FRKP-TERM-501 AI
```

---

# 15. Governance Rules

Master Glossary는

* 대표 정의만 관리한다.
* 세부 설명은 도메인 Glossary에서 관리한다.
* 중복 정의를 허용하지 않는다.
* 모든 문서는 Master Glossary를 우선 참조한다.

---

# 16. Future Expansion

향후 다음 용어집을 작성한다.

| Document      | Scope                   |
| ------------- | ----------------------- |
| FRKP-TERM-101 | Credit Risk             |
| FRKP-TERM-201 | Market Risk             |
| FRKP-TERM-301 | Liquidity               |
| FRKP-TERM-401 | Mathematics             |
| FRKP-TERM-501 | Artificial Intelligence |

---

# 17. Summary

Master Glossary는 FRKP 전체에서 사용하는 핵심 용어의 대표 정의를 관리하는 중앙 용어 사전이다.

모든 문서는 본 문서를 기준으로 용어를 사용하며, 도메인별 Glossary는 각 용어의 상세 설명과 규제적 맥락을 제공한다. 이를 통해 프로젝트 전체에서 의미의 일관성과 추적성을 유지한다.

---

# 18. Revision History

| Version | Date       | Description             |
| ------- | ---------- | ----------------------- |
| 1.0.0   | 2026-06-26 | Initial Master Glossary |
