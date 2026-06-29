# PLAN-004 - Bundle-007 Evidence Mapping Readiness

## Document Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-004 |
| Title | Bundle-007 Evidence Mapping Readiness |
| Status | Completed |
| Category | Evidence Review; Publishing Review |
| Owner | Codex |
| Bundle | Bundle-007 Operational Risk |
| Related Documents | FRKP-002; PROJECT_STATE.md; FRKP-FRKC-001; BUNDLE-007_OPERATIONAL_RISK_REVIEW.md; FRKC CAN-CON-000032 |
| Created | 2026-06-28 |
| Target Completion | 2026-06-28 |
| Completion Date | 2026-06-28 |

## Objective

Review whether Bundle-007 Operational Risk can proceed to evidence-driven completion by confirming the availability, structure, and usability of FRKC evidence and publishing mapping.

## Repository State Verified

| Repository | Branch | Status |
| --- | --- | --- |
| FRKP | feature/bundle-007-operational-risk | Dirty working tree with modified navigation/session files and untracked governance, planning, and Bundle-007 files. |
| FRKC | main | Dirty working tree with untracked governance, certification, report, and tool files. |

## FRKC Operational Risk Evidence Inventory

| Evidence Area | Finding | Usability |
| --- | --- | --- |
| Metadata | Operational Risk appears in metadata for KC-000001, KC-000003, KC-000022, KC-000023, KC-000031, KC-000032, KC-000034, KC-000036, KC-000037, and KC-000042. | Usable only for broad Operational Risk context. |
| Evidence records | `evidence/CAN-CON-000032.yaml` exists for Operational Risk with EVD-000330 through EVD-000339. | Structurally usable, but mostly broad/regulatory and not SMA-specific. |
| Semantic extraction | Semantic artifacts exist for all related source documents listed in CAN-CON-000032. | Usable for traceability; content is noisy and market/NCR-heavy. |
| Canonical vocabulary | `CAN-CON-000032` exists as canonical concept "Operational Risk". | Usable for top-level concept anchoring. |
| Knowledge graph | Graph entries connect Operational Risk to generic concepts including Capital Requirement, Risk Charge, Data Loader, REST API, and Net Capital Ratio. | Usable for broad architecture/context only; graph relationships include weak co-occurrence noise. |
| Publishing mapping | Operational Risk appears in publishing mappings, but `publishes_to` and `target_publication_layers` are empty. | Not ready for evidence-driven Bundle-007 publishing. |

## FRKP Document-to-Evidence Mapping

| FRKP Document | Best Available FRKC Evidence | Mapping Strength | Readiness |
| --- | --- | --- | --- |
| RL-170_OPERATIONAL_RISK_OVERVIEW.md | CAN-CON-000032; EVD-000330 to EVD-000339; KC-000022 direct glossary statement; KC-000031 NCR operational risk amount context. | Medium for overview, weak for Basel III/SMA detail. | Evidence-ready for broad editorial review only. |
| KB-271_OPERATIONAL_RISK_FRAMEWORK.md | CAN-CON-000032; KC-000022 Basel II emergence statement; KC-000031 NCR total-risk structure. | Medium for broad framework, weak for modern Basel operational risk framework. | Needs FRKC reinforcement. |
| KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md | No usable SMA, BI, BIC, LC, ILM, or operational loss data evidence found. | Weak. | Blocked for evidence-driven completion. |
| AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md | KC-000022 Basel II emergence statement; generic Basel II/Basel III references. | Weak for explanatory change analysis. | Needs FRKC reinforcement. |
| MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md | No usable operational loss distribution or loss data evidence found. | Weak. | Blocked for evidence-driven completion. |
| FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md | No usable SMA formula evidence for BIC, ILM, LC, or capital formula found. | Weak. | Blocked for evidence-driven completion. |
| IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md | Generic implementation/architecture terms in KC-000001 and KC-000042: Data Loader, REST API, batch scheduler, platform components. | Medium for generic platform pattern, weak for SMA implementation. | Needs FRKC reinforcement. |
| ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md | Generic architecture terms in KC-000001 and KC-000042 plus graph co-occurrence links. | Medium for generic architecture, weak for SMA-specific architecture. | Needs FRKC reinforcement. |
| BUNDLE-007_OPERATIONAL_RISK_REVIEW.md | Can reference the readiness outcome and broad CAN-CON-000032 inventory. | Weak as final bundle review evidence. | Should remain unfrozen; not ready for final evidence-driven review. |

## Evidence Gaps

| Gap | Status | Impact |
| --- | --- | --- |
| Missing Basel source references | Present | No authoritative Basel operational risk/SMA source is mapped to Bundle-007. |
| Missing SMA evidence | Present | KB-272 and formula/implementation/architecture claims cannot be completed evidence-first. |
| Missing Business Indicator Component evidence | Present | BIC formula and calculation contract are unsupported. |
| Missing Internal Loss Multiplier evidence | Present | ILM explanation and formula are unsupported. |
| Missing Loss Component evidence | Present | LC explanation and formula are unsupported. |
| Missing operational loss data evidence | Present | Loss distribution, LC, and implementation data requirements are unsupported. |
| Missing implementation guidance evidence | Partial | Generic Data Loader/API/batch concepts exist, but no SMA-specific implementation evidence exists. |
| Missing architecture mapping evidence | Partial | Generic architecture concepts exist, but no Operational Risk/SMA architecture publishing mapping exists. |

## Readiness Classification

| Classification | Documents |
| --- | --- |
| Evidence-ready | None for final evidence-driven completion. |
| Evidence-ready for editorial review only | RL-170_OPERATIONAL_RISK_OVERVIEW.md |
| Needs FRKC evidence reinforcement | KB-271_OPERATIONAL_RISK_FRAMEWORK.md; AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md; IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md; ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md; BUNDLE-007_OPERATIONAL_RISK_REVIEW.md |
| Blocked for evidence-driven completion | KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md; MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md; FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md |

## Recommended Next PLAN ID

PLAN-005 - FRKC Operational Risk Evidence Reinforcement and Publishing Mapping.

## Verdict

NO-GO.

Operational Risk evidence exists in FRKC, but it cannot currently support evidence-driven publishing completion for Bundle-007. Bundle-007 should not be frozen or marked evidence-complete until FRKC evidence reinforcement and publishing mapping are completed.

## Validation Performed

* Read required session restoration documents.
* Verified FRKP branch/status.
* Verified FRKC branch/status.
* Reviewed FRKC Operational Risk canonical concept `CAN-CON-000032`.
* Reviewed FRKC evidence bundle `evidence/CAN-CON-000032.yaml`.
* Reviewed FRKC publishing mapping entries for Operational Risk.
* Searched FRKC metadata, semantic, evidence, canonical, graph, and publishing artifacts for SMA-specific terms.
* Reviewed headings and key evidence-sensitive sections for all Bundle-007 FRKP documents.

## Closure Summary

PLAN-004 is completed as an Evidence Review and Publishing Review. The plan produced the required evidence inventory, document-to-evidence mapping table, evidence gap list, readiness classification, recommended next plan, and verdict. No Bundle-007 domain content and no FRKC evidence were modified.
