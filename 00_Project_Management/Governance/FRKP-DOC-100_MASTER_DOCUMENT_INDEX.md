# FRKP-DOC-100 — Master Document Index

---

# Document Information

| Item             | Value                 |
| ---------------- | --------------------- |
| Document ID      | FRKP-DOC-100          |
| Document Name    | Master Document Index |
| Version          | 1.0.0                 |
| Status           | Active                |
| Category         | Governance Index      |
| Owner            | FRKP Governance       |
| Created          | 2026-06-27            |
| Last Updated     | 2026-06-27            |
| Parent Standard  | [FRKP-DOC-001](Standards/FRKP-DOC-001_DOCUMENT_STANDARD.md)          |
| Related Standard | FRKP-ID-001           |

---

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../README.md) > [Home](../../README.md) > [Project Management](../README.md) > [Governance](FRKP-001_PROJECT_CHARTER.md) > [FRKP-DOC-100 — Master Document Index](FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | None |
| ⬆ Parent Bundle | None |
| ⬆ Parent Layer | [Governance](../README.md) |
| ➡ Next | [FRKP-DOC-001](Standards/FRKP-DOC-001_DOCUMENT_STANDARD.md) |

### Related Documents

- [FRKP-DOC-001](Standards/FRKP-DOC-001_DOCUMENT_STANDARD.md)
- [FRKP-ID-001](Standards/FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md)
- [FRKP-FORM-001](Standards/FRKP-FORM-001_FORMULA_STANDARD.md)
- [FRKP-BUNDLE-001](Standards/FRKP-BUNDLE-001_BUNDLE_STANDARD.md)
- [FRKP-TPL-001](Templates/FRKP-TPL-001_DOCUMENT_TEMPLATE.md)
<!-- FRKP-NAV-END -->

# 1. Purpose

본 문서는 Financial Risk Knowledge Platform(FRKP)에 포함된 모든 공식 문서를 관리하기 위한 **Master Document Index**이다.

본 문서는 Repository 전체의 문서 등록부(Document Registry) 역할을 수행하며 다음 목적을 가진다.

* 전체 문서 목록 관리
* 문서 계층 관리
* Document ID 추적
* 문서 상태 관리
* Bundle 진행 현황 관리
* Repository 무결성 검증 지원

---

# 2. Scope

본 인덱스는 다음 문서를 포함한다.

* Governance
* Project Management
* Reference Library
* Knowledge Base
* Analysis
* Formula Catalog
* Mathematical Foundation
* Implementation Guide
* Architecture Guide
* Bundle Review

---

# 3. Repository Knowledge Hierarchy

```text
Governance
      │
      ▼
Reference Library
      │
      ▼
Knowledge Base
      │
      ▼
Analysis
      │
      ▼
Formula Catalog
      │
      ▼
Mathematical Foundation
      │
      ▼
Implementation Guide
      │
      ▼
Architecture Guide
      │
      ▼
Bundle Review
```

---

# 4. Governance Documents

| Document ID     | Document                              | Status |
| --------------- | ------------------------------------- | ------ |
| FRKP-001        | Project Charter                       | Frozen |
| FRKP-002        | Project Bootstrap                     | Frozen |
| FRKP-RMAP-001   | Master Roadmap *(after ID migration)* | Active |
| FRKP-DOC-001    | Document Standard                     | Frozen |
| FRKP-ID-001     | Document Identifier Standard          | Frozen |
| FRKP-ARCH-001   | Architecture Standard                 | Frozen |
| FRKP-FORM-001   | Formula Standard                      | Frozen |
| FRKP-TERM-001   | Glossary Standard                     | Frozen |
| FRKP-ABBR-001   | Abbreviation Standard                 | Frozen |
| FRKP-SYM-001    | Formula Symbol Standard               | Frozen |
| FRKP-BUNDLE-001 | Bundle Standard                       | Frozen |
| FRKP-TPL-001    | Document Template                     | Frozen |

---

# 5. Bundle Status

| Bundle     | Topic                             | Status      |
| ---------- | --------------------------------- | ----------- |
| Bundle-001 | Basel III                         | Completed   |
| Bundle-002 | FRTB                              | Completed   |
| Bundle-003 | IFRS 9                            | Completed   |
| Bundle-004 | SA-CCR                            | Completed   |
| Bundle-005 | Credit Valuation Adjustment (CVA) | In Progress |
| Bundle-006 | Market Risk Standardized Approach | Planned     |
| Bundle-007 | Operational Risk                  | Planned     |
| Bundle-008 | Liquidity Risk                    | Planned     |
| Bundle-009 | ICAAP                             | Planned     |
| Bundle-010 | Stress Testing                    | Planned     |
| Bundle-011 | Model Risk Management             | Planned     |
| Bundle-012 | Climate Risk                      | Planned     |

---

# 6. Layer Registry

| Layer                   | Prefix | Directory                     |
| ----------------------- | ------ | ----------------------------- |
| Reference Library       | RL     | `01_Reference_Library/`       |
| Knowledge Base          | KB     | `02_Knowledge_Base/`          |
| Analysis                | AN     | `03_Analysis/`                |
| Formula Catalog         | FC     | `04_Formula_Catalog/`         |
| Mathematical Foundation | MF     | `05_Mathematical_Foundation/` |
| Implementation Guide    | IMP    | `06_Implementation_Guide/`    |
| Architecture Guide      | ARCH   | `07_Architecture/`            |
| Bundle Review           | BUNDLE | `08_Bundles/`                 |

---

# 7. Current Bundle Deliverables

| Bundle |  RL |  KB |  AN |  FC |  MF | IMP | ARCH | Review |
| ------ | :-: | :-: | :-: | :-: | :-: | :-: | :--: | :----: |
| 001    |  ✓  |  ✓  |  ✓  |  ✓  |  —  |  ✓  |   ✓  |    ✓   |
| 002    |  ✓  |  ✓  |  ✓  |  ✓  |  —  |  ✓  |   ✓  |    ✓   |
| 003    |  ✓  |  ✓  |  ✓  |  ✓  |  —  |  ✓  |   ✓  |    ✓   |
| 004    |  ✓  |  ✓  |  ✓  |  ✓  |  —  |  ✓  |   ✓  |    ✓   |
| 005    |  ✓  |  ✓  |  △  |  △  |  △  |  △  |   △  |    △   |

Legend

* ✓ Completed
* △ In Progress
* — Not Required

---

# 8. Numbering Overview

| Prefix      | Description             |
| ----------- | ----------------------- |
| FRKP        | Governance              |
| FRKP-DOC    | Documentation Standard  |
| FRKP-ID     | Identifier Standard     |
| FRKP-ARCH   | Architecture Standard   |
| FRKP-FORM   | Formula Standard        |
| FRKP-TERM   | Terminology Standard    |
| FRKP-ABBR   | Abbreviation Standard   |
| FRKP-SYM    | Symbol Standard         |
| FRKP-BUNDLE | Bundle Standard         |
| FRKP-TPL    | Document Template       |
| FRKP-RMAP   | Master Roadmap          |
| RL          | Reference Library       |
| KB          | Knowledge Base          |
| AN          | Analysis                |
| FC          | Formula Catalog         |
| MF          | Mathematical Foundation |
| IMP         | Implementation Guide    |
| ARCH        | Architecture Guide      |
| BUNDLE      | Bundle Review           |

---

# 9. Repository Validation Checklist

Repository Freeze 전 다음 항목을 확인한다.

* 모든 Document ID는 유일하다.
* 파일명과 Document ID가 일치한다.
* Layer별 Prefix가 올바르다.
* Bundle 디렉토리 구조가 일관된다.
* Cross Reference가 유효하다.
* README가 최신 상태이다.
* Governance 문서가 최신 상태이다.

---

# 10. Maintenance Rules

본 문서는 다음 경우 반드시 갱신한다.

1. 새로운 Governance 문서 추가
2. 새로운 Bundle 생성
3. 새로운 Layer 추가
4. 새로운 Prefix 추가
5. Repository 구조 변경
6. Document ID Namespace 변경

---

# 11. Cross References

| Category   | Document                                            |
| ---------- | --------------------------------------------------- |
| Governance | [FRKP-DOC-001_DOCUMENT_STANDARD](Standards/FRKP-DOC-001_DOCUMENT_STANDARD.md)                      |
| Governance | [FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD](Standards/FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md)            |
| Governance | [FRKP-BUNDLE-001_BUNDLE_STANDARD](Standards/FRKP-BUNDLE-001_BUNDLE_STANDARD.md)                     |
| Governance | [FRKP-RMAP-001_MASTER_ROADMAP](../Roadmap/FRKP_MASTER_ROADMAP.md) *(after ID migration)* |

---

# 12. Summary

Master Document Index는 FRKP Repository의 공식 문서 등록부이다.

Repository에 포함된 모든 Governance 문서와 Knowledge 문서의 계층, 식별자, Bundle 진행 현황 및 관리 규칙을 중앙에서 관리하며, Repository Freeze와 지속적인 Repository Governance의 기준 문서로 사용된다.

---

# Revision History

| Version | Date       | Description     |
| ------- | ---------- | --------------- |
| 1.0.0   | 2026-06-27 | Initial version |
