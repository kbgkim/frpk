# FRKP-PROGRAM-002 — Editorial Standard

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PROGRAM-002 |
| Document Name | Financial Platform Editorial Standard |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance |
| Owner | FRKP Publishing Office |
| Plan | PLAN-022 |
| Related Documents | FRKP-PROGRAM-000; FRKP-PROGRAM-001; FRKP-PROGRAM-003; FRKP-PROGRAM-004; FRKP-PUB-000; FRKP-PUB-002; FAEP-STD-004; FAEP-STD-001 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# 1. Purpose

This document defines the **Editorial Standard** for the Financial Platform Handbook. It establishes mandatory style, structure, terminology, and formatting rules that every published volume shall conform to.

Compliance with this standard is verified during the Editorial Review stage of the Publication Workflow (FRKP-PROGRAM-001).

---

# 2. Document Style

## 2.1 Markdown Standard

All content shall be authored in GitHub-Flavoured Markdown (GFM).

| Element | Convention |
| --- | --- |
| Heading 1 | `# Title` — One per document, the volume title |
| Heading 2 | `## Chapter Title` — One per chapter |
| Heading 3 | `### Section Title` — One per section |
| Heading 4 | `#### Subsection Title` — Avoid unless necessary |
| Heading 5 | `##### ` — Do not use |
| Heading 6 | `###### ` — Do not use |
| Bold | `**term**` — For emphasis, glossary term first use |
| Italic | `*term*` — For defined terms, cross-reference labels |
| Inline Code | `` `code` `` — For identifiers, file paths, commands |
| Code Block | ` ```language ` — With language identifier |
| Blockquote | `> ` — For warnings, notes, and callouts |
| Unordered List | `- ` — For bullet items |
| Ordered List | `1. ` — For sequential steps |
| Horizontal Rule | `---` — Between major sections only |
| Tables | GFM table syntax with header row |
| Links | `[text](target)` — With descriptive link text |

## 2.2 Heading Rules

- Every volume has exactly one `#` heading (the volume title).
- Every chapter has exactly one `##` heading.
- Every section has exactly one `###` heading.
- Subsections (`####`) are optional and should be used sparingly.
- Headings must not contain code, links, or special characters.
- Heading text uses Title Case (capitalise major words).

## 2.3 Line Length

- Target line length: 100 characters maximum.
- No line may exceed 120 characters.
- Break lines at natural boundaries (sentence endings, clause boundaries).

## 2.4 Paragraph Rules

- One blank line between paragraphs.
- One blank line before and after code blocks, tables, lists, and blockquotes.
- No trailing whitespace.

---

# 3. Terminology

## 3.1 Term Consistency

- Every technical term must be used consistently throughout the Handbook.
- The first use of a glossary term in each volume must use bold formatting.
- Abbreviations must be defined on first use in each volume: `Deterministic Execution (DE)`.
- After definition, use the abbreviation consistently.

## 3.2 Prohibited Patterns

| Pattern | Correction |
| --- | --- |
| "We" | Use "the platform", "the engine", "the implementation" |
| "You" | Use "the implementer", "the consumer" |
| "Obviously" | Remove or replace with factual statement |
| "Simply" | Remove or replace with "is" |
| "Note that" | Remove; the statement is the note |
| "It is important to" | Remove; state the fact directly |
| "Should" | Use "shall" for requirements, "may" for optional, "must" for mandatory |
| Vague quantifiers | Use specific numbers or ranges instead of "many", "some", "several" |

## 3.3 FAEP Terminology

The following terms have specific meaning in the Financial Platform context and must be used in accordance with their FAEP definitions:

| Term | Definition Reference |
| --- | --- |
| Platform | FAEP — Financial AI Engineering Platform |
| Knowledge OS | FRKC — Knowledge Operating System |
| Publishing Platform | FRKP — Financial Risk Knowledge Platform |
| Reference Implementation | FAEP-000 definition |
| Core Contract | FRKP-004 definition |
| Candidate Contract | FAEP-CONTRACT-000 definition |
| Knowledge Object | FRKP-005 definition |
| Evidence | FAEP-STD-003 definition |
| Bundle | FAEP-STD-002 definition |
| Capability | FAEP-CAP-000 definition |

---

# 4. Cross-References

## 4.1 Reference Format

All cross-references within the Handbook must use the following format:

