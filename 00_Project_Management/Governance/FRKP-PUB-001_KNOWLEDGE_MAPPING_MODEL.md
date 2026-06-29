# FRKP-PUB-001 — Knowledge Mapping Model

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PUB-001 |
| Document Name | Knowledge Mapping Model |
| Version | 1.0.0 |
| Status | Active |
| Category | Publishing Architecture |
| Owner | FRKP Publishing Office |
| Plan | PLAN-021 |
| Related Documents | FRKP-PUB-000; FRKP-003; FRKP-004; FRKP-005; FAEP-CAP-000; FAEP-CAP-001; FRKP-FRKC-001; FRKP-DOC-100 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# 1. Purpose

This document defines the **Knowledge Mapping Model** — the methodology for transforming Risk Platform source knowledge into published Financial Platform Handbook content.

The model defines how source code, architecture decisions, formulas, capabilities, and runtime behaviors are systematically identified, extracted, classified, and published as structured knowledge in the Financial Platform Handbook.

---

# 2. Mapping Architecture

## 2.1 Source-to-Publication Chain

```
Source Code (Risk Platform repository)
  |
  |-- Code analysis
  |-- Architecture extraction
  |-- Formula identification
  v
Knowledge Object (FRKC canonical item)
  |
  |-- KO identification
  |-- Evidence mapping
  |-- Metadata assignment
  v
Capability (Candidate Capability)
  |
  |-- Capability classification
  |-- Provider/consumer mapping
  |-- Volume assignment
  v
Formula (canonical mathematical definition)
  |
  |-- Formula extraction
  |-- Symbol standardization
  |-- Implementation mapping
  v
Runtime (execution semantics)
  |
  |-- Determinism model
  |-- Execution mode mapping
  |-- Precision governance
  v
Document (published section)
  |
  |-- Section authoring
  |-- Cross-reference linking
  |-- Evidence citation
  v
Publication (Financial Platform Handbook volume)
  |
  |-- Volume assembly
  |-- Navigation generation
  |-- Freeze certification
```

## 2.2 Mapping Dimensions

| Dimension | Description | Source | Target |
| --- | --- | --- | --- |
| Structural | Code structure to architectural description | Packages, modules, classes | Architecture sections |
| Behavioral | Runtime behavior to execution documentation | Compilation, execution, governance | Runtime sections |
| Knowledge | Domain knowledge to knowledge objects | Formulas, regulations, concepts | Knowledge Platform volumes |
| Capability | Implementation patterns to capability definitions | Provider patterns, consumer interfaces | Capability registry |
| Traceability | Source-to-publication traceability | All source artifacts | Publication evidence citations |

---

# 3. Knowledge Extraction Methodology

## 3.1 Source Identification

| Source Type | Identification Method | Example |
| --- | --- | --- |
| Java Package | Directory structure analysis | `core:core-analysis/calculator/compiler/` |
| Java Class | Reflection and code analysis | `Lexer`, `Parser`, `CompilerPipeline` |
| Formula Definition | Mathematical extraction from code | `FC-471: Operational Risk Loss Distribution` |
| Architecture Pattern | Structural analysis | `Chain-of-responsibility: GovernanceGuard` |
| Configuration | Policy extraction | `Decimal128`, `HALF_EVEN` |
| Test Suite | Behavioral documentation | `DeterminismTest`, `LockdownTest` |

## 3.2 Knowledge Object Creation

Every extracted source artifact becomes a Knowledge Object (KO) in FRKC with:

| Field | Description | Example |
| --- | --- | --- |
| KO-ID | Unique knowledge object identifier | KO-EXE-001 |
| Source Reference | Source code location | `Risk Platform: core/core-analysis/calculator/compiler/Lexer.java` |
| Knowledge Domain | Domain classification | Execution |
| Capability Mapping | Related Candidate Capability | CAP-EXE-001 |
| Volume Assignment | Target handbook volume | FP-VOL-002 |
| Evidence Status | Evidence certification level | Certified |
| Version | Knowledge version number | 1.0.0 |

## 3.3 Extraction Rules

