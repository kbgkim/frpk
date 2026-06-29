# FRKP-PROGRAM-000 — Financial Platform Publication Program

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PROGRAM-000 |
| Document Name | Financial Platform Publication Program |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance |
| Owner | FRKP Publishing Office |
| Plan | PLAN-022 |
| Related Documents | FRKP-PUB-000; FRKP-PUB-001; FRKP-PUB-002; FRKP-PROGRAM-001; FRKP-PROGRAM-002; FRKP-PROGRAM-003; FRKP-PROGRAM-004; FAEP-000; FAEP-001; FAEP-002; FRKP-003; FRKP-004; FRKP-005; FAEP-FOUNDATION-000; FRKP-FRKC-001; FRKP-DOC-100 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# 1. Purpose

This document establishes the **Financial Platform Publication Program** — the official Technical Publishing Program of the Financial Risk Knowledge Platform (FRKP).

The Publication Program governs how Financial Platform knowledge is transformed from source material into published technical handbooks. It defines the program structure, governance model, responsibilities, and relationships with all FAEP programs and platforms.

FRKP is the designated Technical Publishing Platform for the Financial Platform. This program formalises the repeatable publication process required before individual handbook volumes are produced.

---

# 2. Program Definition

## 2.1 FRKP as the Technical Publishing Program

FRKP operates as the official Technical Publishing Program under the FAEP Program hierarchy. Its mission is to publish the **Financial Platform Handbook** series — the authoritative technical reference for all Financial Platform implementations, with the IB Project as the primary downstream consumer.

| Aspect | Definition |
| --- | --- |
| Program Name | Financial Platform Publication Program |
| Operating Entity | Financial Risk Knowledge Platform (FRKP) |
| Program Type | Technical Publishing Program |
| Governance Parent | FAEP Program (FAEP-000, FAEP-001, FAEP-002) |
| Primary Output | Financial Platform Handbook (8 volumes) |
| Target Audience | IB Project implementers, risk engineers, platform architects, technical reviewers |
| Publication Standard | FRKP-PROGRAM-002 (Editorial Standard) |
| Quality Framework | FRKP-PROGRAM-004 (Publication Quality Gate) |
| Workflow | FRKP-PROGRAM-001 (Publication Workflow) |

## 2.2 Program Responsibilities

| Responsibility | Description |
| --- | --- |
| R-001 | Own the Financial Platform Handbook series end-to-end |
| R-002 | Define and maintain the publication governance framework |
| R-003 | Operate the publication workflow from knowledge extraction to official publication |
| R-004 | Enforce editorial standards across all published volumes |
| R-005 | Manage the publication backlog and prioritisation |
| R-006 | Conduct quality gates at every publication milestone |
| R-007 | Maintain traceability from source knowledge to published content |
| R-008 | Coordinate technical, architecture, and editorial reviews |
| R-009 | Certify volume freeze and authorise official publication |
| R-010 | Manage volume versioning, errata, and revision cycles |
| R-011 | Liaise with the IB Project on publication requirements and readiness |
| R-012 | Report publication status to the FAEP Program governance |

## 2.3 Program Governance

### 2.3.1 Governance Hierarchy

```
FAEP Program (FAEP-000, FAEP-001, FAEP-002)
  |
  +-- FAEP Core Standards (FAEP-STD-000 through FAEP-STD-006)
  |
  +-- FAEP Foundation (FAEP-FOUNDATION-000/001/002)
  |
  +-- FRKC Knowledge OS (FRKP-005)
  |
  +-- FRKP Publication Program (FRKP-PROGRAM-000 through FRKP-PROGRAM-004)
        |
        +-- Publication Workflow (FRKP-PROGRAM-001)
        +-- Editorial Standard (FRKP-PROGRAM-002)
        +-- Publication Backlog (FRKP-PROGRAM-003)
        +-- Publication Quality Gate (FRKP-PROGRAM-004)
        |
        +-- Active Volumes
              |
              +-- FP-VOL-001 through FP-VOL-008
```

### 2.3.2 Decision Authority

| Decision | Authority | Escalation |
| --- | --- | --- |
| Publication scope and backlog | FRKP Publishing Office | FAEP Program Board |
| Editorial standard changes | FRKP Publishing Office | FAEP Program Board |
| Volume freeze certification | Freeze Authority | FAEP Program Board |
| Official publication authorisation | FRKP Publishing Office | FAEP Program Board |
| Quality gate verdict appeal | Technical Reviewer + Editorial Reviewer | FAEP Architecture Board |
| Priority override | FRKP Publishing Office | FAEP Program Board |

