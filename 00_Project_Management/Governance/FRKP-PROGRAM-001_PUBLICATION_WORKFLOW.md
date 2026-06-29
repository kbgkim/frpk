# FRKP-PROGRAM-001 — Publication Workflow

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-PROGRAM-001 |
| Document Name | Financial Platform Publication Workflow |
| Version | 1.0.0 |
| Status | Active |
| Category | Publication Governance |
| Owner | FRKP Publishing Office |
| Plan | PLAN-022 |
| Related Documents | FRKP-PROGRAM-000; FRKP-PROGRAM-002; FRKP-PROGRAM-003; FRKP-PROGRAM-004; FRKP-PUB-000; FRKP-PUB-001; FRKP-PUB-002; FRKP-FRKC-001; FAEP-STD-006 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |

---

# 1. Purpose

This document defines the **Publication Workflow** for the Financial Platform Handbook. It specifies the ordered stages through which every volume passes from initial knowledge identification to official publication.

The workflow extends the publishing architecture defined in FRKP-PUB-000 with detailed stage definitions, input/output specifications, and transition criteria.

---

# 2. Workflow Overview

```
Knowledge Extraction
       |
       v
  Technical Draft
       |
       v
  Architecture Review
       |
       v
  Technical Review
       |
       v
  Editorial Review
       |
       v
  Publication Freeze
       |
       v
  Official Publication
```

Each stage produces defined outputs and requires explicit approval before the next stage begins. Stages may iterate if approval criteria are not met, but iteration must be documented and timeboxed.

---

# 3. Stage Definitions

## 3.1 Knowledge Extraction

### Purpose
Identify and extract source knowledge from FRKC, Risk Platform, FRKP governance, and other authoritative sources. Produce structured knowledge packages ready for technical writing.

### Entry Criteria
- Volume is registered in the Publication Backlog (FRKP-PROGRAM-003) with priority assigned.
- Source repositories are accessible and baseline versions are identified.
- Knowledge mapping from FRKP-PUB-001 is available for the volume's capabilities.

### Inputs
| Input | Source | Format |
| --- | --- | --- |
| Knowledge Object references | FRKC | KO-{DOMAIN}-{NNN} identifiers |
| Capability mappings | FAEP-CAP-001 | CAP-{DOMAIN}-{NNN} mappings |
| Volume structure definition | FRKP-PUB-002 | Chapter and section outline |
| Source code references | Risk Platform | REF-{TYPE}-{NNN} identifiers |
| Governance documents | FRKP / FAEP | Document IDs |
| Evidence items | FRKC | EVD-{NNN} identifiers |

### Activities
- Identify all Knowledge Objects relevant to the volume.
- Extract source code, formula, and architecture references.
- Collect evidence items for every section claim.
- Catalogue cross-references to other volumes, chapters, and sections.
- Produce the Knowledge Extraction Package.

### Outputs
| Output | Description |
| --- | --- |
| Knowledge Extraction Package | Structured collection of all source materials by section |
| Source Reference Catalogue | Complete list of REF identifiers with locations |
| Evidence Bundle | All EVD identifiers with certification status |
| Cross-Reference Map | Known cross-references to other publications |
| Gap Register | Missing knowledge or evidence items requiring escalation |

### Exit Criteria
- Every section in the volume has at least one Knowledge Object reference.
- Every Knowledge Object reference resolves to a valid FRKC object.
- Evidence items are catalogued with certification status.
- Gaps are documented in the Gap Register.
- FRKP Publishing Office approves the Knowledge Extraction Package.

### Duration Target
2-4 weeks per volume (initial); 1-2 weeks per volume (subsequent volumes with established patterns).

---

## 3.2 Technical Draft

### Purpose
Transform the Knowledge Extraction Package into structured draft content following the Editorial Standard (FRKP-PROGRAM-002).

### Entry Criteria
- Knowledge Extraction Package approved.
- Volume structure from FRKP-PUB-002 is available.
- Section template from FRKP-PUB-002 is applied.
- Editorial Standard (FRKP-PROGRAM-002) is available as reference.

### Inputs
| Input | Source |
| --- | --- |
| Knowledge Extraction Package | Knowledge Extraction stage |
| Volume structure | FRKP-PUB-002 |
| Section template | FRKP-PUB-002 |
| Editorial Standard | FRKP-PROGRAM-002 |

### Activities
- Write section content following the section template.
- Embed Knowledge Object references inline using KO identifiers.
- Embed Capability references inline using CAP identifiers.
- Embed Evidence references inline using EVD identifiers.
- Create figures and tables following editorial conventions.
- Write all cross-references using the navigation standard.
- Ensure every section complies with the Editorial Standard.

### Outputs
| Output | Description |
| --- | --- |
| Volume Draft (v0.1) | Complete first draft of all chapters and sections |
| Figure and Table Assets | All embedded diagrams, charts, and data tables |
| Draft Cross-Reference Index | All cross-references with resolution status |
| Compliance Self-Check | Author's own assessment against Editorial Standard |

