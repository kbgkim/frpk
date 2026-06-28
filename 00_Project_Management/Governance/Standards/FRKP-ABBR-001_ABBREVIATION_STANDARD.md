# FRKP-ABBR-001 — Abbreviation Standard

---

# Document Information

| Item          | Value                 |
| ------------- | --------------------- |
| Standard ID   | FRKP-ABBR-001         |
| Document Name | Abbreviation Standard |
| Version       | 1.0.0                 |
| Status        | Active                |
| Category      | Governance Standard   |
| Created       | 2026-06-26            |
| Last Updated  | 2026-06-26            |
| Applies To    | All FRKP Documents    |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에서 사용하는 모든 약어(Abbreviation)의 정의, 명명 규칙, 사용 원칙 및 관리 절차를 표준화한다.

본 표준의 목적은 다음과 같다.

* 프로젝트 전체의 약어 일관성 확보
* 동일 개념의 중복 약어 사용 방지
* 문서 간 의미 충돌 방지
* 용어(Term)와 기호(Symbol)의 연결
* 국제 금융 규제와의 정합성 확보

본 문서는 모든 약어 관리의 상위 규격(Normative Standard)으로 적용된다.

---

# 2. Scope

본 표준은 다음 문서에 적용한다.

* Reference Library
* Knowledge Base
* Analysis
* Formula Catalog
* Implementation Guide
* Architecture Guide
* Governance Documents
* Bundle Review Documents

---

# 3. Relationship Model

약어는 용어와 기호 사이의 연결 계층이다.

```text
Concept
    │
    ▼
Preferred Term
    │
    ▼
Official Abbreviation
    │
    ▼
Formula Symbol
```

약어는 개념을 축약하여 표현하지만, 개념 자체를 대체하지는 않는다.

---

# 4. Guiding Principles

모든 약어는 다음 원칙을 따른다.

1. One Concept → One Official Abbreviation
2. One Preferred Abbreviation
3. International Consistency
4. Stable Meaning
5. Technology Neutral
6. Traceable Definition
7. Backward Compatibility

---

# 5. Abbreviation Definition Template

모든 약어는 다음 정보를 포함한다.

| Field                  | Required |
| ---------------------- | :------: |
| Preferred Abbreviation |     ✔    |
| Full Term              |     ✔    |
| Definition             |     ✔    |
| Category               |     ✔    |
| Source                 |     ✔    |
| Related Symbol         | Optional |
| Notes                  | Optional |

---

# 6. Preferred Abbreviation Rule

동일 개념에는 하나의 공식 약어만 사용한다.

예시

| Preferred Abbreviation | Full Term                 |
| ---------------------- | ------------------------- |
| PD                     | Probability of Default    |
| LGD                    | Loss Given Default        |
| EAD                    | Exposure at Default       |
| ECL                    | Expected Credit Loss      |
| RC                     | Replacement Cost          |
| PFE                    | Potential Future Exposure |

다른 표현은 비권장(Alias)으로 관리한다.

---

# 7. First Use Rule

문서에서 약어를 처음 사용할 때는 전체 용어를 함께 표기한다.

예시

```text
Exposure at Default (EAD)

Expected Credit Loss (ECL)

Probability of Default (PD)
```

이후에는 약어만 사용할 수 있다.

---

# 8. Category Classification

약어는 최소 하나 이상의 카테고리를 가진다.

| Category          | Examples     |
| ----------------- | ------------ |
| Credit Risk       | PD, LGD, EAD |
| Market Risk       | VaR, ES, SBM |
| Liquidity         | LCR, NSFR    |
| Capital           | RWA, CET1    |
| Counterparty Risk | SA-CCR, CVA  |
| Accounting        | IFRS, IAS    |
| Mathematics       | PCA, SVD     |
| AI                | LLM, RAG     |

---

# 9. Source Priority

약어는 다음 우선순위를 따른다.