| Rule | Description |
| --- | --- |
| KR-001 | Extract only what exists in source code. Do not invent. |
| KR-002 | Every KO must reference a specific source location (file, line range, or commit). |
| KR-003 | Every KO must map to at least one Candidate Capability or be recorded as Backlog. |
| KR-004 | Mature patterns (production, tested) are extracted as primary KOs. |
| KR-005 | Experimental or speculative patterns are extracted as secondary KOs with maturity annotation. |

---

# 4. Capability Mapping

## 4.1 Mapping Method

Each of the 35 Candidate Capabilities (FAEP-CAP-001) is mapped to exactly one Volume, Chapter, and Section in the Financial Platform Handbook.

The mapping follows these rules:

| Rule | Description |
| --- | --- |
| CM-001 | Every Candidate Capability is assigned to exactly one primary Section. |
| CM-002 | A Capability may be referenced by secondary Sections as cross-reference. |
| CM-003 | The primary Section is where the Capability's implementation and behavior are fully described. |
| CM-004 | Cross-domain Capabilities appear in their primary domain's volume with cross-references. |

## 4.2 Full Capability Mapping Table

### Knowledge Domain (8 Capabilities)

| Capability ID | Title | Volume | Chapter | Section |
| --- | --- | --- | --- | --- |
| CAP-KNW-001 | Canonical Knowledge Storage | FP-VOL-005 | CH-01 — Knowledge OS Architecture | SEC-01 — Canonical Knowledge Model |
| CAP-KNW-002 | Evidence Registration & Mapping | FP-VOL-005 | CH-05 — Evidence Management | SEC-01 — Evidence Lifecycle |
| CAP-KNW-003 | Terminology Management | FP-VOL-005 | CH-03 — Knowledge Objects | SEC-02 — Terminology and Glossary |
| CAP-KNW-004 | Domain Classification | FP-VOL-005 | CH-02 — Knowledge Architecture | SEC-03 — Domain Scoping |
| CAP-KNW-005 | Knowledge Layering | FP-VOL-005 | CH-02 — Knowledge Architecture | SEC-01 — Layer Architecture |
| CAP-KNW-006 | Cross-Reference Linking | FP-VOL-005 | CH-04 — Ontology and Knowledge Graph | SEC-02 — Cross-Reference Model |
| CAP-KNW-007 | Metadata Enforcement | FP-VOL-005 | CH-03 — Knowledge Objects | SEC-01 — Metadata Schema |
| CAP-KNW-008 | Knowledge Versioning | FP-VOL-005 | CH-03 — Knowledge Objects | SEC-03 — Version Strategy |

### Publishing Domain (8 Capabilities)

| Capability ID | Title | Volume | Chapter | Section |
| --- | --- | --- | --- | --- |
| CAP-PUB-001 | Evidence-Driven Publishing Workflow | FP-VOL-006 | CH-05 — Evidence-Driven Publishing | SEC-01 — Workflow Definition |
| CAP-PUB-002 | Bundle Lifecycle Management | FP-VOL-006 | CH-03 — Bundle Lifecycle | SEC-01 — Lifecycle Stages |
| CAP-PUB-003 | Document Authoring & Publication | FP-VOL-006 | CH-04 — Document Authoring | SEC-01 — Authoring Process |
| CAP-PUB-004 | Navigation Index Management | FP-VOL-006 | CH-04 — Document Authoring | SEC-02 — Navigation Structure |
| CAP-PUB-005 | AI Agent Orchestration | FP-VOL-007 | CH-04 — AI Agent Operations | SEC-01 — Agent Framework |
| CAP-PUB-006 | Session Handoff & Restoration | FP-VOL-007 | CH-05 — Session Management | SEC-01 — Session Lifecycle |
| CAP-PUB-007 | Freeze Certification | FP-VOL-007 | CH-03 — Freeze Certification | SEC-01 — Certification Process |
| CAP-PUB-008 | Archive Management | FP-VOL-007 | CH-06 — Continuous Improvement | SEC-02 — Archive Strategy |

### Execution Domain (15 Capabilities)

