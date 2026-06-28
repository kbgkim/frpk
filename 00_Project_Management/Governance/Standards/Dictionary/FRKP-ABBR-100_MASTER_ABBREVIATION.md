# FRKP-ABBR-100 — Master Abbreviation Dictionary

---

# Document Information

| Item            | Value                          |
| --------------- | ------------------------------ |
| Document ID     | FRKP-ABBR-100                  |
| Document Name   | Master Abbreviation Dictionary |
| Version         | 1.0.0                          |
| Status          | Active                         |
| Category        | Governance / Master Dictionary |
| Parent Standard | [FRKP-ABBR-001](../FRKP-ABBR-001_ABBREVIATION_STANDARD.md)                  |
| Created         | 2026-06-26                     |
| Last Updated    | 2026-06-26                     |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에서 사용하는 모든 공식 약어(Official Abbreviation)를 관리하는 중앙 사전(Canonical Dictionary)이다.

본 문서는 다음을 제공한다.

* 프로젝트 전체의 공식 약어 등록부
* 용어(Term)와 약어(Abbreviation)의 연결
* 약어(Symbolic Name)의 일관성 유지
* 문서 간 의미 충돌 방지
* 도메인별 약어 인덱스

모든 FRKP 문서는 본 문서를 기준으로 약어를 사용한다.

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
* Statistics
* Artificial Intelligence

---

# 3. Dictionary Architecture

```text
Master Abbreviation Dictionary
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

# 4. Registry Policy

모든 약어는 다음 원칙을 따른다.

* One Concept → One Official Abbreviation
* One Preferred Abbreviation
* 국제 규제 표준 우선
* 프로젝트 전체에서 동일 의미 유지
* 대표 용어(Preferred Term)와 연결

---

# 5. Domain Index

| Domain      | Document      |
| ----------- | ------------- |
| Credit Risk | FRKP-ABBR-101 |
| Market Risk | FRKP-ABBR-201 |
| Liquidity   | FRKP-ABBR-301 |
| Mathematics | FRKP-ABBR-401 |
| AI          | FRKP-ABBR-501 |

---

# 6. Credit Risk Abbreviations

| Abbreviation | Full Term                                          | Related Symbol | Related Formula |
| ------------ | -------------------------------------------------- | -------------- | --------------- |
| PD           | Probability of Default                             | PD             | FC-431          |
| LGD          | Loss Given Default                                 | LGD            | FC-432          |
| EAD          | Exposure at Default                                | EAD            | FC-433, FC-444  |
| ECL          | Expected Credit Loss                               | ECL            | FC-434          |
| RC           | Replacement Cost                                   | RC             | FC-441          |
| PFE          | Potential Future Exposure                          | PFE            | FC-442          |
| CCR          | Counterparty Credit Risk                           | -              | KB-241          |
| SA-CCR       | Standardised Approach for Counterparty Credit Risk | -              | KB-242          |
| CVA          | Credit Valuation Adjustment                        | CVA            | 향후 작성           |

---

# 7. Market Risk Abbreviations

| Abbreviation | Full Term                | Related Formula |
| ------------ | ------------------------ | --------------- |
| VaR          | Value at Risk            | FC-411          |
| ES           | Expected Shortfall       | FC-421          |
| SBM          | Sensitivity Based Method | FC-423          |
| DRC          | Default Risk Charge      | 향후 작성           |
| RRAO         | Residual Risk Add-On     | 향후 작성           |
| RF           | Risk Factor              | FC-423          |
| LH           | Liquidity Horizon        | FC-422          |

---

# 8. Capital Abbreviations

| Abbreviation | Full Term              |
| ------------ | ---------------------- |
| RWA          | Risk Weighted Assets   |
| CAR          | Capital Adequacy Ratio |
| CET1         | Common Equity Tier 1   |
| AT1          | Additional Tier 1      |
| T2           | Tier 2 Capital         |

---

# 9. Liquidity Abbreviations

| Abbreviation | Full Term                  |
| ------------ | -------------------------- |
| LCR          | Liquidity Coverage Ratio   |
| NSFR         | Net Stable Funding Ratio   |
| HQLA         | High Quality Liquid Assets |

---

# 10. Mathematics Abbreviations

| Abbreviation | Full Term                    |
| ------------ | ---------------------------- |
| PCA          | Principal Component Analysis |
| SVD          | Singular Value Decomposition |
| PSD          | Positive Semi-definite       |
| SPD          | Symmetric Positive Definite  |
| OLS          | Ordinary Least Squares       |

---

# 11. Statistics Abbreviations

| Abbreviation | Full Term                               |
| ------------ | --------------------------------------- |
| PDF          | Probability Density Function            |
| CDF          | Cumulative Distribution Function        |
| IID          | Independent and Identically Distributed |
| MLE          | Maximum Likelihood Estimation           |

---

# 12. AI Abbreviations

| Abbreviation | Full Term                      |
| ------------ | ------------------------------ |
| AI           | Artificial Intelligence        |
| ML           | Machine Learning               |
| DL           | Deep Learning                  |
| LLM          | Large Language Model           |
| RAG          | Retrieval-Augmented Generation |
| NLP          | Natural Language Processing    |
| RL           | Reinforcement Learning         |

---

# 13. Common Technical Abbreviations

| Abbreviation | Full Term                         |
| ------------ | --------------------------------- |
| API          | Application Programming Interface |
| ETL          | Extract Transform Load            |
| REST         | Representational State Transfer   |
| JSON         | JavaScript Object Notation        |
| SQL          | Structured Query Language         |

---

# 14. Cross Reference

```text
Master Abbreviation
        │
        ├── FRKP-TERM-100 Master Glossary
        ├── FRKP-SYM-100 Master Symbol Dictionary
        ├── FRKP-ABBR-101 Credit Risk
        ├── FRKP-ABBR-201 Market Risk
        ├── FRKP-ABBR-301 Liquidity
        ├── FRKP-ABBR-401 Mathematics
        └── FRKP-ABBR-501 AI