### Exit Criteria
- All sections have draft content.
- Section template is correctly applied to every section.
- All Knowledge Object, Capability, and Evidence references are embedded.
- Draft is self-consistent (no placeholder references).
- Technical Author confirms draft ready for review.

### Duration Target
2-4 weeks per volume.

---

## 3.3 Architecture Review

### Purpose
Validate the draft against FAEP architecture, platform consistency, and cross-volume architectural alignment. Ensure that architectural claims, engine descriptions, and contract references are accurate and consistent with the FAEP Master Architecture (FRKP-003) and Core Platform Specification (FRKP-004).

### Entry Criteria
- Technical Draft completed and submitted for review.
- Volume draft is architecture-complete (all architectural claims present).

### Inputs
| Input | Source |
| --- | --- |
| Volume Draft | Technical Draft stage |
| FAEP Master Architecture | FRKP-003 |
| FAEP Core Platform Specification | FRKP-004 |
| FAEP Standards | FAEP-STD-000 through FAEP-STD-006 |
| FAEP ADR Registry | FAEP-ADR-000 |
| FRKC Knowledge OS Specification | FRKP-005 |

### Activities
- Verify architectural descriptions match FRKP-003 and FRKP-004.
- Confirm engine model, contract references, and governance descriptions are correct.
- Validate cross-volume architectural consistency.
- Check ADR references against the ADR Registry.
- Identify architectural inaccuracies or ambiguities.

### Outputs
| Output | Description |
| --- | --- |
| Architecture Review Report | Findings, corrections required, and recommendations |
| Architecture Discrepancy Register | Specific inaccuracies with reference to source documents |
| Architecture Approval | Signed approval or conditional approval with required corrections |

### Exit Criteria
- All architecture descriptions are factually correct.
- All engine model references are accurate.
- All contract references conform to the Core Specification.
- Cross-volume architecture is consistent.
- Architecture discrepancies are resolved or accepted with documented risk.
- Architecture Reviewer issues approval.

### Duration Target
1-2 weeks per volume.

---

## 3.4 Technical Review

### Purpose
Validate the technical accuracy of every claim against source code, formulas, runtime behaviour, and implementation evidence. This is the primary quality gate for technical correctness.

### Entry Criteria
- Architecture Review approved.
- Technical sources (code, formulas, test outputs) are available at known versions.

### Inputs
| Input | Source |
| --- | --- |
| Volume Draft (post-architecture review) | Architecture Review stage |
| Risk Platform source code | Risk Platform repository |
| Formula Catalog | 04_Formula_Catalog/ |
| Evidence items | FRKC |
| Reference implementation | FRKP bundles and documentation |
| Technical Review checklist | FRKP-PROGRAM-004 |

### Activities
- Verify every technical claim against source code or evidence.
- Validate formula definitions against the Formula Catalog.
- Confirm runtime behaviour descriptions match actual execution.
- Check numeric precision claims against implementation.
- Validate compiler pipeline, execution plan, and runtime descriptions.
- Test code examples against actual implementation (where applicable).

### Outputs
| Output | Description |
| --- | --- |
| Technical Review Report | Findings, errors, and corrections required |
| Technical Error Register | Specific technical inaccuracies with correction instructions |
| Code Example Validation | Validation results for any embedded code examples |
| Technical Approval | Signed approval or conditional approval with required corrections |

### Exit Criteria
- Every technical claim is verified against source code or evidence.
- Formula references match the Formula Catalog.
- Runtime descriptions match actual execution behaviour.
- Code examples compile and execute correctly (where applicable).
- All technical errors are resolved.
- Technical Reviewer issues approval.

### Duration Target
2-3 weeks per volume.

---

## 3.5 Editorial Review

### Purpose
Validate compliance with the Editorial Standard (FRKP-PROGRAM-002), including document style, terminology, cross-references, traceability, figures, tables, glossary, and formatting.

### Entry Criteria
- Technical Review approved.

### Inputs
| Input | Source |
| --- | --- |
| Volume Draft (post-technical review) | Technical Review stage |
| Editorial Standard | FRKP-PROGRAM-002 |
| Navigation Standard | FAEP-STD-004 |
| Section Template | FRKP-PUB-002 |

### Activities
- Check document style compliance (headings, lists, code blocks, emphasis).
- Verify terminology consistency across the volume.
- Validate all cross-references resolve to valid targets.
- Check traceability from every section to Knowledge Objects.
- Verify Figure and Table formatting, numbering, and captions.
- Validate Example formatting and numbering.
- Check Glossary term usage and definitions.
- Verify navigation structure matches the Handbook Structure.
- Check reading order and logical flow.