| Capability ID | Title | Volume | Chapter | Section |
| --- | --- | --- | --- | --- |
| CAP-EXE-001 | DSL Compilation Pipeline | FP-VOL-002 | CH-03 — Compiler Pipeline | SEC-01 — Pipeline Architecture |
| CAP-EXE-002 | Deterministic Runtime Execution | FP-VOL-003 | CH-02 — Deterministic Execution | SEC-01 — Determinism Model |
| CAP-EXE-003 | Formula Governance Workflow | FP-VOL-002 | CH-06 — Formula Governance | SEC-01 — Lifecycle States |
| CAP-EXE-004 | Content-Addressed Execution Plans | FP-VOL-003 | CH-03 — Execution Plans | SEC-01 — Plan Structure |
| CAP-EXE-005 | Execution Mode Enforcement | FP-VOL-003 | CH-04 — Execution Modes | SEC-01 — Mode Taxonomy |
| CAP-EXE-006 | Policy-First Governance Guard | FP-VOL-003 | CH-02 — Deterministic Execution | SEC-03 — Governance Guards |
| CAP-EXE-007 | PLAN-based Execution | FP-VOL-007 | CH-01 — Platform Governance | SEC-03 — PLAN Execution Model |
| CAP-EXE-008 | Architecture Enforcement | FP-VOL-001 | CH-03 — Core Platform Specification | SEC-04 — Architecture Enforcement |
| CAP-EXE-009 | Release Snapshot Management | FP-VOL-007 | CH-02 — Release Management | SEC-02 — Snapshot Strategy |
| CAP-EXE-010 | Evidence-Gated Promotion | FP-VOL-002 | CH-06 — Formula Governance | SEC-03 — Promotion Workflow |
| CAP-EXE-011 | Dependency Impact Analysis | FP-VOL-002 | CH-05 — Optimization | SEC-03 — Dependency Analysis |
| CAP-EXE-012 | Variable Resolution | FP-VOL-003 | CH-06 — Variable System | SEC-01 — Resolution Strategy |
| CAP-EXE-013 | Variable Codec Serialization | FP-VOL-003 | CH-06 — Variable System | SEC-02 — Codec Architecture |
| CAP-EXE-014 | Numeric Precision Governance | FP-VOL-003 | CH-05 — Numeric Precision | SEC-01 — Precision Policy |
| CAP-EXE-015 | Operator Review & Governance Metrics | FP-VOL-007 | CH-01 — Platform Governance | SEC-04 — Governance Metrics |

### Governance Domain (5 Capabilities)

| Capability ID | Title | Volume | Chapter | Section |
| --- | --- | --- | --- | --- |
| CAP-GOV-001 | PLAN Governance Model | FP-VOL-007 | CH-01 — Platform Governance | SEC-03 — PLAN Governance Model |
| CAP-GOV-002 | Architecture Decision Records | FP-VOL-001 | CH-05 — Governance Integration | SEC-02 — ADR Framework |
| CAP-GOV-003 | Contract Lifecycle Governance | FP-VOL-001 | CH-03 — Core Platform Specification | SEC-02 — Contract Model |
| CAP-GOV-004 | Foundation Freeze & Evolution | FP-VOL-001 | CH-03 — Core Platform Specification | SEC-03 — Foundation Governance |
| CAP-GOV-005 | Reference Implementation Validation | FP-VOL-006 | CH-02 — Reference Implementation | SEC-01 — Validation Framework |

---

# 5. Knowledge Mapping Summary

## 5.1 Mapping by Source

| Source | Knowledge Objects | Capabilities | Volumes |
| --- | --- | --- | --- |
| FRKC Knowledge Corpus | 8 Knowledge Domain KOs | CAP-KNW-001 through 008 | FP-VOL-005 |
| FRKP Publishing Platform | 8 Publishing Domain KOs | CAP-PUB-001 through 008 | FP-VOL-006, FP-VOL-007 |
| Risk Platform Codebase | 15 Execution Domain KOs | CAP-EXE-001 through 015 | FP-VOL-001, FP-VOL-002, FP-VOL-003, FP-VOL-007 |
| FAEP Governance | 5 Governance Domain KOs | CAP-GOV-001 through 005 | FP-VOL-001, FP-VOL-006, FP-VOL-007 |
| **Total** | **36** | **35** | **8 Volumes** |

## 5.2 Mapping by Volume

