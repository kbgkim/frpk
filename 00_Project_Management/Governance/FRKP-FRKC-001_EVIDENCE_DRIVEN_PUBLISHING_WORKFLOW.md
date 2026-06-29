# FRKP-FRKC-001 — Evidence-Driven Publishing Workflow

## Financial Risk Knowledge Platform (FRKP)

---

# Document Information

| Item          | Value                                                                          |
| ------------- | ------------------------------------------------------------------------------ |
| Document ID   | FRKP-FRKC-001                                                                  |
| Document Name | Evidence-Driven Publishing Workflow                                            |
| Version       | 1.0.0                                                                          |
| Status        | Active                                                                         |
| Created       | 2026-06-28                                                                     |
| Purpose       | Define the standard workflow for publishing FRKP documents using FRKC evidence |

---

# 1. Purpose

This document defines the standard publishing workflow between the Financial Risk Knowledge Corpus (FRKC) and the Financial Risk Knowledge Platform (FRKP).

Its purpose is to ensure that every published document is:

* Evidence-backed
* Traceable
* Reproducible
* Consistent with project governance

---

# 2. Scope

This workflow applies to every new FRKP document, including:

* Reference Library (RL)
* Knowledge Base (KB)
* Analysis (AN)
* Mathematical Foundation (MF)
* Formula Catalog (FC)
* Implementation Guide (IMP)
* Architecture (ARCH)
* Bundle Review

---

# 3. Publishing Philosophy

The platform follows one fundamental rule.

> Knowledge is created and maintained in FRKC.
> Knowledge is published in FRKP.

FRKC is the authoritative knowledge source.

FRKP is the publishing platform.

---

# 4. Overall Workflow

```text
Original Source Documents
        │
        ▼
FRKC
  Metadata
  Semantic Extraction
  Knowledge Graph
  Canonical Concepts
  Evidence Bundles
  Publishing Mapping
        │
        ▼
Publishing Preparation
        │
        ▼
ChatGPT Editorial Review
        │
        ▼
Human Technical Review
        │
        ▼
FRKP Publication
```

---

# 5. Roles and Responsibilities

## FRKC

Responsibilities:

* Preserve source knowledge
* Manage canonical concepts
* Maintain evidence bundles
* Maintain publishing mappings
* Provide traceability

FRKC never publishes documents directly.

---

## Codex

Responsibilities:

* Repository-wide generation
* Metadata generation
* Mapping generation
* Validation
* Navigation
* Batch processing

Codex produces deterministic and repeatable artifacts.

---

## ChatGPT

Responsibilities:

* Technical explanation
* Document structure
* Readability
* Educational quality
* Domain interpretation
* Example generation
* Consistency improvement

ChatGPT works only with evidence provided by FRKC.

---

## Human Reviewer

Responsibilities:

* Technical verification
* Regulatory validation
* Bundle approval
* Release approval

---

# 6. Standard Publishing Process

Every new document follows these steps.

## Step 1

Identify the target document.

Example:

```text
RL-170_OPERATIONAL_RISK_OVERVIEW
```

---

## Step 2

Retrieve supporting knowledge from FRKC.

Retrieve:

* Canonical Concepts
* Evidence Bundles
* Glossary
* Formula References
* Regulations
* Mathematical Foundations

---

## Step 3

Verify Publishing Mapping.

Confirm:

* Target publication layer
* Existing mappings
* Related documents
* Confidence level

---

## Step 4

Generate the first draft.

The draft must contain:

* Supporting evidence
* Traceable terminology
* Consistent document structure

---

## Step 5

Editorial Review.

ChatGPT improves:

* Clarity
* Flow
* Technical explanations
* Examples
* Cross-references

No unsupported claims shall be introduced.

---

## Step 6

Technical Review.

Verify:

* Regulatory correctness
* Formula consistency
* Navigation
* Links
* Naming conventions

---

## Step 7

Publish to FRKP.

Commit through the appropriate feature branch.

---

# 7. Traceability Model

Every published document should be traceable.

```text
FRKP Document
        │
        ▼
Publishing Mapping
        │
        ▼
Canonical Concept
        │
        ▼
Evidence Bundle
        │
        ▼
Original Source Document
```

---

# 8. AI Collaboration Principles

The workflow follows FRKC-AI-001.

| Responsibility        | Owner   |
| --------------------- | ------- |
| Knowledge acquisition | FRKC    |
| Repository automation | Codex   |
| Editorial refinement  | ChatGPT |
| Final approval        | Human   |

---

# 9. Bundle Workflow

Bundle development proceeds as follows.

```text
New Bundle
        │
        ▼
Expand FRKC Knowledge
        │
        ▼
Update Publishing Mapping
        │
        ▼
Generate FRKP Drafts
        │
        ▼
Editorial Review
        │
        ▼
Bundle Review
        │
        ▼
Freeze
```

---

# 10. Quality Gates

Every document shall satisfy:

* Evidence available
* Canonical concepts identified
* Publishing mapping confirmed
* Navigation verified
* Cross-references verified
* Editorial review completed
* Human approval completed

---

# 11. Working Principles

* Knowledge First
* Evidence First
* Publishing Second
* AI Assisted
* Human Approved
* Technology Neutral
* Immutable Document IDs
* Incremental Repository Growth
* Bundle-based Development

---

# 12. Version Compatibility

| FRKC | FRKP |
| ---- | ---- |
| v0.1 | v1.1 |

Future versions shall maintain an explicit compatibility matrix.

---

# 13. Operational Checklist

Before publishing any document:

1. Confirm FRKC evidence exists.
2. Confirm publishing mapping exists.
3. Generate the initial draft.
4. Perform ChatGPT editorial review.
5. Perform human technical review.
6. Validate navigation and links.
7. Commit to the feature branch.
8. Update bundle status.

---

# 14. Future Evolution

Future enhancements include:

* Incremental Knowledge Updates
* Automated Impact Analysis
* AI-assisted Publishing
* Continuous Evidence Validation
* Regulatory Change Detection

---

# 15. Guiding Principle

> **Knowledge grows in FRKC.
> Documents grow in FRKP.
> Evidence precedes publication.**

The objective of the platform is not merely to create documents, but to create trustworthy, traceable, evidence-backed financial risk knowledge.

---

# 16. Revision History

| Version | Date       | Description                                 |
| ------- | ---------- | ------------------------------------------- |
| 1.0.0   | 2026-06-28 | Initial Evidence-Driven Publishing Workflow |
