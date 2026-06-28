# FRKP-DOC-001 — Document Standard

<!-- FRKP-NAV-START -->
[Financial Risk Knowledge Platform](../../../README.md) > [Home](../../../README.md) > [Project Management](../../README.md) > [Governance](../FRKP-001_PROJECT_CHARTER.md) > [FRKP-DOC-001 — Document Standard](FRKP-DOC-001_DOCUMENT_STANDARD.md)

---

## Navigation

| Navigation | Document |
|------------|----------|
| ⬅ Previous | [FRKP-DOC-100](../FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md) |
| ⬆ Parent Bundle | None |
| ⬆ Parent Layer | [Governance](../../README.md) |
| ➡ Next | [FRKP-ID-001](FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md) |

### Related Documents

- [FRKP-DOC-100](../FRKP-DOC-100_MASTER_DOCUMENT_INDEX.md)
- [FRKP-ID-001](FRKP-ID-001_DOCUMENT_IDENTIFIER_STANDARD.md)
- [FRKP-FORM-001](FRKP-FORM-001_FORMULA_STANDARD.md)
- [FRKP-BUNDLE-001](FRKP-BUNDLE-001_BUNDLE_STANDARD.md)
- [FRKP-TPL-001](../Templates/FRKP-TPL-001_DOCUMENT_TEMPLATE.md)
<!-- FRKP-NAV-END -->

## Version 1.1.0 Update

---

# Revision History

기존 Revision History를 다음과 같이 수정한다.

| Version | Date       | Description                                                                                                     |
| ------- | ---------- | --------------------------------------------------------------------------------------------------------------- |
| 1.0.0   | 2026-06-26 | Initial Document Standard                                                                                       |
| 1.1.0   | 2026-06-27 | Added Document Header Rules, Markdown Compatibility Rules, YAML Front Matter Policy, Standard Document Template |

---

# New Section — Document Header Standard

모든 FRKP 문서는 동일한 Header 구조를 사용한다.

문서는 반드시 다음 순서로 시작해야 한다.

```markdown
# Document Title

## Document Information

| Item | Value |
|------|-------|
| Document ID | |
| Document Name | |
| Version | |
| Status | |
| Category | |
| Created | |
| Last Updated | |
```

Document Information은 모든 공식 문서의 필수 요소이다.

---

# New Section — YAML Front Matter Policy

FRKP는 YAML Front Matter를 사용하지 않는다.

다음 형식은 사용하지 않는다.

```yaml
---
title: Example
version: 1.0
---
```

YAML Front Matter는 Markdown Viewer, PDF 변환기, Word 변환기 및 일부 에디터에서 호환성 문제가 발생할 수 있으므로 FRKP 표준에서는 사용하지 않는다.

---

# New Section — Markdown Compatibility

모든 문서는 다음 환경에서 동일하게 표시되어야 한다.

* GitHub
* VS Code
* Obsidian
* Notepad++
* IntelliJ IDEA
* PDF 변환
* DOCX 변환
* LLM Processing

특정 Markdown 엔진에 종속되는 문법은 사용하지 않는다.

---

# New Section — Document Header Template

새 문서를 작성할 때는 다음 Header를 사용한다.

```markdown
# Document Title

## Document Information

| Item | Value |
|------|-------|
| Document ID | FRKP-XXX |
| Document Name | |
| Version | 1.0.0 |
| Status | Draft |
| Category | |
| Created | YYYY-MM-DD |
| Last Updated | YYYY-MM-DD |

---

# 1. Purpose
```

---

# New Section — Markdown Portability Principle

FRKP 문서는 특정 Markdown 구현체가 아닌 CommonMark 기반의 범용 Markdown을 우선한다.

다음 항목은 사용을 지양한다.

* YAML Front Matter
* Vendor-specific Extensions
* HTML 의존 레이아웃
* 플랫폼 전용 Markdown 확장

필요한 경우에도 범용 Markdown으로 대체 가능한 형식을 우선한다.

---

# New Section — Compatibility Checklist

새 문서를 작성할 때 다음 항목을 확인한다.

| Check Item              | Required |
| ----------------------- | :------: |
| Document Information 포함 |     ✔    |
| YAML Front Matter 미사용   |     ✔    |
| CommonMark 호환           |     ✔    |
| GitHub 표시 확인            |     ✔    |
| PDF 변환 가능               |     ✔    |
| DOCX 변환 가능              |     ✔    |
| Cross Reference 확인      |     ✔    |

---

# Summary Update

FRKP Document Standard Version 1.1.0은 프로젝트 전체 문서의 호환성과 일관성을 향상시키기 위해 Document Header 구조를 표준화하고, YAML Front Matter를 사용하지 않는 CommonMark 기반 문서 작성 원칙을 공식 채택한다.
