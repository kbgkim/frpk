# FRKP-SYM-100 — Master Symbol Dictionary

---

# Document Information

| Item            | Value                          |
| --------------- | ------------------------------ |
| Document ID     | FRKP-SYM-100                   |
| Document Name   | Master Symbol Dictionary       |
| Version         | 1.0.0                          |
| Status          | Active                         |
| Category        | Governance / Master Dictionary |
| Parent Standard | [FRKP-SYM-001](../FRKP-SYM-001_FORMULA_SYMBOL_STANDARD.md)                   |
| Created         | 2026-06-26                     |
| Last Updated    | 2026-06-26                     |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에서 사용하는 모든 수학 기호(Mathematical Symbols), 변수(Variables), 벡터(Vector), 행렬(Matrix), 그리스 문자(Greek Symbols) 및 금융 규제 산식 기호를 관리하는 중앙 사전(Canonical Symbol Registry)이다.

본 문서는 프로젝트 전체의 수학적 일관성과 추적성을 보장하는 단일 기준(Single Source of Truth)이다.

---

# 2. Scope

본 문서는 다음 영역을 포함한다.

* Basel III
* FRTB
* IFRS 9
* SA-CCR
* Liquidity Risk
* Financial Mathematics
* Statistics
* Portfolio Theory
* Artificial Intelligence

---

# 3. Dictionary Architecture

```text
Master Symbol Dictionary
            │
            ├── Credit Risk
            ├── Market Risk
            ├── Capital
            ├── Liquidity
            ├── Mathematics
            ├── Statistics
            └── AI
```

---

# 4. Symbol Governance

모든 기호는 다음 속성을 가진다.

* Preferred Symbol
* Preferred Term
* Unit
* Dimension
* Category
* Related Formula
* Related Documents

---

# 5. Credit Risk Symbols

| Symbol | Meaning                   | Unit     | Related Formula |
| ------ | ------------------------- | -------- | --------------- |
| PD     | Probability of Default    | %        | FC-431          |
| LGD    | Loss Given Default        | %        | FC-432          |
| EAD    | Exposure at Default       | Currency | FC-433, FC-444  |
| ECL    | Expected Credit Loss      | Currency | FC-434          |
| RC     | Replacement Cost          | Currency | FC-441          |
| PFE    | Potential Future Exposure | Currency | FC-442          |

---

# 6. Market Risk Symbols

| Symbol | Meaning            | Unit                    |
| ------ | ------------------ | ----------------------- |
| VaR    | Value at Risk      | Currency                |
| ES     | Expected Shortfall | Currency                |
| Δ      | Delta Sensitivity  | Currency / Risk Factor  |
| Γ      | Gamma Sensitivity  | Currency / Risk Factor² |
| ν      | Vega Sensitivity   | Currency / Volatility   |
| κ      | Curvature          | Currency                |

---

# 7. Capital Symbols

| Symbol | Meaning                    | Unit     |
| ------ | -------------------------- | -------- |
| RWA    | Risk Weighted Assets       | Currency |
| C      | Regulatory Capital         | Currency |
| CAR    | Capital Adequacy Ratio     | %        |
| CET1   | Common Equity Tier 1 Ratio | %        |

---

# 8. Liquidity Symbols

| Symbol | Meaning                    | Unit     |
| ------ | -------------------------- | -------- |
| LCR    | Liquidity Coverage Ratio   | %        |
| NSFR   | Net Stable Funding Ratio   | %        |
| HQLA   | High Quality Liquid Assets | Currency |

---

# 9. Statistics Symbols

| Symbol   | Meaning            | Unit          |
| -------- | ------------------ | ------------- |
| μ        | Mean               | Variable      |
| σ        | Standard Deviation | Variable      |
| σ²       | Variance           | Variable²     |
| ρ        | Correlation        | Dimensionless |
| Cov(X,Y) | Covariance         | Variable²     |

---

# 10. Linear Algebra Symbols

| Symbol | Meaning                 |
| ------ | ----------------------- |
| **A**  | Matrix                  |
| **Σ**  | Covariance Matrix       |
| **I**  | Identity Matrix         |
| **x**  | Vector                  |
| **w**  | Portfolio Weight Vector |
| λ      | Eigenvalue              |
| **v**  | Eigenvector             |

