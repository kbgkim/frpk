# PLAN-021 — Risk Platform Publishing Architecture and Knowledge Mapping

## Plan Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-021 |
| Title | Risk Platform Publishing Architecture and Knowledge Mapping |
| Status | Completed |
| Category | Publishing Architecture; Knowledge Mapping; Governance Definition |
| Owner | FRKP Publishing Office |
| Repository | https://github.com/kbgkim/frpk |
| Branch | feature/bundle-007-operational-risk |
| Related Documents | FRKP-PUB-000; FRKP-PUB-001; FRKP-PUB-002; FRKP-003; FRKP-004; FRKP-005; FAEP-CAP-000; FAEP-CAP-001; FAEP-FOUNDATION-000; FAEP-FOUNDATION-001; FAEP-FOUNDATION-002; FRKP-FRKC-001; FRKP-DOC-100; PLAN-001 through PLAN-020; PLAN_STANDARD.md; PLAN_INDEX.md; active.md; CURRENT_WORK.md; next-session.md; PROJECT_STATE.md; MASTER_SESSION.md; AI_SESSION_HANDOFF.md |
| Created | 2026-06-28 |
| Completed | 2026-06-28 |

---

## Executive Summary

PLAN-021 defines the **Financial Platform Publishing Architecture** and **Knowledge Mapping Model** for transforming Risk Platform knowledge into publishable Financial Platform documentation.

The FAEP Foundation v1.0 is frozen. The Risk Platform is established as the primary Reference Implementation. The next priority is preparing high-quality technical publications for the upcoming IB Project.

**Key Results:**

- **FRKP-PUB-000** — Financial Platform Publishing Architecture established with complete publication hierarchy, workflow, and traceability model.
- **FRKP-PUB-001** — Knowledge Mapping Model defining source-to-publication transformation and full 35-capability mapping table.
- **FRKP-PUB-002** — Financial Platform Handbook Structure with 8 volumes, 48 chapters, 144+ sections.
- **All 35 Candidate Capabilities** mapped to specific volumes, chapters, and sections.
- **PLAN-022** recommended as Financial Platform Handbook Volume Pilot.

**No FAEP Foundation artifacts, Core Contracts, Standards, frozen bundles, or repository structure were modified.**

**Verdict: GO — Financial Platform Publishing Architecture Established.**

---

## 1. Objective

Define the publishing architecture for the Financial Platform Handbook and create the mapping from Risk Platform source knowledge to published documentation.

Establish FRKP as the official technical publishing platform for the Financial Platform, serving the IB Project as the primary downstream consumer.

---

## 2. Scope

### In Scope

- Publishing Philosophy — FRKP role, FAEP/FRKC/FRKP/Risk Platform/IB Project relationships.
- Publishing Architecture — Publication hierarchy (Financial Platform → Volume → Chapter → Section → Knowledge Object → Reference).
- Handbook Structure — 8 volumes with chapters, sections, justifications, and dependencies.
- Knowledge Mapping — Source code to publication transformation methodology.
- Capability Mapping — All 35 Candidate Capabilities mapped to Volume/Chapter/Section.
- Traceability Model — End-to-end traceability (Risk Source → Knowledge → Formula → Capability → Publication → IB Requirement).
- Publishing Workflow — Knowledge Extraction → Technical Review → Publication Review → Version Freeze → Official Publication.
- Publication priority and PLAN-022 recommendation.

### Out of Scope

- Handbook content writing.
- Implementation.
- Code.
- Repository migration.
- Commits.
- FAEP Foundation modifications.
- Candidate Capability validation (deferred to future PLAN).

---

## 3. Constraints

- Architecture and mapping only.
- No handbook writing.
- No code.
- No implementation.
- No repository migration.
- Preserve FAEP Foundation v1.0 frozen artifacts.
- Preserve all Core Contracts, Standards, Specifications, and governance documents.
- Preserve existing Bundle-007 frozen artifacts.
- Preserve existing Version 1.0.0 artifacts.

---

## 4. Source of Truth

| Priority | Source | Used For |
| --- | --- | --- |
| 1 | FAEP-CAP-001 — Candidate Capability Registry | 35 Candidate Capabilities, provider/consumer mapping, validation priorities |
| 2 | FRKP-003 — FAEP Master Architecture | Platform architecture, engine model, program hierarchy |
| 3 | FRKP-004 — FAEP Core Platform Specification | Core contracts, platform specification, governance model |
| 4 | FRKP-005 — FRKC Knowledge Operating System | Knowledge architecture, objects, ontology, evidence management |
| 5 | FRKP-FRKC-001 — Evidence-Driven Publishing Workflow | Publishing workflow, evidence mapping methodology |
| 6 | PLAN-016 — FAEP Platform Validation Using Risk Platform | Risk Platform capabilities, gaps, over-generalization findings |
| 7 | FRKP-DOC-100 — Master Document Index | Document hierarchy, layer architecture, bundle status |
| 8 | FAEP-FOUNDATION-000/001/002 | Foundation freeze boundaries, evolution policy |
| 9 | FRKP-002 — AI Operating Model | AI agent orchestration, session management patterns |

---

## 5. Deliverables

