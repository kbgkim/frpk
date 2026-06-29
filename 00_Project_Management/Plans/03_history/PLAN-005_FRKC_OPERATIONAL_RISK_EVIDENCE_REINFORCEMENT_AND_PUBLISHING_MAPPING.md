# PLAN-005 - FRKC Operational Risk Evidence Reinforcement and Publishing Mapping

## Document Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-005 |
| Title | FRKC Operational Risk Evidence Reinforcement and Publishing Mapping |
| Status | Completed |
| Category | Evidence Review; Knowledge Review; Publishing Review |
| Owner | Codex |
| Bundle | Bundle-007 Operational Risk |
| Related Documents | PLAN-004; FRKP-002; FRKP-FRKC-001; RL-170; KB-271; KB-272; AN-271; MF-471; FC-471; IMP-471; ARCH-771; BUNDLE-007 |
| Created | 2026-06-28 |
| Target Completion | 2026-06-28 |
| Completion Date | 2026-06-28 |

## Objective

Strengthen the Operational Risk evidence bridge required for Bundle-007 so FRKP publication can proceed under the Evidence-driven Publishing policy.

This plan records authoritative Operational Risk evidence, canonical terminology, graph relationships, and FRKC-to-FRKP publishing mappings. It does not modify FRKP Bundle-007 content and does not freeze the bundle.

## Scope

Included:

* Operational Risk evidence inventory review.
* SMA, BI, BIC, ILM, LC, operational loss data, Basel II AMA to Basel III SMA evolution, regulatory rationale, implementation, and architecture evidence reinforcement.
* Canonical vocabulary review.
* Knowledge graph relationship review.
* Publishing mapping for all Bundle-007 target documents.
* Evidence readiness verdict.

Excluded:

* FRKP Bundle-007 document content edits.
* Bundle freeze.
* Commit or release activity.
* Full integration tests or full build.

## Authoritative Source Register

| Source ID | Source | Coverage | Status |
| --- | --- | --- | --- |
| SRC-OPR-BCBS-D424 | Basel Committee on Banking Supervision, `Basel III: Finalising post-crisis reforms`, December 2017, https://www.bis.org/bcbs/publ/d424.pdf | SMA, BI, BIC, LC, ILM, operational risk capital, replacement of prior approaches | Authoritative |
| SRC-OPR-BCBS-128 | Basel Committee on Banking Supervision, `International Convergence of Capital Measurement and Capital Standards: A Revised Framework`, June 2006, https://www.bis.org/publ/bcbs128.pdf | Basel II operational risk framework, Basic Indicator Approach, Standardised Approach, AMA, operational loss data governance | Authoritative |
| SRC-OPR-FRKC-CAN-000032 | FRKC canonical concept `CAN-CON-000032` Operational Risk and evidence records `EVD-000330` through `EVD-000339` | Existing broad Operational Risk anchor | Existing FRKC evidence |

## Evidence Inventory

| Class | Existing Coverage | Reinforcement Result | Readiness |
| --- | --- | --- | --- |
| Canonical Concepts | `CAN-CON-000032` anchors Operational Risk. | Added required child concepts for SMA, BI, BIC, LC, ILM, operational loss data, implementation, and architecture. | Ready |
| Evidence Records | Existing `EVD-000330` through `EVD-000339` support broad Operational Risk only. | Added `EVD-000340` through `EVD-000349` evidence register for SMA-specific Bundle-007 use. | Ready |
| Metadata | Existing metadata points to broad Operational Risk context. | Reinforced metadata with source, coverage, layer, confidence, and cross-reference fields. | Ready |
| Semantic Chunks | Existing semantic chunks are traceable but noisy for SMA. | Defined clean semantic chunks by concept and target layer. | Ready |
| Knowledge Graph | Existing graph contains broad and weak co-occurrence links. | Added directed Operational Risk -> SMA -> BI/BIC/LC/ILM -> capital -> implementation -> architecture links. | Ready |
| Publishing Mapping | Existing mapping has empty target layers. | Added complete Bundle-007 target mapping. | Ready |

## Reinforced Evidence Register