| Volume | Capabilities | Chapters | Sections |
| --- | --- | --- | --- |
| FP-VOL-001 — Platform Architecture | CAP-EXE-008, CAP-GOV-002, CAP-GOV-003, CAP-GOV-004 | 6 | 18+ |
| FP-VOL-002 — Formula Engine | CAP-EXE-001, CAP-EXE-003, CAP-EXE-010, CAP-EXE-011 | 6 | 18+ |
| FP-VOL-003 — Risk Engine | CAP-EXE-002, CAP-EXE-004, CAP-EXE-005, CAP-EXE-006, CAP-EXE-012, CAP-EXE-013, CAP-EXE-014 | 6 | 18+ |
| FP-VOL-004 — Risk Solution | (domain-specific content from bundles) | 6 | 18+ |
| FP-VOL-005 — Knowledge Platform | CAP-KNW-001 through 008 | 6 | 18+ |
| FP-VOL-006 — Implementation Guide | CAP-PUB-001 through 004, CAP-GOV-005 | 6 | 18+ |
| FP-VOL-007 — Operations Guide | CAP-PUB-005 through 008, CAP-EXE-007, CAP-EXE-009, CAP-EXE-015, CAP-GOV-001 | 6 | 18+ |
| FP-VOL-008 — IB Integration Guide | (cross-references all capabilities) | 6 | 18+ |

---

# 6. Knowledge Object Registry (Conceptual)

## 6.1 Knowledge Object Template

Every Knowledge Object follows this structure:

```
KO-{DOMAIN}-{NNN}: Title
  Source: {source location}
  Capability: {CAP-ID}
  Volume: {FP-VOL-NNN}
  Chapter: {chapter name}
  Section: {section name}
  Evidence: {EVD-ID}
  Status: {Draft | Certified | Frozen}
```

## 6.2 Example Knowledge Objects

| KO-ID | Title | Source | Capability |
| --- | --- | --- | --- |
| KO-EXE-001 | DSL Compilation Pipeline | Risk Platform: core/core-analysis/calculator/compiler/ | CAP-EXE-001 |
| KO-EXE-002 | Deterministic Runtime | Risk Platform: runtime/execution/RuntimeCompiledPlan.java | CAP-EXE-002 |
| KO-EXE-004 | Content-Addressed Plans | Risk Platform: runtime/execution/RuntimeCompiledPlan.java | CAP-EXE-004 |
| KO-PUB-001 | Evidence-Driven Workflow | FRKP: FRKP-FRKC-001 | CAP-PUB-001 |
| KO-KNW-001 | Canonical Knowledge Storage | FRKC: knowledge objects lifecycle | CAP-KNW-001 |
| KO-GOV-001 | PLAN Governance Model | FRKP: PLAN_INDEX.md; Risk Platform: PLAN-NNN | CAP-GOV-001 |

---

# 7. Traceability Example

## 7.1 Full Traceability Chain

```
Source: Risk Platform — core/core-analysis/calculator/compiler/Lexer.java:42-156
  |
  v
Knowledge Object: KO-EXE-001 — DSL Compilation Pipeline
  |  EVD-000342: Lexer implementation verified
  v
Capability: CAP-EXE-001 — DSL Compilation Pipeline
  |  Registered in FAEP-CAP-001 as P1-Critical
  v
Formula: FC-471 — Operational Risk Loss Distribution
  |  Uses DSL syntax defined by compiler pipeline
  v
Runtime: Execution Plan with opcode IR
  |  SHA-256 content-addressed plan
  v
Document: FP-VOL-002-CH-003-SEC-001 — Pipeline Architecture
  |  Section authored with KO-EXE-001 as primary knowledge source
  v
Publication: FP-VOL-002 — Formula Engine
  |  Volume released as part of Financial Platform Handbook
  v
IB Requirement: IB-REQ-042 — Formula compilation must be deterministic
  |  Requirement satisfied by compiler pipeline architecture
```

---

# 8. Summary

FRKP-PUB-001 defines the Knowledge Mapping Model for transforming Risk Platform knowledge into Financial Platform Handbook publications. The model defines a 7-stage source-to-publication chain (Source Code → Knowledge Object → Capability → Formula → Runtime → Document → Publication), a complete capability mapping table assigning all 35 Candidate Capabilities to specific volumes, chapters, and sections, and a traceability model ensuring every publication artifact traces back to its source code origin.

---

# Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Knowledge Mapping Model (PLAN-021) |
