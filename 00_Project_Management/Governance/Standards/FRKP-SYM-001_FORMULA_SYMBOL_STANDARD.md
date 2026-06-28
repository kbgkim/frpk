# FRKP-SYM-001 — Formula Symbol Standard

---

# Document Information

| Item          | Value                                  |
| ------------- | -------------------------------------- |
| Standard ID   | FRKP-SYM-001                           |
| Document Name | Formula Symbol Standard                |
| Version       | 1.0.0                                  |
| Status        | Active                                 |
| Category      | Governance Standard                    |
| Created       | 2026-06-26                             |
| Last Updated  | 2026-06-26                             |
| Applies To    | All Formula and Mathematical Documents |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에서 사용하는 모든 수학 기호(Mathematical Symbols), 변수(Variables), 약어(Symbolic Abbreviations) 및 규제 산식의 표기 규칙을 정의한다.

본 표준의 목적은 다음과 같다.

* Formula Catalog의 기호 일관성 확보
* 동일 개념의 중복 기호 사용 방지
* 문서 간 수학적 의미 유지
* 구현과 독립적인 기호 체계 구축
* 장기적인 Formula Dictionary 구축

본 문서는 **기호를 정의하고 관리하는 상위 규격(Normative Standard)** 이다.

---

# 2. Scope

본 표준은 다음 문서에 적용한다.

* Formula Catalog (FC-*)
* Knowledge Base (KB-*)
* Analysis (AN-*)
* Implementation Guide (IMP-*)
* Architecture Guide (ARCH-*)
* Mathematical Foundation
* AI Mathematical Documents

---

# 3. Symbol Position in FRKP

Formula Symbol은 Formula 계층뿐 아니라 모든 계산 문서의 공통 언어이다.

```text
                 Symbol Dictionary
                        │
                        ▼
Reference
    │
Knowledge
    │
Analysis
    │
Formula
    │
Implementation
    │
Architecture
```

Symbol Standard는 Formula보다 상위 개념이다.

---

# 4. Guiding Principles

기호는 다음 원칙을 따른다.

1. One Concept → One Symbol
2. One Preferred Symbol
3. Mathematical Consistency
4. Regulatory Consistency
5. Technology Neutral
6. Stable Meaning
7. Reusable Across Bundles

---

# 5. Symbol Definition Template

모든 기호는 다음 항목을 가진다.

| Field            | Required |
| ---------------- | :------: |
| Preferred Symbol |     ✔    |
| Full Name        |     ✔    |
| Definition       |     ✔    |
| Unit             |     ✔    |
| Category         |     ✔    |
| Source           |     ✔    |
| Related Symbols  | Optional |
| Notes            | Optional |

---

# 6. Preferred Symbol Rule

동일 개념은 하나의 대표 기호만 사용한다.

예시

| Concept                   | Preferred Symbol |
| ------------------------- | ---------------- |
| Probability of Default    | PD               |
| Loss Given Default        | LGD              |
| Exposure at Default       | EAD              |
| Replacement Cost          | RC               |
| Potential Future Exposure | PFE              |
| Expected Credit Loss      | ECL              |

다른 표기는 별칭으로만 관리한다.

---

# 7. Naming Rules

기호는 가능한 한 국제적으로 널리 사용되는 표기를 따른다.

우선순위

1. Basel Committee
2. IFRS Foundation
3. BIS
4. 국제 금융공학 관례
5. FRKP 정의

---

# 8. Symbol Categories

모든 기호는 최소 하나 이상의 카테고리를 가진다.

| Category       | Examples     |
| -------------- | ------------ |
| Credit Risk    | PD, LGD, EAD |
| Market Risk    | Δ, Γ, ν, ES  |
| Liquidity      | LCR, NSFR    |
| Capital        | RWA, CET1    |
| Statistics     | μ, σ, ρ      |
| Linear Algebra | A, x, λ      |
| Optimization   | w, Σ         |
| AI             | θ, L         |

---

# 9. Greek Letter Policy

그리스 문자는 국제 관례를 따른다.

| Symbol | Typical Meaning             |
| ------ | --------------------------- |
| α      | Adjustment / Alpha          |
| β      | Beta                        |
| γ      | Gamma                       |
| δ      | Delta                       |
| ε      | Error / Residual            |
| λ      | Eigenvalue / Regularization |
| μ      | Mean                        |
| ρ      | Correlation                 |
| σ      | Standard Deviation          |
| ν      | Vega (관례적 사용)               |