---

# 11. Optimization Symbols

| Symbol | Meaning                 |
| ------ | ----------------------- |
| w      | Portfolio Weight        |
| Σ      | Covariance Matrix       |
| r      | Expected Return Vector  |
| μ      | Expected Return         |
| λ      | Risk Aversion Parameter |

---

# 12. AI Symbols

| Symbol | Meaning          |
| ------ | ---------------- |
| θ      | Model Parameters |
| L      | Loss Function    |
| x      | Input Vector     |
| y      | Target Variable  |
| ŷ      | Predicted Value  |

---

# 13. Dimension Rules

| Type          | Example          |
| ------------- | ---------------- |
| Currency      | KRW, USD         |
| Percentage    | PD, LGD          |
| Dimensionless | Correlation      |
| Time          | Duration (Years) |

모든 기호는 단위를 명시하는 것을 원칙으로 한다.

---

# 14. Notation Rules

프로젝트 전체에서 다음 표기법을 사용한다.

| Object       | Style              |
| ------------ | ------------------ |
| Scalar       | *Italic*           |
| Vector       | **Bold Lowercase** |
| Matrix       | **Bold Uppercase** |
| Greek Symbol | Standard Greek     |
| Function     | Roman              |

예시

```math
\mathbf{\Sigma}\mathbf{w}
```

---

# 15. Reserved Symbols

다음 기호는 프로젝트 전역에서 예약한다.

| Symbol | Reserved Meaning                                 |
| ------ | ------------------------------------------------ |
| PD     | Probability of Default                           |
| LGD    | Loss Given Default                               |
| EAD    | Exposure at Default                              |
| ECL    | Expected Credit Loss                             |
| RC     | Replacement Cost                                 |
| PFE    | Potential Future Exposure                        |
| ES     | Expected Shortfall                               |
| RWA    | Risk Weighted Assets                             |
| Σ      | Covariance Matrix                                |
| λ      | Eigenvalue 또는 Risk Aversion Parameter(문맥에 따라 명시) |

예약 기호는 다른 의미로 재사용하지 않는다.

---

# 16. Cross Reference

```text
Master Symbol Dictionary
        │
        ├── FRKP-TERM-100 Master Glossary
        ├── FRKP-ABBR-100 Master Abbreviation
        ├── FRKP-SYM-101 Credit Risk Symbols
        ├── FRKP-SYM-201 Market Risk Symbols
        ├── FRKP-SYM-301 Liquidity Symbols
        ├── FRKP-SYM-401 Mathematics Symbols
        └── FRKP-SYM-501 AI Symbols
```

---

# 17. Governance Rules

새로운 기호를 도입할 때는 다음 절차를 따른다.

1. Preferred Term 확인
2. Official Abbreviation 확인
3. Symbol 등록
4. Unit 정의
5. Formula 연결
6. Domain Dictionary 등록

---

# 18. Future Expansion

향후 다음 문서를 작성한다.

| Document                            | Scope |
| ----------------------------------- | ----- |
| FRKP-SYM-101_CREDIT_RISK_SYMBOLS.md | 신용위험  |
| FRKP-SYM-201_MARKET_RISK_SYMBOLS.md | 시장위험  |
| FRKP-SYM-301_LIQUIDITY_SYMBOLS.md   | 유동성   |
| FRKP-SYM-401_MATHEMATICS_SYMBOLS.md | 수학    |
| FRKP-SYM-501_AI_SYMBOLS.md          | AI    |

---

# 19. Summary

Master Symbol Dictionary는 FRKP에서 사용하는 모든 수학 기호와 금융 규제 기호를 관리하는 중앙 저장소이다.

모든 기호는 대표 용어, 공식 약어, 단위, 관련 Formula 및 관련 문서와 연결되며, 프로젝트 전체에서 동일한 의미와 표기 규칙을 유지해야 한다. 이를 통해 Formula, Implementation 및 Architecture 전반에 걸쳐 수학적 일관성과 추적성을 확보한다.

---

# 20. Revision History

| Version | Date       | Description                      |
| ------- | ---------- | -------------------------------- |
| 1.0.0   | 2026-06-26 | Initial Master Symbol Dictionary |
