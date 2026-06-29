# FRKP-PUB-002 — Financial Platform Handbook Structure

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PUB-002 |
| Document Name | Financial Platform Handbook Structure |
| Version | 1.0.0 |
| Status | Active |
| Category | Publishing Architecture |
| Owner | FRKP Publishing Office |
| Plan | PLAN-021 |
| Related Documents | FRKP-PUB-000; FRKP-PUB-001; FRKP-003; FRKP-004; FRKP-005; FAEP-CAP-001; FRKP-FRKC-001 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# 1. Purpose

This document defines the complete **Financial Platform Handbook Structure** — the volume, chapter, and section architecture for the official Financial Platform publication.

The Handbook is the authoritative technical reference for all Financial Platform implementations, with the IB Project as the primary downstream consumer. Every volume, chapter, and section is justified, mapped to source capabilities, and assigned a publication priority.

---

# 2. Handbook Overview

| Property | Value |
| --- | --- |
| Publication Name | Financial Platform Handbook |
| Publisher | FRKP (Financial Risk Knowledge Platform) |
| Target Audience | IB Project implementers, risk engineers, platform architects, technical reviewers |
| Volumes | 8 |
| Chapters per Volume | 6 |
| Estimated Total Sections | 144+ |
| Source Platforms | Risk Platform, FRKC, FRKP, FAEP |
| Publication Format | Structured markdown with navigation, cross-references, and evidence citations |

---

# 3. Volume Structure

## FP-VOL-001 — Platform Architecture

**Purpose:** Define the FAEP umbrella architecture, engine model, core contracts, and platform governance structure.

**Justification:** Every platform decision depends on architectural foundations. This volume defines the structural framework that all other volumes reference. Without it, readers cannot understand how engines, contracts, and governance relate.

**Source Evidence:** FRKP-003 (FAEP Master Architecture), FRKP-004 (FAEP Core Platform Specification), PLAN-011, PLAN-012, PLAN-016

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | FAEP Master Architecture | SEC-01 — Platform Vision and Philosophy; SEC-02 — Program Hierarchy; SEC-03 — Engine Model; SEC-04 — Repository Strategy |
| CH-02 | Platform Engine Model | SEC-01 — Engine Taxonomy; SEC-02 — Engine Contracts; SEC-03 — Plugin Architecture; SEC-04 — Engine Lifecycle |
| CH-03 | Core Platform Specification | SEC-01 — Core Contracts; SEC-02 — Contract Lifecycle (CAP-GOV-003); SEC-03 — Foundation Governance (CAP-GOV-004); SEC-04 — Architecture Enforcement (CAP-EXE-008) |
| CH-04 | Integration Architecture | SEC-01 — Platform Integration Points; SEC-02 — Data Flow Model; SEC-03 — Dependency Management |
| CH-05 | Governance Integration | SEC-01 — Standards Framework; SEC-02 — ADR Framework (CAP-GOV-002); SEC-03 — Review and Certification |
| CH-06 | Platform Evolution | SEC-01 — Version Strategy; SEC-02 — Migration Paths; SEC-03 — Future Roadmap |

**Capabilities Mapped:** CAP-EXE-008, CAP-GOV-002, CAP-GOV-003, CAP-GOV-004

---

## FP-VOL-002 — Formula Engine

**Purpose:** Document the formula language, compiler pipeline, optimization, and formula governance.

**Justification:** The Risk Platform's most sophisticated capability is its formula engine — a multi-stage compilation pipeline from domain-specific language to deterministic execution. This volume documents the complete formula lifecycle.

**Source Evidence:** Risk Platform compiler (Lexer, Parser, AST, Optimizer, Canonical Plan), PLAN-016, FAEP-CAND-001, FAEP-CAND-002

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | Formula Language | SEC-01 — Language Syntax; SEC-02 — Type System; SEC-03 — Expression Model; SEC-04 — Domain-Specific Constructs |
| CH-02 | Lexical and Syntactic Analysis | SEC-01 — Lexer Architecture; SEC-02 — Parser Design; SEC-03 — AST Structure; SEC-04 — Error Handling |
| CH-03 | Compiler Pipeline | SEC-01 — Pipeline Architecture (CAP-EXE-001); SEC-02 — Semantic Validation; SEC-03 — Intermediate Representation |
| CH-04 | Compiler Optimization | SEC-01 — Optimization Passes; SEC-02 — Constant Folding; SEC-03 — Dead Code Elimination |
| CH-05 | Canonical Plan Generation | SEC-01 — Plan Structure; SEC-02 — Opcode IR; SEC-03 — Dependency Analysis (CAP-EXE-011) |
| CH-06 | Formula Governance | SEC-01 — Lifecycle States (CAP-EXE-003); SEC-02 — Maker-Checker Workflow; SEC-03 — Promotion Workflow (CAP-EXE-010) |

