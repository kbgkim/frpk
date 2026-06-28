# FRKP-TERM-001 — Glossary Standard

---

# Document Information

| Item          | Value               |
| ------------- | ------------------- |
| Standard ID   | FRKP-TERM-001       |
| Document Name | Glossary Standard   |
| Version       | 1.0.0               |
| Status        | Active              |
| Category      | Governance Standard |
| Created       | 2026-06-26          |
| Last Updated  | 2026-06-26          |
| Applies To    | All FRKP Documents  |

---

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에서 사용하는 모든 업무 용어(Business Terms), 규제 용어(Regulatory Terms), 수학 용어(Mathematical Terms) 및 기술 용어(Technical Terms)의 정의 및 관리 기준을 규정한다.

본 표준의 목적은 다음과 같다.

* 프로젝트 전체의 용어 일관성 확보
* 동일 용어의 중복 정의 방지
* 문서 간 의미 충돌 방지
* Formula와 Architecture 간 의미 일치
* 장기적인 Knowledge Platform 구축

본 문서는 **용어집(Glossary)을 작성하는 방법**을 정의하는 상위 규격이다.

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

모든 FRKP 문서는 본 표준을 따른다.

---

# 3. Glossary Position

Glossary는 모든 문서의 공통 의미 체계를 제공한다.

```text
                Glossary
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

Glossary는 모든 문서 계층보다 상위 개념이다.

---

# 4. Guiding Principles

용어 정의는 다음 원칙을 따른다.

1. One Concept → One Definition
2. One Preferred Term
3. Business First
4. Regulatory Consistency
5. Technology Neutral
6. Stable Meaning
7. Traceable Definition

---

# 5. Definition Rules

각 용어는 다음 항목을 포함해야 한다.

| Field          | Required |
| -------------- | :------: |
| Preferred Term |     ✔    |
| Definition     |     ✔    |
| Category       |     ✔    |
| Source         |     ✔    |
| Related Terms  |     ✔    |
| Synonyms       | Optional |
| Abbreviation   | Optional |
| Notes          | Optional |

---

# 6. Preferred Term Rule

하나의 개념에는 하나의 대표 용어만 사용한다.

예시

| Preferred              | Avoid                     |
| ---------------------- | ------------------------- |
| Exposure at Default    | Default Exposure          |
| Replacement Cost       | Current Replacement Value |
| Probability of Default | Default Probability       |

대표 용어 이외의 표현은 별칭(Synonym)으로 관리한다.

---

# 7. Definition Style

정의는 다음 형식을 따른다.

```text
<용어>는
<무엇인지 정의>

<왜 필요한지 설명>

<어디에서 사용하는지 설명>
```

예시

> Exposure at Default(EAD)는 거래상대방이 부도하는 시점에 금융기관이 규제 목적상 보유하고 있다고 간주하는 신용노출이다.

---

# 8. Term Categories

용어는 반드시 하나 이상의 카테고리를 가진다.

| Category    | Examples             |
| ----------- | -------------------- |
| Business    | Portfolio, Trade     |
| Regulatory  | RWA, Capital Ratio   |
| Credit Risk | PD, LGD, EAD         |
| Market Risk | Delta, Vega          |
| Liquidity   | LCR, NSFR            |
| Mathematics | Matrix, Eigenvalue   |
| Statistics  | Variance, Covariance |
| AI          | Embedding, Attention |
| Technology  | API, Batch           |

---

# 9. Source Hierarchy

용어 정의는 다음 우선순위를 따른다.

1. Basel Committee
2. IFRS Foundation
3. BIS
4. IOSCO
5. 금융감독원
6. 한국은행
7. FRKP 자체 정의

FRKP 자체 정의를 사용할 경우 근거를 명시한다.

---

# 10. Synonym Rules

동일 의미의 용어는 별칭으로 관리한다.

예시

| Preferred              | Synonym |
| ---------------------- | ------- |
| Exposure at Default    | EAD     |
| Probability of Default | PD      |
| Loss Given Default     | LGD     |

문서 본문에서는 대표 용어 사용을 원칙으로 한다.

---

# 11. Abbreviation Rules

약어는 최초 등장 시 전체 명칭과 함께 표기한다.

예시

```text
Exposure at Default (EAD)
```

이후에는 약어 사용을 허용한다.

---

# 12. Cross Reference

각 용어는 관련 문서를 참조해야 한다.

예시

| Related Document |
| ---------------- |
| KB-231           |
| FC-431           |
| IMP-431          |

---

# 13. Versioning

용어 정의가 변경되는 경우 버전을 관리한다.

| Version | Meaning |
| ------- | ------- |
| 1.0     | 최초 정의   |
| 1.1     | 설명 보완   |
| 2.0     | 의미 변경   |

의미가 변경되면 반드시 Major Version을 증가시킨다.

---

# 14. Change Control

다음 경우에만 정의를 변경할 수 있다.

* 규제 변경
* 국제 표준 변경
* FRKP Governance 승인
* 명백한 오류 수정

변경 시 Revision History를 반드시 기록한다.

---

# 15. Review Checklist

Glossary Review 시 다음을 확인한다.

| Check           | Required |
| --------------- | :------: |
| Preferred Term  |     ✔    |
| Definition      |     ✔    |
| Category        |     ✔    |
| Source          |     ✔    |
| Cross Reference |     ✔    |
| Duplicate Check |     ✔    |
| Synonym Check   |     ✔    |

---

# 16. Compliance

모든 FRKP 문서는 본 표준의 용어 정의를 사용해야 한다.

동일 개념에 대해 새로운 용어를 사용하는 경우에는 Glossary에 먼저 등록한 후 문서에 반영한다.

---

# 17. Relationship with Other Standards

Glossary는 다음 표준과 함께 사용한다.

```text
FRKP-DOC-001
      │
      ├── FRKP-TERM-001
      ├── FRKP-KB-001
      ├── FRKP-FORM-001
      ├── FRKP-IMP-001
      ├── FRKP-ARCH-001
      └── FRKP-BUNDLE-001
```

---

# 18. Future Evolution

향후 다음 문서를 추가한다.

* FRKP-TERM-101_CREDIT_RISK_GLOSSARY.md
* FRKP-TERM-201_MARKET_RISK_GLOSSARY.md
* FRKP-TERM-301_LIQUIDITY_GLOSSARY.md
* FRKP-TERM-401_MATHEMATICS_GLOSSARY.md
* FRKP-TERM-501_AI_GLOSSARY.md

본 표준은 이들 도메인별 용어집의 공통 규격으로 사용한다.

---

# 19. Summary

Glossary Standard는 FRKP 전체에서 사용하는 용어의 정의, 작성 방식, 관리 절차 및 변경 원칙을 표준화한다.

모든 용어는 하나의 대표 정의(Preferred Definition)를 가지며, 규제 표준을 우선으로 하고, 문서 간 추적성과 일관성을 유지해야 한다. 이를 통해 FRKP는 장기적으로 일관된 금융 리스크 지식 플랫폼을 유지할 수 있다.

---

# 20. Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-06-26 | Initial Standard |