---

# 3. Relationship Model

## 3.1 Relationship Overview

```
FAEP (Financial AI Engineering Platform)
  |
  +-- Defines platform architecture, core contracts, standards
  |
  +-- FRKC (Knowledge Operating System)
  |     |
  |     +-- Provides canonical knowledge objects
  |     +-- Provides certified evidence
  |     +-- Provides ontology and semantic model
  |     +-- **Source** of all published knowledge
  |
  +-- FRKP (Publication Program)
  |     |
  |     +-- Owns the Financial Platform Handbook
  |     +-- Operates the publication workflow
  |     +-- Enforces editorial standards
  |     +-- **Publisher** of all Financial Platform documentation
  |
  +-- Risk Platform (Reference Implementation)
  |     |
  |     +-- Provides source code, formulas, architecture
  |     +-- Validated against FAEP Core (PLAN-016)
  |     +-- **Reference Source** for technical content
  |
  +-- IB Project (First Consumer)
        |
        +-- Consumes the Financial Platform Handbook
        +-- Uses published volumes as IB Reference Materials
        +-- **Primary Audience** for all publications
```

## 3.2 Relationship with FAEP

FAEP is the architectural umbrella and program governance parent. The Publication Program operates within FAEP Foundation v1.0 boundaries and conforms to FAEP Core Standards, Navigation Standard (FAEP-STD-004), and Release/Freeze Standard (FAEP-STD-006).

| Aspect | Relationship |
| --- | --- |
| Governance | Publication Program reports to FAEP Program Governance |
| Standards | Publication Program conforms to FAEP Core Standards |
| Foundation | Operates within FAEP Foundation v1.0 frozen boundaries |
| Evolution | Publication governance may evolve per FAEP Foundation Evolution Policy |

## 3.3 Relationship with FRKC

FRKC is the authoritative knowledge source. Every published section in the Financial Platform Handbook must trace to at least one FRKC Knowledge Object. The Publication Program does not own knowledge — it owns the publication of knowledge.

| Aspect | Relationship |
| --- | --- |
| Knowledge Source | FRKC provides canonical knowledge objects |
| Evidence | FRKC provides certified evidence with traceability |
| Ontology | FRKC provides the semantic model for cross-references |
| Retrieval | FRKC provides semantic retrieval for content assembly |

## 3.4 Relationship with Risk Platform

The Risk Platform is the primary reference implementation and the richest source of technical content for the Handbook. Its source code, formulas, architecture decisions, and execution semantics provide the technical foundation for volumes FP-VOL-001 through FP-VOL-004.

| Aspect | Relationship |
| --- | --- |
| Technical Source | Risk Platform code, formulas, architecture |
| Validation Reference | Risk Platform validates FAEP Core contracts |
| Capability Provider | Risk Platform capabilities mapped to Handbook sections |

## 3.5 Relationship with IB Project

The IB Project is the first downstream consumer of the Financial Platform Handbook. All publication decisions consider IB Project readiness, requirements, and consumption model.

| Aspect | Relationship |
| --- | --- |
| Primary Audience | IB Project implementers and technical reviewers |
| Readiness Driver | IB Project bootstrapping timeline drives publication priority |
| Feedback Loop | IB Project review feeds into volume revisions |
| Integration | FP-VOL-008 (IB Integration Guide) is the direct bridge |

---

# 4. Publication Numbering

## 4.1 Numbering Principles

- All publication identifiers follow the FAEP-STD-001 Document Identification Standard.
- Identifiers are hierarchical and human-readable.
- Identifiers are stable after volume publication freeze.
- Reserved identifiers may not be reused after deprecation.

## 4.2 Identifier Patterns

| Element | Pattern | Example |
| --- | --- | --- |
| Financial Platform | `FP` | Financial Platform Handbook |
| Volume | `FP-VOL-{NNN}` | FP-VOL-001 — Platform Architecture |
| Chapter | `FP-VOL-{NNN}-CH-{NNN}` | FP-VOL-001-CH-002 — Platform Engine Model |
| Section | `FP-VOL-{NNN}-CH-{NNN}-SEC-{NNN}` | FP-VOL-001-CH-002-SEC-001 — Engine Taxonomy |
| Figure | `FP-VOL-{NNN}-FIG-{NNN}` | FP-VOL-001-FIG-003 — Engine Dependency Diagram |
| Table | `FP-VOL-{NNN}-TBL-{NNN}` | FP-VOL-001-TBL-002 — Contract Summary |
| Example | `FP-VOL-{NNN}-EX-{NNN}` | FP-VOL-002-EX-001 — Formula Compilation Walkthrough |
| Reference | `FP-VOL-{NNN}-REF-{NNN}` | FP-VOL-001-REF-001 — FAEP Master Architecture Document |
| Glossary Term | `FP-GLOSS-{TERM}` | FP-GLOSS-DETERMINISM |
| Appendix | `FP-VOL-{NNN}-APP-{NNN}` | FP-VOL-002-APP-001 — Grammar Reference |
| Index | `FP-VOL-{NNN}-IDX` | FP-VOL-003-IDX |