**Capabilities Mapped:** CAP-EXE-001, CAP-EXE-003, CAP-EXE-010, CAP-EXE-011

---

## FP-VOL-003 — Risk Engine

**Purpose:** Describe deterministic runtime execution, execution plans, modes, precision, and variable resolution.

**Justification:** The runtime execution layer makes formulas computable. Determinism, execution plans, modes, and numeric precision are engineering concerns that every platform implementer must understand.

**Source Evidence:** Risk Platform runtime (RuntimeCompiledPlan, CalculationContext, VariableResolver), PLAN-016, FAEP-CAND-003, FAEP-CAND-007

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | Runtime Architecture | SEC-01 — Runtime Engine Model; SEC-02 — Execution Lifecycle; SEC-03 — Sandbox Architecture |
| CH-02 | Deterministic Execution | SEC-01 — Determinism Model (CAP-EXE-002); SEC-02 — SHA-256 Content Addressing; SEC-03 — Governance Guards (CAP-EXE-006) |
| CH-03 | Execution Plans | SEC-01 — Plan Structure (CAP-EXE-004); SEC-02 — Caching Strategy; SEC-03 — Replay Verification |
| CH-04 | Execution Modes | SEC-01 — Mode Taxonomy (CAP-EXE-005); SEC-02 — Mode-Specific Policies; SEC-03 — Governance Integration |
| CH-05 | Numeric Precision | SEC-01 — Precision Policy (CAP-EXE-014); SEC-02 — Decimal128 Standard; SEC-03 — Rounding and Overflow |
| CH-06 | Variable System | SEC-01 — Resolution Strategy (CAP-EXE-012); SEC-02 — Codec Architecture (CAP-EXE-013); SEC-03 — Multi-Context Lookup |

**Capabilities Mapped:** CAP-EXE-002, CAP-EXE-004, CAP-EXE-005, CAP-EXE-006, CAP-EXE-012, CAP-EXE-013, CAP-EXE-014

---

## FP-VOL-004 — Risk Solution

**Purpose:** Present domain-specific risk solutions: market risk, credit risk, operational risk, liquidity, ICAAP, stress testing.

**Justification:** The primary business-facing volume. Domain experts and risk practitioners need comprehensive treatments of each risk domain.

**Source Evidence:** FRKP Bundles 1-7, Risk Platform calculator implementations, regulatory texts

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | Market Risk | SEC-01 — Basel III Framework; SEC-02 — FRTB Standardized Approach; SEC-03 — FRTB Internal Models; SEC-04 — Market Risk SA |
| CH-02 | Credit Risk | SEC-01 — IFRS 9 Framework; SEC-02 — Expected Credit Loss; SEC-03 — SA-CCR; SEC-04 — CVA |
| CH-03 | Operational Risk | SEC-01 — Operational Risk Framework; SEC-02 — Standardized Measurement Approach; SEC-03 — Loss Distribution |
| CH-04 | Liquidity Risk | SEC-01 — LCR; SEC-02 — NSFR; SEC-03 — Liquidity Monitoring |
| CH-05 | ICAAP | SEC-01 — ICAAP Framework; SEC-02 — Capital Planning; SEC-03 — Stress Testing Integration |
| CH-06 | Stress Testing | SEC-01 — Scenario Design; SEC-02 — Capital Adequacy; SEC-03 — Reverse Stress Testing |

**Capabilities Mapped:** (Domain-specific; cross-refers to execution capabilities)

---

## FP-VOL-005 — Knowledge Platform

**Purpose:** Define the FRKC Knowledge Operating System, knowledge objects, ontology, evidence management, and semantic retrieval.

**Justification:** The knowledge foundation that underpins every publication. FRKC is the authoritative knowledge source; this volume documents how knowledge is structured, versioned, and retrieved.