```

---

# 15. Governance Rules

모든 약어는 다음 절차를 따른다.

1. Preferred Term 등록
2. Official Abbreviation 등록
3. Formula Symbol 연결
4. Related Formula 연결
5. Domain Dictionary 등록

---

# 16. Reserved Abbreviations

다음 약어는 프로젝트 전역에서 예약한다.

| Abbreviation | Reserved Meaning          |
| ------------ | ------------------------- |
| PD           | Probability of Default    |
| LGD          | Loss Given Default        |
| EAD          | Exposure at Default       |
| ECL          | Expected Credit Loss      |
| RC           | Replacement Cost          |
| PFE          | Potential Future Exposure |
| RWA          | Risk Weighted Assets      |
| ES           | Expected Shortfall        |
| VaR          | Value at Risk             |
| LCR          | Liquidity Coverage Ratio  |
| NSFR         | Net Stable Funding Ratio  |
| LLM          | Large Language Model      |

예약 약어는 다른 의미로 재사용할 수 없다.

---

# 17. Future Expansion

향후 다음 문서를 작성한다.

| Document                                   | Scope |
| ------------------------------------------ | ----- |
| FRKP-ABBR-101_CREDIT_RISK_ABBREVIATIONS.md | 신용위험  |
| FRKP-ABBR-201_MARKET_RISK_ABBREVIATIONS.md | 시장위험  |
| FRKP-ABBR-301_LIQUIDITY_ABBREVIATIONS.md   | 유동성   |
| FRKP-ABBR-401_MATHEMATICS_ABBREVIATIONS.md | 수학    |
| FRKP-ABBR-501_AI_ABBREVIATIONS.md          | AI    |

---

# 18. Summary

Master Abbreviation Dictionary는 FRKP에서 사용하는 모든 공식 약어를 관리하는 중앙 저장소(Canonical Registry)이다.

모든 약어는 대표 용어(Preferred Term), 수학 기호(Symbol), Formula Catalog 및 도메인 문서와 연결되며, 프로젝트 전체에서 동일한 의미와 표기를 유지해야 한다. 이를 통해 용어, 기호 및 문서 간의 추적성과 일관성을 확보한다.

---

# 19. Revision History

| Version | Date       | Description                            |
| ------- | ---------- | -------------------------------------- |
| 1.0.0   | 2026-06-26 | Initial Master Abbreviation Dictionary |