## 4.3 Numbering Rules

- Volume numbers are sequential: `001`, `002`, `003`...
- Chapter numbers restart at `001` within each volume.
- Section numbers restart at `001` within each chapter.
- Figure, Table, Example, and Reference numbers restart per volume.
- Numbers are zero-padded to exactly 3 digits for volumes, chapters, sections, figures, tables, examples, references, and appendices.
- Once assigned, numbers are permanent. A retired number may not be reassigned.

## 4.4 Version Numbers

Publication versions follow `vMAJOR.MINOR.PATCH`:

| Component | Rule |
| --- | --- |
| MAJOR | Structural change (chapter reorganisation, scope change) |
| MINOR | Content addition (new sections, significant revisions) |
| PATCH | Correction (errata, formatting, cross-reference fixes) |

- Version applies at the **volume level**. A chapter or section inherits its volume version.
- Version `v1.0.0` is the initial published release.
- Pre-publication drafts carry `v0.{N}.{M}`.
- Freeze candidates carry `v0.{N}.{M}-freeze-candidate`.

---

# 5. Publication Roles

| Role | Responsibility |
| --- | --- |
| FRKP Publishing Office | Program ownership, backlog management, publication authorisation |
| Volume Owner | End-to-end ownership of a specific volume |
| Technical Author | Writes draft content from knowledge extraction |
| Architecture Reviewer | Validates architectural consistency and FAEP compliance |
| Technical Reviewer | Validates technical accuracy against source |
| Editorial Reviewer | Validates editorial standard compliance |
| Freeze Authority | Certifies volume freeze and authorises publication |
| IB Project Liaison | Represents consumer requirements and reviews IB readiness |
| Quality Gate Reviewer | Assesses publication against quality gate criteria |

---

# 6. Program Artifacts

| Artifact | Location | Description |
| --- | --- | --- |
| FRKP-PROGRAM-000 | 00_Project_Management/Governance/ | Publication Program definition (this document) |
| FRKP-PROGRAM-001 | 00_Project_Management/Governance/ | Publication Workflow specification |
| FRKP-PROGRAM-002 | 00_Project_Management/Governance/ | Editorial Standard |
| FRKP-PROGRAM-003 | 00_Project_Management/Governance/ | Publication Backlog |
| FRKP-PROGRAM-004 | 00_Project_Management/Governance/ | Publication Quality Gate |
| FRKP-PUB-000 | 00_Project_Management/Governance/ | Financial Platform Publishing Architecture |
| FRKP-PUB-001 | 00_Project_Management/Governance/ | Knowledge Mapping Model |
| FRKP-PUB-002 | 00_Project_Management/Governance/ | Financial Platform Handbook Structure |
| FP-VOL-{NNN} | 11_Volumes/ | Published handbook volumes |

---

# 7. Preservation Commitment

This document does not modify:
- FAEP Foundation v1.0 frozen artifacts
- FAEP Core Contracts
- FAEP Standards (FAEP-STD-000 through FAEP-STD-006)
- FAEP Specifications (FRKP-003, FRKP-004, FRKP-005)
- FAEP Governance documents (FAEP-000, FAEP-001, FAEP-002)
- FAEP ADR Registry (FAEP-ADR-000)
- FAEP Contract Governance (FAEP-CONTRACT-000, FAEP-CONTRACT-001)
- FAEP Validation Framework (FAEP-VALIDATION-000, FAEP-VALIDATION-001)
- FAEP Foundation Governance (FAEP-FOUNDATION-000, FAEP-FOUNDATION-001, FAEP-FOUNDATION-002)
- FAEP Capability Discovery (FAEP-CAP-000, FAEP-CAP-001)
- Existing FRKP-PUB-000, FRKP-PUB-001, FRKP-PUB-002
- Bundle-007 frozen artifacts
- Existing Version 1.0.0 artifacts
- Bundle structure or repository layout

---

# 8. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Financial Platform Publication Program (PLAN-022) |