| Evidence ID | Canonical Concept | Source | Metadata | Canonical Terminology | Cross References |
| --- | --- | --- | --- | --- | --- |
| EVD-000340 | Operational Risk | SRC-OPR-BCBS-128; SRC-OPR-FRKC-CAN-000032 | layer=RL/KB; confidence=high; type=definition/framework | Operational Risk; Operational Event; Operational Loss | CAN-CON-000032; RL-170; KB-271 |
| EVD-000341 | Historical Basel Operational Risk Evolution | SRC-OPR-BCBS-128; SRC-OPR-BCBS-D424 | layer=AN/KB; confidence=high; type=regulatory evolution | Basic Indicator Approach; Standardised Approach; AMA; SMA | AN-271; KB-271; KB-272 |
| EVD-000342 | Standardized Measurement Approach | SRC-OPR-BCBS-D424 | layer=KB/FC; confidence=high; type=methodology | Standardized Measurement Approach; SMA; Operational Risk Capital | KB-272; FC-471 |
| EVD-000343 | Business Indicator | SRC-OPR-BCBS-D424 | layer=KB/FC/IMP; confidence=high; type=input measure | Business Indicator; BI; financial statement input | KB-272; FC-471; IMP-471 |
| EVD-000344 | Business Indicator Component | SRC-OPR-BCBS-D424 | layer=KB/FC; confidence=high; type=formula component | Business Indicator Component; BIC; marginal coefficient | KB-272; FC-471 |
| EVD-000345 | Loss Component | SRC-OPR-BCBS-D424 | layer=KB/MF/FC; confidence=high; type=formula component | Loss Component; LC; internal loss experience | KB-272; MF-471; FC-471 |
| EVD-000346 | Internal Loss Multiplier | SRC-OPR-BCBS-D424 | layer=KB/FC; confidence=high; type=formula component | Internal Loss Multiplier; ILM; LC/BIC relationship | KB-272; FC-471 |
| EVD-000347 | Operational Loss Data | SRC-OPR-BCBS-128; SRC-OPR-BCBS-D424 | layer=MF/IMP; confidence=high; type=data requirement | Operational Loss; Internal Loss Data; External Loss Data; observation window | MF-471; IMP-471 |
| EVD-000348 | Implementation Considerations | SRC-OPR-BCBS-D424; SRC-OPR-FRKC-CAN-000032 | layer=IMP; confidence=medium-high; type=implementation control | BI calculation; loss data ingestion; validation; audit trail | IMP-471; FC-471 |
| EVD-000349 | Architecture Considerations | SRC-OPR-BCBS-D424; SRC-OPR-FRKC-CAN-000032 | layer=ARCH; confidence=medium-high; type=architecture control | BI Engine; Loss Event Engine; LC Engine; ILM Engine; Capital Engine; Reporting and Audit | ARCH-771; IMP-471 |

## Canonical Vocabulary

| Term | Canonical Use | Status |
| --- | --- | --- |
| Operational Risk | Risk of loss from failed or inadequate internal processes, people, systems, or external events. | Ready |
| Standardized Measurement Approach | Basel operational risk capital approach combining business scale and internal loss experience. | Ready |
| SMA | Abbreviation for Standardized Measurement Approach. | Ready |
| Business Indicator | Regulatory business-scale measure used as the basis for BIC. | Ready |
| BI | Abbreviation for Business Indicator. | Ready |
| Business Indicator Component | Piecewise regulatory transformation of BI into a capital component. | Ready |
| BIC | Abbreviation for Business Indicator Component. | Ready |
| Loss Component | Measure derived from internal operational loss experience. | Ready |
| LC | Abbreviation for Loss Component. | Ready |
| Internal Loss Multiplier | Adjustment factor reflecting the relationship between LC and BIC. | Ready |
| ILM | Abbreviation for Internal Loss Multiplier. | Ready |
| Operational Loss | Loss caused by an operational risk event. | Ready |
| Operational Event | Event that can produce an operational loss. | Ready |
| Internal Loss Data | Institution-specific operational loss event data. | Ready |
| External Loss Data | External operational loss event data used for benchmarking or context where permitted. | Ready |
| Expected Loss | Average or ordinary loss expectation for a loss distribution. | Supporting term |
| Unexpected Loss | Tail or adverse deviation beyond expected loss. | Supporting term |

## Knowledge Graph Summary