하나의 문서에서 동일한 그리스 문자를 서로 다른 의미로 사용해서는 안 된다.

---

# 10. Latin Letter Policy

라틴 문자는 가능한 의미 중심으로 사용한다.

예시

| Symbol | Meaning      |
| ------ | ------------ |
| E      | Exposure     |
| C      | Collateral   |
| V      | Market Value |
| T      | Time         |
| N      | Notional     |

문서 내에서 의미를 명확히 정의해야 한다.

---

# 11. Unit Convention

모든 기호는 단위를 명시한다.

예시

| Symbol   | Unit     |
| -------- | -------- |
| PD       | %        |
| LGD      | %        |
| EAD      | Currency |
| ES       | Currency |
| Duration | Year     |

단위가 없는 경우 "Dimensionless"로 표기한다.

---

# 12. Mathematical Notation Rules

수식 작성 원칙

* 변수는 이탤릭체 사용
* 함수명은 일반체 사용
* 벡터는 **굵은 소문자**
* 행렬은 **굵은 대문자**
* 스칼라는 일반 이탤릭체

예시

```math
\mathbf{A}\mathbf{x}=\mathbf{b}
```

---

# 13. Reserved Symbols

다음 기호는 프로젝트 전역에서 예약한다.

| Symbol | Reserved Meaning          |
| ------ | ------------------------- |
| PD     | Probability of Default    |
| LGD    | Loss Given Default        |
| EAD    | Exposure at Default       |
| RC     | Replacement Cost          |
| PFE    | Potential Future Exposure |
| ECL    | Expected Credit Loss      |
| ES     | Expected Shortfall        |
| RWA    | Risk Weighted Assets      |

예약 기호는 다른 의미로 재사용하지 않는다.

---

# 14. Cross Reference

각 기호는 관련 Formula를 참조해야 한다.

예시

| Symbol | Related Formula |
| ------ | --------------- |
| EAD    | FC-444          |
| RC     | FC-441          |
| PFE    | FC-442          |

---

# 15. Versioning

기호 정의 변경은 다음 규칙을 따른다.

| Version | Meaning |
| ------- | ------- |
| 1.0     | 최초 정의   |
| 1.1     | 설명 보완   |
| 2.0     | 의미 변경   |

의미 변경 시에는 Major Version을 증가시킨다.

---

# 16. Review Checklist

Symbol Review 시 확인 사항

| Check            | Required |
| ---------------- | :------: |
| Preferred Symbol |     ✔    |
| Duplicate Symbol |     ✔    |
| Definition       |     ✔    |
| Unit             |     ✔    |
| Category         |     ✔    |
| Source           |     ✔    |
| Related Formula  |     ✔    |

---

# 17. Compliance

모든 Formula 및 수학 관련 문서는 본 표준을 준수해야 한다.

새로운 기호를 도입하는 경우에는 Symbol Dictionary에 먼저 등록한 후 사용한다.

---

# 18. Relationship with Other Standards

```text
FRKP-DOC-001
      │
      ├── FRKP-TERM-001
      ├── FRKP-SYM-001
      ├── FRKP-FORM-001
      ├── FRKP-IMP-001
      ├── FRKP-ARCH-001
      └── FRKP-BUNDLE-001
```

용어 표준은 개념을 정의하고, Symbol Standard는 그 개념의 수학적 표현을 정의한다.

---

# 19. Future Evolution

향후 다음 문서를 작성한다.

* FRKP-SYM-100_MASTER_SYMBOL_DICTIONARY.md
* FRKP-SYM-101_CREDIT_RISK_SYMBOLS.md
* FRKP-SYM-201_MARKET_RISK_SYMBOLS.md
* FRKP-SYM-301_LIQUIDITY_SYMBOLS.md
* FRKP-SYM-401_MATHEMATICS_SYMBOLS.md
* FRKP-SYM-501_AI_SYMBOLS.md

본 표준은 이들 Symbol Dictionary의 공통 규격으로 사용한다.

---

# 20. Summary

Formula Symbol Standard는 FRKP 전체에서 사용하는 수학 기호와 변수의 정의, 명명 규칙, 단위, 사용 원칙 및 변경 절차를 표준화한다.

모든 기호는 하나의 대표 기호(Preferred Symbol)를 가지며, 동일한 기호는 프로젝트 전체에서 동일한 의미를 유지해야 한다. 이를 통해 Formula Catalog, Implementation Guide, Architecture Guide 및 Knowledge Base 간의 수학적 일관성과 추적성을 확보한다.

---

# 21. Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-06-26 | Initial Standard |