**Source Evidence:** FRKP-005 (FRKC Knowledge OS), FRKC repository, FAEP-CAP-001 Knowledge Domain

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | Knowledge OS Architecture | SEC-01 — Canonical Knowledge Model (CAP-KNW-001); SEC-02 — Knowledge Philosophy; SEC-03 — Platform Responsibilities; SEC-04 — Architecture Layers |
| CH-02 | Knowledge Architecture | SEC-01 — Layer Architecture (CAP-KNW-005); SEC-02 — Knowledge Hierarchy; SEC-03 — Domain Scoping (CAP-KNW-004) |
| CH-03 | Knowledge Objects | SEC-01 — Metadata Schema (CAP-KNW-007); SEC-02 — Terminology and Glossary (CAP-KNW-003); SEC-03 — Version Strategy (CAP-KNW-008); SEC-04 — Object Lifecycle |
| CH-04 | Ontology and Knowledge Graph | SEC-01 — Ontology Principles; SEC-02 — Cross-Reference Model (CAP-KNW-006); SEC-03 — Graph Traversal |
| CH-05 | Evidence Management | SEC-01 — Evidence Lifecycle (CAP-KNW-002); SEC-02 — Evidence Graph; SEC-03 — Certification Workflow |
| CH-06 | Semantic Retrieval and AI | SEC-01 — Retrieval Architecture; SEC-02 — Multi-Strategy Ranking; SEC-03 — AI Context Assembly |

**Capabilities Mapped:** CAP-KNW-001 through CAP-KNW-008

---

## FP-VOL-006 — Implementation Guide

**Purpose:** Provide reference implementation methodology, bundle lifecycle, document authoring, and evidence-driven publishing.

**Justification:** Practical methodology for building FAEP-conformant implementations. Every project needs a repeatable process for knowledge engineering, bundle management, and evidence-driven publishing.

**Source Evidence:** FRKP-FRKC-001, FAEP-VALIDATION-000/001, Bundle-007 lifecycle, FRKP bundle execution

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | Platform Bootstrap | SEC-01 — Bootstrap Methodology; SEC-02 — Repository Setup; SEC-03 — Governance Scaffolding |
| CH-02 | Reference Implementation | SEC-01 — Validation Framework (CAP-GOV-005); SEC-02 — Maturity Model; SEC-03 — Score Model |
| CH-03 | Bundle Lifecycle | SEC-01 — Lifecycle Stages (CAP-PUB-002); SEC-02 — Boundary Review; SEC-03 — Knowledge and Evidence Reviews |
| CH-04 | Document Authoring | SEC-01 — Authoring Process (CAP-PUB-003); SEC-02 — Navigation Structure (CAP-PUB-004); SEC-03 — Template Compliance |
| CH-05 | Evidence-Driven Publishing | SEC-01 — Workflow Definition (CAP-PUB-001); SEC-02 — Evidence Mapping; SEC-03 — Publication Review |
| CH-06 | Quality Assurance | SEC-01 — Standards Compliance; SEC-02 — Link Validation; SEC-03 — Consistency Checking |

**Capabilities Mapped:** CAP-PUB-001, CAP-PUB-002, CAP-PUB-003, CAP-PUB-004, CAP-GOV-005

---

## FP-VOL-007 — Operations Guide

**Purpose:** Cover platform governance, release management, freeze certification, AI agent operations, and session management.

**Justification:** Governance and operational procedures for running the platform. Freeze certification, release management, AI agent operations, and continuous improvement are essential for platform sustainability.

**Source Evidence:** FRKP-002, FAEP-STD-006, FAEP-STD-002, PLAN lifecycle (PLAN-001 through PLAN-020), FRKP-FREEZE-001

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | Platform Governance | SEC-01 — Governance Framework; SEC-02 — Decision Authority; SEC-03 — PLAN Execution Model (CAP-EXE-007, CAP-GOV-001); SEC-04 — Governance Metrics (CAP-EXE-015) |
| CH-02 | Release Management | SEC-01 — Release Lifecycle; SEC-02 — Snapshot Strategy (CAP-EXE-009); SEC-03 — Release Verification |
| CH-03 | Freeze Certification | SEC-01 — Certification Process (CAP-PUB-007); SEC-02 — Evidence Baseline; SEC-03 — Risk and Deferred Items |
| CH-04 | AI Agent Operations | SEC-01 — Agent Framework (CAP-PUB-005); SEC-02 — Task Orchestration; SEC-03 — Human Supervision |
| CH-05 | Session Management | SEC-01 — Session Lifecycle (CAP-PUB-006); SEC-02 — Agent Handoff; SEC-03 — Restoration Protocol |
| CH-06 | Continuous Improvement | SEC-01 — Feedback Loop; SEC-02 — Archive Strategy (CAP-PUB-008); SEC-03 — Lessons Learned |