| Target Type | Format | Example |
| --- | --- | --- |
| Volume | [Volume Title](FP-VOL-{NNN}) | [Platform Architecture](FP-VOL-001) |
| Chapter | [Chapter Title](FP-VOL-{NNN}-CH-{NNN}) | [Engine Model](FP-VOL-001-CH-002) |
| Section | [Section Title](FP-VOL-{NNN}-CH-{NNN}-SEC-{NNN}) | [Engine Taxonomy](FP-VOL-001-CH-002-SEC-001) |
| Figure | [Figure {NNN}](FP-VOL-{NNN}-FIG-{NNN}) | [Figure 3](FP-VOL-001-FIG-003) |
| Table | [Table {NNN}](FP-VOL-{NNN}-TBL-{NNN}) | [Table 2](FP-VOL-001-TBL-002) |
| Example | [Example {NNN}](FP-VOL-{NNN}-EX-{NNN}) | [Example 1](FP-VOL-002-EX-001) |
| External document | [Document Title](path/to/document.md) | [FAEP Master Architecture](../../Governance/FRKP-003.md) |

## 4.2 Reference Rules

- Every cross-reference must resolve to an existing target at the time of publication.
- Cross-references to sections in other volumes must include the volume identifier.
- Cross-references to sections within the same volume may use relative section IDs.
- Dead links are not permitted. All links are validated during Editorial Review.
- External document references must use relative paths from the publishing directory.

---

# 5. Traceability

## 5.1 Knowledge Object Traceability

Every section must include a Knowledge Object Reference block immediately after the section heading:

```
### Knowledge Object References
| KO ID | Title |
| --- | --- |
| KO-KNW-001 | Canonical Knowledge Storage |
| KO-EVD-002 | Evidence Certification Standard |
```

## 5.2 Capability Traceability

Every section must include a Capability Mapping block:

```
### Capability Mapping
| CAP ID | Title |
| --- | --- |
| CAP-KNW-001 | Canonical Knowledge Model |
| CAP-PUB-001 | Evidence-Driven Publishing Workflow |
```

## 5.3 Evidence Traceability

Every section must include an Evidence block listing all evidence items supporting the section content:

```
### Evidence
| EVD ID | Description |
| --- | --- |
| EVD-000340 | FRKC Evidence Certification Record |
| EVD-000345 | Knowledge Object Version Policy |
```

## 5.4 Traceability Rules

- Every section must reference at least one Knowledge Object.
- Every Knowledge Object reference must resolve to a valid KO identifier.
- Every Capability reference must resolve to a valid CAP identifier in FAEP-CAP-001.
- Every Evidence reference must resolve to a valid EVD identifier in FRKC.
- Traceability blocks may be omitted for introductory or summary sections with Publishing Office approval.

---

# 6. Figures

## 6.1 Figure Rules

- Figures include diagrams, charts, screenshots, and architectural illustrations.
- Every figure must have a caption.
- Figure numbering resets per volume.
- Figure format: `![Figure {NNN}: {Caption}](path/to/figure.png)`
- Figures must use SVG format for diagrams, PNG for screenshots.
- Source files for SVG diagrams must be committed alongside the published figure.
- Maximum figure width: 800 pixels (SVG viewport).
- Figures must be referenced in the text before they appear.

## 6.2 Figure Placement

```
[Text referring to the figure context...]

![Figure 1: FAEP Engine Dependency Diagram](figures/FP-VOL-001-FIG-001.svg)

[Text continuing after the figure...]
```

## 6.3 Figure Numbering Table

Every volume must include a Figure Index at the end:

```
# Figures

| Figure | Title |
| --- | --- |
| 1 | FAEP Engine Dependency Diagram |
| 2 | Core Contract Lifecycle |
```

---

# 7. Tables

## 7.1 Table Rules

- Every table must have a caption.
- Table numbering resets per volume.
- Table format: Standard GFM table with header row.
- Column alignment must be specified where content requires it.
- Tables must not contain blank cells. Use `—` or `N/A`.
- Tables wider than 120 characters must be reformatted or split.

## 7.2 Table Format

```
### Table {NNN}: {Caption}

| Header 1 | Header 2 | Header 3 |
| --- | --- | --- |
| Value 1 | Value 2 | Value 3 |
```

## 7.3 Table Numbering Table

Every volume must include a Table Index at the end:

```
# Tables

| Table | Title |
| --- | --- |
| 1 | Core Contract Summary |
| 2 | Engine Responsibility Matrix |
```

---

# 8. Examples

## 8.1 Example Rules

- Examples illustrate concepts, workflows, or usage patterns.
- Every example must have a caption.
- Example numbering resets per volume.
- Example format: Code block or structured text with caption.
- Examples must be self-contained and verifiable.

## 8.2 Example Format

```
**Example {NNN}: {Caption}**

```language
{example code or structured content}
```
```