### Outputs
| Output | Description |
| --- | --- |
| Editorial Review Report | Style, terminology, and formatting findings |
| Cross-Reference Validation Report | All cross-references with resolution status |
| Glossary Compliance Report | Glossary term usage and definition check |
| Editorial Approval | Signed approval or conditional approval with required corrections |

### Exit Criteria
- All sections comply with the Editorial Standard.
- All cross-references resolve.
- Terminology is consistent within and across volumes.
- Figures and Tables are correctly numbered and captioned.
- Glossary terms are correctly used and defined.
- Navigation is correct and complete.
- Editorial Reviewer issues approval.

### Duration Target
1 week per volume.

---

## 3.6 Publication Freeze

### Purpose
Freeze the volume scope and content. Activate change control. Only correction-level edits are permitted after freeze.

### Entry Criteria
- Architecture Review, Technical Review, and Editorial Review all approved.
- All required corrections from all reviews are applied.
- Quality Gate (FRKP-PROGRAM-004) is assessed as PASS or CONDITIONAL PASS.

### Inputs
| Input | Source |
| --- | --- |
| Final Volume Draft | Editorial Review stage |
| Quality Gate Assessment | FRKP-PROGRAM-004 |
| Review Reports | Architecture, Technical, Editorial reviews |

### Activities
- Verify all review corrections are applied.
- Freeze the volume scope (no new sections, chapters, or content).
- Activate change control — only errata, formatting, and cross-reference corrections.
- Record the freeze baseline version.
- Issue Freeze Certificate.
- Register the volume as frozen in the Publication Backlog.

### Outputs
| Output | Description |
| --- | --- |
| Freeze Certificate | Signed certification of volume freeze |
| Freeze Baseline Record | Volume version, chapter manifest, section count, evidence baseline |
| Change Control Log | Post-freeze change register |
| Residual Risk Register | Known issues accepted at freeze (if any) |

### Exit Criteria
- Freeze Certificate issued.
- Change control is active.
- Scope is locked.
- Freeze Authority signs the certificate.

### Duration Target
1 week per volume.

---

## 3.7 Official Publication

### Purpose
Release the frozen volume as an official publication of the Financial Platform Handbook. Make it available to the IB Project and all downstream consumers.

### Entry Criteria
- Publication Freeze certified.
- Quality Gate verdict is PASS or CONDITIONAL PASS.
- FRKP Publishing Office authorises publication.

### Inputs
| Input | Source |
| --- | --- |
| Frozen Volume | Publication Freeze stage |
| Freeze Certificate | Publication Freeze stage |
| Publication Authorisation | FRKP Publishing Office |

### Activities
- Release the volume to `11_Volumes/FP-VOL-{NNN}/`.
- Archive supporting assets (figures, tables, examples).
- Update the Master Document Index (FRKP-DOC-100).
- Update the Publication Backlog (FRKP-PROGRAM-003) with publication date.
- Notify the IB Project Liaison.
- Announce the publication to the FAEP Program.

### Outputs
| Output | Location |
| --- | --- |
| Published Volume | `11_Volumes/FP-VOL-{NNN}/` |
| Volume README | `11_Volumes/FP-VOL-{NNN}/README.md` |
| Publication Notice | Notification to IB Project and FAEP Program |

### Exit Criteria
- Volume is published in `11_Volumes/`.
- Master Document Index is updated.
- IB Project Liaison is notified.
- Publication Backlog is updated.

### Duration Target
1 day per volume.

---

# 4. Stage Transition Rules

## 4.1 Forward Transition

A stage transitions to the next stage only when all exit criteria are met and the appropriate approval is issued.

## 4.2 Backward Transition

A stage may return to any prior stage if exit criteria are not met. The reason must be documented, and a re-review plan must be defined with a timebox.

```
Knowledge Extraction <-- Technical Draft <-- Architecture Review
                                                      |
                                                      v
      Technical Review <-- Editorial Review <-- Publication Freeze
                                                      |
                                                      v
                                              Official Publication
```

## 4.3 Skip Rule

No stage may be skipped without explicit written authorisation from the FRKP Publishing Office and the FAEP Architecture Board. Skipped stages must be documented as accepted risks in the Residual Risk Register.

---

# 5. Workflow States

| State | Meaning |
| --- | --- |
| Planned | Volume registered in backlog; not yet started |
| Extracting | Knowledge Extraction in progress |
| Drafting | Technical Draft in progress |
| Architecture Review | Under architecture review |
| Technical Review | Under technical review |
| Editorial Review | Under editorial review |
| Freezing | Publication Freeze in progress |
| Published | Officially published |
| Errata | Post-publication correction in progress |
| Revision | New version in development |
| Deprecated | Volume superseded or retired |

---

# 6. Preservation Commitment

This document does not modify any FAEP Foundation, Core Contract, Standard, Specification, Governance, frozen bundle, or Version 1.0.0 artifact.

---

# 7. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Publication Workflow (PLAN-022) |