| Relationship | Evidence | Status |
| --- | --- | --- |
| Operational Risk -> Standardized Measurement Approach | EVD-000340; EVD-000342 | Ready |
| Historical Basel Operational Risk Evolution -> AMA -> SMA | EVD-000341; EVD-000342 | Ready |
| SMA -> Business Indicator | EVD-000342; EVD-000343 | Ready |
| Business Indicator -> Business Indicator Component | EVD-000343; EVD-000344 | Ready |
| Operational Loss Data -> Loss Component | EVD-000345; EVD-000347 | Ready |
| Business Indicator Component + Loss Component -> Internal Loss Multiplier | EVD-000344; EVD-000345; EVD-000346 | Ready |
| Business Indicator Component + Internal Loss Multiplier -> Operational Risk Capital | EVD-000342; EVD-000344; EVD-000346 | Ready |
| Operational Risk Capital -> Implementation | EVD-000348 | Ready |
| Implementation -> Architecture | EVD-000348; EVD-000349 | Ready |

## Publishing Mapping

| Evidence | Target Document | Target Layer | Coverage | Status |
| --- | --- | --- | --- | --- |
| EVD-000340; EVD-000341; EVD-000342 | RL-170_OPERATIONAL_RISK_OVERVIEW.md | Reference Library | Operational Risk definition, scope, regulatory direction, SMA overview | Ready |
| EVD-000340; EVD-000341; EVD-000347 | KB-271_OPERATIONAL_RISK_FRAMEWORK.md | Knowledge Base | Operational Risk framework, loss data, governance, historical context | Ready |
| EVD-000342; EVD-000343; EVD-000344; EVD-000345; EVD-000346 | KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md | Knowledge Base | SMA mechanics, BI, BIC, LC, ILM | Ready |
| EVD-000341; EVD-000342; EVD-000347 | AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md | Analysis | AMA to SMA rationale, comparability, simplicity, loss sensitivity | Ready |
| EVD-000345; EVD-000347 | MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md | Mathematical Foundation | Operational loss data, frequency/severity interpretation, LC context | Ready |
| EVD-000342; EVD-000343; EVD-000344; EVD-000345; EVD-000346 | FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md | Formula Catalog | BIC, LC, ILM, capital formula, input/output contract | Ready |
| EVD-000343; EVD-000347; EVD-000348 | IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md | Implementation Guide | BI calculation, loss data ingestion, validation, traceability | Ready |
| EVD-000348; EVD-000349 | ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md | Architecture Guide | BI engine, loss event engine, LC/ILM/capital engines, audit architecture | Ready |
| EVD-000340 through EVD-000349 | BUNDLE-007_OPERATIONAL_RISK_REVIEW.md | Bundle Review | Bundle evidence coverage, traceability, readiness assessment | Ready |

## Remaining Evidence Gaps

| Gap | Status | Treatment |
| --- | --- | --- |
| Jurisdiction-specific national implementation options | Open | Not required for Bundle-007 baseline; defer to future jurisdictional bundle or appendix. |
| Machine-readable FRKC YAML synchronization | Open | If the separate FRKC repository is used as the operational source, mirror `EVD-000340` through `EVD-000349` into FRKC evidence and mapping files. |
| Human regulatory review | Open | Required before freeze or release; not required for evidence readiness. |

## Verification

| Check | Result |
| --- | --- |
| Evidence completeness | Pass |
| Canonical terminology | Pass |
| Knowledge graph links | Pass |
| Publishing mapping | Pass |
| Cross references | Pass |
| Evidence IDs | Pass |
| Repository navigation | Pass |
| FRKP Bundle-007 content untouched | Pass |

## Readiness Assessment

Bundle-007 is evidence-ready for evidence-driven FRKP publication review. FRKP should not require manual evidence discovery for the listed target documents because the reinforced evidence register and publishing mapping now identify the source, evidence ID, canonical terminology, target layer, coverage, and status.

## Recommended Next PLAN

PLAN-006 - Bundle-007 Evidence-Driven Publication Review and Freeze Readiness.

PLAN-006 should consume this mapping, review the existing Bundle-007 documents against `EVD-000340` through `EVD-000349`, and decide whether the bundle can enter review or freeze. PLAN-006 must still avoid freeze unless human review accepts the evidence alignment.

## Verdict

GO.

Bundle-007 Operational Risk can proceed to evidence-driven publication review. This is not a bundle freeze verdict.

## Closure Summary

PLAN-005 completed the evidence inventory, evidence reinforcement register, canonical vocabulary review, knowledge graph summary, publishing mapping, gap analysis, readiness assessment, and recommended next plan. No FRKP Bundle-007 content was modified and no commit was created.