## 8.3 Example Numbering Table

Every volume must include an Example Index at the end:

```
# Examples

| Example | Title |
| --- | --- |
| 1 | Formula Compilation Walkthrough |
| 2 | Evidence Registration Workflow |
```

---

# 9. Glossary

## 9.1 Volume Glossary

Each volume must include a Glossary section listing all technical terms introduced or used in that volume.

## 9.2 Glossary Format

```
# Glossary

| Term | Definition | Cross-Reference |
| --- | --- | --- |
| Deterministic Execution | Execution that produces identical results given identical inputs | FP-VOL-003-CH-002 |
| Knowledge Object | A canonical knowledge artifact within FRKC | FP-VOL-005-CH-003 |
```

## 9.3 Glossary Rules

- Every term in bold within the volume must appear in the Glossary.
- Definitions must be self-contained (no forward references to other glossary terms).
- Cross-references to Handbook sections where the term is explained are recommended.

---

# 10. References

## 10.1 Reference Section

Each volume must include a References section listing all external documents, standards, and sources cited.

## 10.2 Reference Format

```
# References

| ID | Title | Source | Version |
| --- | --- | --- | --- |
| FP-VOL-001-REF-001 | FAEP Master Architecture | FRKP-003 | 1.0.0 |
| FP-VOL-001-REF-002 | FAEP Core Platform Specification | FRKP-004 | 1.0.0 |
```

## 10.3 Reference Rules

- References use the `FP-VOL-{NNN}-REF-{NNN}` identifier pattern.
- External references (regulations, standards) use full citation format.
- Internal references to FAEP/FRKP documents use document ID and version.

---

# 11. Versioning

## 11.1 Volume Version

Each published volume carries a version number as defined in FRKP-PROGRAM-000 Section 4.4.

## 11.2 Version Block

Every volume document must include a version information block after the title:

```
## Document Information

| Item | Value |
| --- | --- |
| Volume ID | FP-VOL-{NNN} |
| Volume Name | {Volume Title} |
| Version | v1.0.0 |
| Status | Published |
| Publication Date | YYYY-MM-DD |
| Owner | {Volume Owner} |
| Related Documents | {list of related document IDs} |
```

## 11.3 Revision History

Every volume must include a revision history table at the end:

```
## Revision History

| Version | Date | Description |
| --- | --- | --- |
| v1.0.0 | YYYY-MM-DD | Initial publication |
```

---

# 12. Navigation

## 12.1 Volume Navigation

Every volume must begin with a Navigation section showing the volume structure:

```
# Navigation

## Chapter Index

| Chapter | Title |
| --- | --- |
| CH-01 | Chapter One Title |
| CH-02 | Chapter Two Title |
| CH-03 | Chapter Three Title |

## Section Index

| Chapter | Section | Title |
| --- | --- | --- |
| CH-01 | SEC-01 | Section One Title |
| CH-01 | SEC-02 | Section Two Title |
```

## 12.2 Navigation Rules

- Navigation must be complete and accurate at time of publication.
- Navigation entries must match actual heading text.
- Navigation is validated during Editorial Review.

---

# 13. Reading Order

## 13.1 Volume Structure

Each volume shall follow this structural reading order:

1. Title and Document Information
2. Navigation (Chapter and Section Index)
3. Foreword or Preface (optional)
4. Chapter 1 (always the introductory chapter)
5. Chapter 2..N (content chapters)
6. Figures Index
7. Tables Index
8. Examples Index
9. Glossary
10. References
11. Revision History

## 13.2 Reading Order Rules within Sections

Each section shall follow this internal order:

1. Section heading
2. Knowledge Object References block
3. Capability Mapping block
4. Evidence block
5. Content (prose, figures, tables, examples)
6. Cross-References to related sections (optional)
7. IB Relevance block (explanation of relevance to IB Project)

---

# 14. Compliance

## 14.1 Compliance Levels

| Level | Meaning |
| --- | --- |
| MUST | Mandatory requirement. Non-compliance blocks publication. |
| SHOULD | Recommended requirement. Non-compliance requires documented justification. |
| MAY | Optional requirement. At author's discretion. |

## 14.2 Editorial Review

Compliance with this standard is verified during the Editorial Review stage (FRKP-PROGRAM-001 Section 3.5). The Editorial Reviewer may issue PASS, CONDITIONAL PASS, or FAIL based on compliance assessment.

---

# 15. Preservation Commitment

This document does not modify any FAEP Foundation, Core Contract, Standard, Specification, Governance, frozen bundle, or Version 1.0.0 artifact.

---

# 16. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Editorial Standard (PLAN-022) |