1. Basel Committee
2. IFRS Foundation
3. BIS
4. IOSCO
5. 금융감독원
6. 한국은행
7. FRKP 자체 정의

---

# 10. Alias Policy

동일한 개념에 여러 약어가 존재하는 경우 하나만 공식 약어로 지정한다.

예시

| Official | Alias              | Status                    |
| -------- | ------------------ | ------------------------- |
| ES       | Expected Tail Loss | Deprecated                |
| VaR      | Value-at-Risk      | Accepted Spelling Variant |

Alias는 검색과 호환성을 위해 유지할 수 있으나 문서에서는 공식 약어 사용을 원칙으로 한다.

---

# 11. Naming Rules

약어는 다음 규칙을 따른다.

* 국제적으로 널리 사용되는 형태를 우선한다.
* 임의의 프로젝트 전용 약어는 지양한다.
* 대문자 사용을 원칙으로 한다.
* 숫자는 필요한 경우에만 포함한다.

예시

```text
PD
LGD
EAD
CVA
RWA
FRTB
SA-CCR
```

---

# 12. Cross Reference

모든 약어는 관련 문서를 참조한다.

| Abbreviation | Related Documents |
| ------------ | ----------------- |
| PD           | FC-431, IMP-431   |
| LGD          | FC-432            |
| EAD          | FC-433, FC-444    |
| ES           | FC-421            |

---

# 13. Relationship with Other Standards

```text
FRKP-DOC-001
      │
      ├── FRKP-TERM-001
      ├── FRKP-ABBR-001
      ├── FRKP-SYM-001
      ├── FRKP-FORM-001
      ├── FRKP-IMP-001
      ├── FRKP-ARCH-001
      └── FRKP-BUNDLE-001
```

* **Glossary(Standard)** 는 개념을 정의한다.
* **Abbreviation(Standard)** 는 공식 약어를 정의한다.
* **Formula Symbol(Standard)** 는 수학적 표현을 정의한다.

---

# 14. Review Checklist

약어 검토 시 다음을 확인한다.

| Check                  | Required |
| ---------------------- | :------: |
| Preferred Abbreviation |     ✔    |
| Full Term              |     ✔    |
| Duplicate Check        |     ✔    |
| Source Verified        |     ✔    |
| Cross Reference        |     ✔    |
| Category Assigned      |     ✔    |

---

# 15. Compliance

모든 FRKP 문서는 본 표준의 약어를 사용해야 한다.

새로운 약어를 도입하는 경우에는 Master Abbreviation Dictionary에 등록한 후 사용할 수 있다.

---

# 16. Future Evolution

향후 다음 문서를 작성한다.

| Document                                   | Scope         |
| ------------------------------------------ | ------------- |
| FRKP-ABBR-100_MASTER_ABBREVIATION.md       | 프로젝트 전체 약어 사전 |
| FRKP-ABBR-101_CREDIT_RISK_ABBREVIATIONS.md | 신용위험          |
| FRKP-ABBR-201_MARKET_RISK_ABBREVIATIONS.md | 시장위험          |
| FRKP-ABBR-301_LIQUIDITY_ABBREVIATIONS.md   | 유동성           |
| FRKP-ABBR-401_MATHEMATICS_ABBREVIATIONS.md | 수학            |
| FRKP-ABBR-501_AI_ABBREVIATIONS.md          | AI            |

---

# 17. Summary

Abbreviation Standard는 FRKP에서 사용하는 모든 공식 약어의 정의, 명명 규칙 및 사용 원칙을 표준화한다.

모든 약어는 하나의 대표 개념(Preferred Term)에 대응하며, 국제 규제 기준을 우선으로 하고 프로젝트 전체에서 동일한 의미를 유지해야 한다. 이를 통해 Glossary, Formula Symbol 및 모든 FRKP 문서 간의 일관성과 추적성을 확보한다.

---

# 18. Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-06-26 | Initial Standard |