**Capabilities Mapped:** CAP-PUB-005, CAP-PUB-006, CAP-PUB-007, CAP-PUB-008, CAP-EXE-007, CAP-EXE-009, CAP-EXE-015, CAP-GOV-001

---

## FP-VOL-008 — IB Integration Guide

**Purpose:** Guide the integration of IB Project as the first downstream consumer of the Financial Platform.

**Justification:** The final volume bridges the Financial Platform Handbook to its primary consumer. The IB Project represents the first real-world validation of the publishing architecture.

**Source Evidence:** IB Project requirements (anticipated), FAEP-000 program charter, FAEP-001 program roadmap, PLAN-016 validation findings

| Chapter | Title | Key Sections |
| --- | --- | --- |
| CH-01 | IB Project Overview | SEC-01 — Project Scope; SEC-02 — FAEP Compliance Requirements; SEC-03 — Integration Timeline |
| CH-02 | Knowledge Integration | SEC-01 — FRKC Knowledge Access; SEC-02 — Terminology Alignment; SEC-03 — Evidence Traceability |
| CH-03 | Formula and Engine Integration | SEC-01 — Formula Language Adoption; SEC-02 — Compiler Integration; SEC-03 — Runtime Binding |
| CH-04 | Risk Analytics Integration | SEC-01 — Risk Solution Adaptation; SEC-02 — Calculation Workflow; SEC-03 — Output Harmonization |
| CH-05 | Governance Integration | SEC-01 — FAEP Standard Compliance; SEC-02 — Review and Certification; SEC-03 — ADR Alignment |
| CH-06 | IB Reference Materials | SEC-01 — Handbook-to-IB Mapping; SEC-02 — Customization Guide; SEC-03 — FAQ and Troubleshooting |

**Capabilities Mapped:** (Cross-references all capabilities; IB-specific mappings to be defined during IB Project bootstrap)

---

# 4. Volume Dependency Graph

```
FP-VOL-005 (Knowledge Platform)
  |
  |  provides knowledge model
  v
FP-VOL-001 (Platform Architecture)
  |
  |  provides architectural context
  v
FP-VOL-002 (Formula Engine) --> FP-VOL-003 (Risk Engine)
  |                               |
  |  provides formulas            |  provides runtime
  v                               v
FP-VOL-004 (Risk Solution)
  |
  |  provides domain content
  v
FP-VOL-006 (Implementation Guide) --> FP-VOL-007 (Operations Guide)
  |                                     |
  |  provides methodology               |  provides procedures
  v                                     v
FP-VOL-008 (IB Integration Guide)
```

---

# 5. Publication Priority

| Priority | Volume | Dependencies | Target Duration |
| --- | --- | --- | --- |
| 1 | FP-VOL-005 — Knowledge Platform | None | 4 weeks |
| 2 | FP-VOL-001 — Platform Architecture | FP-VOL-005 | 4 weeks |
| 3 | FP-VOL-002 — Formula Engine | FP-VOL-001 | 6 weeks |
| 4 | FP-VOL-003 — Risk Engine | FP-VOL-001, FP-VOL-002 | 6 weeks |
| 5 | FP-VOL-004 — Risk Solution | FP-VOL-003 | 8 weeks |
| 6 | FP-VOL-006 — Implementation Guide | FP-VOL-001 | 4 weeks |
| 7 | FP-VOL-007 — Operations Guide | FP-VOL-001 | 4 weeks |
| 8 | FP-VOL-008 — IB Integration Guide | All prior volumes | 4 weeks |

---

# 6. Section Template

Every section in the Handbook follows this structure:

```
## {Section Title}

### Knowledge Object Reference
KO-{DOMAIN}-{NNN}: {Knowledge Object Title}

### Capability Mapping
CAP-{DOMAIN}-{NNN}: {Capability Title}

### Evidence
EVD-{NNN}: {Evidence Description}

### Content
{Section content — architecture, behavior, implementation, usage}

### Cross-References
- {Related section reference}
- {Related knowledge object reference}
- {Related capability reference}

### IB Relevance
{Explanation of relevance to IB Project implementers}
```

---

# 7. Summary

FRKP-PUB-002 defines the complete Financial Platform Handbook Structure with 8 volumes, 48 chapters, and 144+ sections. Each volume is justified with source evidence, capability mapping, and target audience. Volume-5 (Knowledge Platform) is recommended as the first publication pilot. The volume dependency graph ensures logical reading order for IB Project implementers.

---

# Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Financial Platform Handbook Structure (PLAN-021) |