| Deliverable | Location | Description |
| --- | --- | --- |
| FRKP-PUB-000 | 00_Project_Management/Governance/FRKP-PUB-000_FINANCIAL_PLATFORM_PUBLISHING_ARCHITECTURE.md | Financial Platform Publishing Architecture — philosophy, hierarchy, workflow, traceability |
| FRKP-PUB-001 | 00_Project_Management/Governance/FRKP-PUB-001_KNOWLEDGE_MAPPING_MODEL.md | Knowledge Mapping Model — source-to-publication methodology, 35-capability mapping table |
| FRKP-PUB-002 | 00_Project_Management/Governance/FRKP-PUB-002_FINANCIAL_PLATFORM_HANDBOOK_STRUCTURE.md | Financial Platform Handbook Structure — 8 volumes, 48 chapters, 144+ sections |
| PLAN-021 | 00_Project_Management/Plans/03_history/PLAN-021_RISK_PLATFORM_PUBLISHING_ARCHITECTURE_AND_KNOWLEDGE_MAPPING.md | This plan document |
| PLAN_INDEX.md | Updated with PLAN-021 entry | |
| active.md | Updated with completed PLAN-021 | |
| CURRENT_WORK.md | Updated with PLAN-021 completion | |
| next-session.md | Updated with PLAN-021 handoff | |
| PROJECT_STATE.md | Updated with PLAN-021 verdict | |

---

## 6. Key Findings

1. **FRKP is positioned as the official technical publishing platform for the Financial Platform.** The publishing architecture establishes FRKP's role beyond internal knowledge management to external technical publication for the IB Project.

2. **The publication hierarchy (Financial Platform → Volume → Chapter → Section → Knowledge Object → Reference) provides 6 levels of granularity.** Every publication artifact traces to source code through Knowledge Objects and References.

3. **8 volumes with 6 chapters each provide balanced coverage.** Each volume has a clear architectural justification mapped to specific source evidence.

4. **All 35 Candidate Capabilities are mapped to specific sections.** No capability is left unmapped. Knowledge domain capabilities concentrate in FP-VOL-005; Publishing domain in FP-VOL-006 and FP-VOL-007; Execution domain across FP-VOL-001, FP-VOL-002, FP-VOL-003, and FP-VOL-007; Governance domain in FP-VOL-001, FP-VOL-006, and FP-VOL-007.

5. **FP-VOL-004 (Risk Solution) is the only volume without direct Candidate Capability mapping.** This is expected — Risk Solution is business-domain content derived from FRKP bundles, not from platform capabilities.

6. **The 5-stage publishing workflow (Knowledge Extraction → Technical Review → Publication Review → Version Freeze → Official Publication) aligns with the existing FRKP-FRKC-001 evidence-driven model.**

7. **The traceability model enables bidirectional resolution.** Every section traces to a Knowledge Object; every Knowledge Object traces to a source code location; every IB Requirement traces to a section.

8. **FP-VOL-005 (Knowledge Platform) is the recommended first publication.** It has no dependencies and provides the knowledge foundation for all other volumes.

---

## 7. Recommended PLAN-022

### PLAN-022 — Financial Platform Handbook Volume Pilot

| Aspect | Description |
| --- | --- |
| **Title** | Financial Platform Handbook Volume Pilot |
| **Objective** | Write the first volume (FP-VOL-005 — Knowledge Platform) as a pilot to validate the publishing architecture end-to-end |
| **Scope** | Full 6-chapter volume with complete traceability from FRKC knowledge objects to published content |
| **Source** | FRKP-PUB-000 (architecture), FRKP-PUB-001 (mapping), FRKP-PUB-002 (structure), FRKP-005 (FRKC specification), FAEP-CAP-001 (capabilities) |
| **Outputs** | FP-VOL-005 draft content; publishing architecture validation report; lessons learned for remaining 7 volumes |
| **Priority** | High — validates the entire publishing workflow before committing to full 8-volume production |
| **Dependencies** | None — all architectural inputs are documented in FRKP-PUB-000/001/002 |
| **Risk** | Low — pilot scope limits risk; lessons learned improve subsequent volumes |

---

## 8. Preservation Statement

PLAN-021 did not modify:
- FAEP Foundation v1.0 frozen artifacts.
- FAEP Core Contracts (CC-*).
- FAEP Standards (FAEP-STD-000 through FAEP-STD-006).
- FAEP Specifications (FRKP-003, FRKP-004, FRKP-005).
- FAEP Governance documents (FAEP-000, FAEP-001, FAEP-002).
- FAEP ADR Registry (FAEP-ADR-000).
- FAEP Contract Governance (FAEP-CONTRACT-000, FAEP-CONTRACT-001).
- FAEP Validation Framework (FAEP-VALIDATION-000, FAEP-VALIDATION-001).
- FAEP Foundation Governance (FAEP-FOUNDATION-000, FAEP-FOUNDATION-001, FAEP-FOUNDATION-002).
- FAEP Capability Discovery (FAEP-CAP-000, FAEP-CAP-001).
- Bundle-007 frozen artifacts.
- Existing Version 1.0.0 artifacts.
- Bundle structure or repository layout.

PLAN-021 did not perform:
- Implementation.
- Code.
- Repository migration.
- Commits.
- Releases.

---

## 9. Verdict

**GO — Financial Platform Publishing Architecture Established.**

The Financial Platform Publishing Architecture (FRKP-PUB-000), Knowledge Mapping Model (FRKP-PUB-001), and Financial Platform Handbook Structure (FRKP-PUB-002) have been created. The architecture defines a complete publication hierarchy, an 8-volume Handbook structure, a 5-stage publishing workflow, an end-to-end traceability model, and a full mapping of all 35 Candidate Capabilities to specific volumes, chapters, and sections. No Foundation artifacts were modified. PLAN-022 is recommended as a volume pilot to validate the architecture before full production.

---

## 10. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Risk Platform Publishing Architecture and Knowledge Mapping (PLAN-021) |
