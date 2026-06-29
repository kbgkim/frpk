# BUNDLE-007 Review Package

## Package Information

| Item | Value |
| --- | --- |
| Package ID | BUNDLE-007-REVIEW-PACKAGE |
| Related Plan | PLAN-035A |
| Bundle | Bundle-007 - Operational Risk Review |
| Purpose | GPT review handoff package |
| Created | 2026-06-29 |
| Owner | Codex |
| Status | Ready for GPT Review |

---

# 1. Review Package Summary

This package is the Engineering Review handoff for Bundle-007. It does not perform Semantic Review,
Financial Review, Architecture Review, Publication Review, editorial correction, or source document
modification.

Bundle-007 contains nine reviewable documents: one Reference Library document, two Knowledge Base
documents, one Analysis document, one Mathematical Foundation document, one Formula Catalog document,
one Implementation Guide, one Architecture Guide, and the Bundle Review closure document.

The bundle is structurally complete and follows the FRKP layer progression:

```text
Reference Library
-> Knowledge Base
-> Analysis
-> Formula
-> Mathematics
-> Implementation
-> Architecture
```

The main GPT review requirement is not to rewrite content but to assess semantic consistency,
financial/regulatory correctness, formula completeness, architecture coherence, publication readiness,
and traceability maturity.

Known engineering review conditions from prior plans remain:

- KO references are not yet explicitly mapped.
- CAP references are not yet explicitly mapped.
- EVD references are not yet explicitly mapped.
- FRKP master index synchronization remains a governance/publication condition.
- Final freeze and release are out of scope.

---

# 2. Repository Verification

| Check | Result |
| --- | --- |
| Required branch | feature/bundle-007-operational-risk |
| Current branch | feature/bundle-007-operational-risk |
| Branch verification | PASS |
| Repository synchronization | PASS - ahead/behind count `0 0` against `origin/feature/bundle-007-operational-risk` |
| Source of truth | Repository documents only |

---

# 3. Baseline Workflow Context

| Plan | Role in Current Workflow |
| --- | --- |
| PLAN-024 | Established repository audit and Bundle-007 editorial baseline. |
| PLAN-026 | Converted recurring P2 findings into Editorial Contracts EC-001 through EC-010. |
| PLAN-027 | Defined automation categories and capability routing for editorial work. |
| PLAN-028 | Validated the editorial workflow and confirmed Bundle-007 readiness for Semantic Review. |
| PLAN-029 | Defined traceability scaffold and TC-001 through TC-008. |
| PLAN-030 | Defined execution lifecycle and state model. |
| PLAN-031 | Validated FAEP using FRKP as reference implementation. |
| PLAN-032 | Defined validation evidence and score calibration model. |
| PLAN-033 | Validated FAEP across Risk Platform as a different platform type. |
| PLAN-034 | Certified FAEP Operational Baseline and identified Bundle-007 publication completion as next priority. |

---

# 4. Document Review Packages

## 4.1 RL-170 - Operational Risk Overview

## Document Information

| Item | Value |
| --- | --- |
| Document ID | RL-170 |
| File | `01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md` |
| Purpose | Define the top-level operational risk reference and Bundle-007 entry point. |
| Layer | Reference Library |
| Intended Reader | Reader needing a high-level operational risk orientation before detailed knowledge, analysis, formula, implementation, or architecture review. |

## Executive Summary

1. RL-170 is the top-level reference document for Bundle-007.
2. It defines operational risk as loss risk from internal process, people, system, or external event failures.
3. It positions operational risk as a regulatory capital, control, data quality, and governance topic.
4. It introduces loss events, internal loss data, control environment, and capital requirements.
5. It frames SMA as the bundle's regulatory direction.
6. It establishes the downstream document chain from Knowledge Base to Architecture.
7. It describes Bundle-007 as a Basel III-related operational risk knowledge expansion.
8. It identifies the intended deliverables across all bundle layers.
9. It is conceptually broad and intentionally not formula-specific.
10. GPT should use it as the semantic anchor for all other Bundle-007 documents.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | Operational risk, loss event, control environment, regulatory capital, SMA. |
| Definitions | Operational risk is tied to process, people, system, and external event failures. |
| Formula relationships | Establishes the context that later flows into BIC, LC, ILM, and capital formula documents. |
| Risk concepts | Operational failure, loss realization, control weakness, capital adequacy, data quality. |

## Architecture Position

RL-170 sits at the Reference Library layer. It provides the domain entry point that all later layers
depend on. It does not define implementation architecture but supplies the reference concepts that
must remain consistent through Knowledge Base, Analysis, Formula, Mathematics, Implementation, and
Architecture.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271, KB-272
-> Analysis: AN-271
-> Formula: FC-471
-> Mathematics: MF-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Implied but not explicitly mapped to KO identifiers. |
| Capabilities | Implied operational risk knowledge capability; no explicit CAP reference. |
| Evidence | No explicit EVD reference in source document. |
| Cross References | Links to KB-271, KB-272, AN-271, FC-471, and MF-471. |
| Related Documents | Missing direct related links to IMP-471 and ARCH-771 in its Related Documents block, though deliverables list includes them. |
| Current Traceability Status | Structurally traceable; explicit KO/CAP/EVD traceability pending GPT/governance review. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear entry point, strong concept framing, complete bundle deliverables list. |
| Weaknesses | High-level; does not cite explicit evidence identifiers or capability/knowledge-object mappings. |
| Known Issues | Traceability references remain implicit. |
| Recommended Review Focus | Confirm that the operational risk definition and scope align with downstream documents and regulatory review expectations. |

---

## 4.2 KB-271 - Operational Risk Framework

## Document Information

| Item | Value |
| --- | --- |
| Document ID | KB-271 |
| File | `02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md` |
| Purpose | Define the operational risk conceptual framework used by Bundle-007. |
| Layer | Knowledge Base |
| Intended Reader | Reader needing the event-control-capital model before SMA, analysis, formula, and architecture review. |

## Executive Summary

1. KB-271 is the central Knowledge Base framework document for Bundle-007.
2. It frames operational risk around risk events, loss data, control environment, and regulatory capital.
3. It explains why operational risk is harder to quantify than credit or market risk.
4. It emphasizes non-standardized events, complex causality, control effects, and uneven data quality.
5. It identifies Event, Control, and Capital as the three main interpretation axes.
6. It defines risk event, loss data, control failure, and risk governance.
7. It provides the conceptual bridge from RL-170 to KB-272 and downstream documents.
8. It explains that operational risk is not solved by capital alone.
9. It links capital calculation to control and data governance.
10. GPT should use it to check semantic consistency across the bundle's conceptual model.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | Risk event, loss data, control failure, risk governance, event-control-capital model. |
| Definitions | A risk event causes loss or loss potential; loss data records operational losses; control failure is a failed process, people, system, or external response mechanism. |
| Formula relationships | Provides conceptual inputs for LC and the governance rationale behind SMA adjustments. |
| Risk concepts | Data quality, governance, control environment, capital adequacy, regulatory comparability. |

## Architecture Position

KB-271 translates RL-170 into a reusable knowledge model. It is upstream of KB-272, AN-271, MF-471,
FC-471, IMP-471, and ARCH-771. Its event-control-capital framing should be reflected in implementation
and architecture components.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271
-> Knowledge Base: KB-272
-> Analysis: AN-271
-> Formula/Mathematics: FC-471, MF-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Candidate KOs implied: Operational Risk Framework, Risk Event, Loss Data, Control Environment, Risk Governance. |
| Capabilities | Candidate capabilities implied: operational risk classification, loss data interpretation, control governance framing. |
| Evidence | No explicit EVD references. |
| Cross References | Provides complete cross-reference table across all major Bundle-007 layers. |
| Related Documents | Links to RL-170, KB-272, AN-271, FC-471, and MF-471 in Related Documents. |
| Current Traceability Status | Strong document-level traceability; explicit KO/CAP/EVD mapping pending. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear domain framework and useful three-axis model. |
| Weaknesses | Does not explicitly tie definitions to evidence or canonical knowledge object identifiers. |
| Known Issues | Review should confirm whether control governance is sufficiently represented downstream. |
| Recommended Review Focus | Validate semantic alignment between the framework model and later SMA, implementation, and architecture documents. |

---

## 4.3 KB-272 - Standardized Measurement Approach

## Document Information

| Item | Value |
| --- | --- |
| Document ID | KB-272 |
| File | `02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md` |
| Purpose | Explain SMA as the bundle's core regulatory measurement concept. |
| Layer | Knowledge Base |
| Intended Reader | Reader reviewing SMA concepts before financial, formula, implementation, or architecture validation. |

## Executive Summary

1. KB-272 defines the Standardized Measurement Approach for operational risk capital.
2. It describes SMA as combining business scale and internal loss experience.
3. It identifies BI, BIC, LC, ILM, and Operational Risk Capital as the primary chain.
4. It explains BI as a standardized measure of operational risk exposure scale.
5. It explains BIC as BI transformed through regulatory scaling.
6. It explains LC as a loss-history based component using operational loss events.
7. It explains ILM as the relationship between LC and BIC.
8. It describes SMA as simpler and more comparable than internal model approaches.
9. It serves as the conceptual source for FC-471 and IMP-471.
10. GPT should prioritize financial/regulatory correctness review here.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | BI, BIC, LC, ILM, SMA, business scale, internal loss adjustment. |
| Definitions | BI measures business activity scale; BIC applies regulatory scaling; LC summarizes internal losses; ILM adjusts capital based on LC/BIC. |
| Formula relationships | Defines the conceptual chain later expressed by FC-471 as Operational Risk Capital = BIC x ILM. |
| Risk concepts | Loss sensitivity, comparability, auditability, data quality, regulatory standardization. |

## Architecture Position

KB-272 is the specific knowledge layer that converts the general operational risk framework into the
SMA calculation model. It directly informs AN-271, MF-471, FC-471, IMP-471, and ARCH-771.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271
-> Knowledge Base: KB-272
-> Analysis: AN-271
-> Formula: FC-471
-> Mathematics: MF-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Candidate KOs implied: SMA, BI, BIC, LC, ILM, Operational Risk Capital. |
| Capabilities | Candidate capabilities implied: SMA calculation interpretation, loss data adjustment, regulatory scaling review. |
| Evidence | No explicit EVD references. |
| Cross References | Complete cross-reference table across Reference, Knowledge, Analysis, Mathematical Foundation, Formula, Implementation, Architecture. |
| Related Documents | Links to all major Bundle-007 source documents. |
| Current Traceability Status | Strong document-level traceability; explicit KO/CAP/EVD mapping pending. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear high-level SMA chain and readable explanation of BI/BIC/LC/ILM. |
| Weaknesses | Formula details are intentionally conceptual; regulatory exactness needs financial review. |
| Known Issues | Needs review for whether BI components, BIC scaling, LC window, and ILM description are financially complete. |
| Recommended Review Focus | Financial/regulatory review of SMA mechanics and terminology consistency with Basel operational risk standards. |

---

## 4.4 AN-271 - Why Operational Risk Capital Changed

## Document Information

| Item | Value |
| --- | --- |
| Document ID | AN-271 |
| File | `03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md` |
| Purpose | Explain the rationale for transition from legacy operational risk approaches to SMA. |
| Layer | Analysis |
| Intended Reader | Reader evaluating why the bundle's SMA direction is justified and how it affects systems and governance. |

## Executive Summary

1. AN-271 is the analytical rationale document for Bundle-007.
2. It explains the historical transition from income proxy and internal model approaches to SMA.
3. It identifies weaknesses in legacy income proxy approaches.
4. It identifies model variability as a limitation of internal models.
5. It explains the loss experience gap as a weakness in prior capital methods.
6. It lists comparability, simplicity, loss sensitivity, governance, and supervisory consistency as drivers.
7. It frames SMA as a balance between simplicity, scale reflection, loss experience, and explainability.
8. It connects capital methodology changes to system architecture requirements.
9. It identifies BI calculation, loss data, regulatory scaling, audit trail, and exception handling as implications.
10. GPT should use it to review whether the narrative supports the formula and architecture choices.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | Legacy approach limitations, income proxy weakness, model variability, loss sensitivity, supervisory consistency. |
| Definitions | SMA is presented as a standardized and explainable capital approach rather than a full operational risk model. |
| Formula relationships | Provides rationale for using BIC, LC, and ILM instead of pure income proxy or internal model results. |
| Risk concepts | Governance incentives, comparability, loss experience, model risk, data quality. |

## Architecture Position

AN-271 is the bridge between knowledge concepts and downstream design. It explains why the bundle needs
a deterministic and auditable calculation pipeline.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271, KB-272
-> Analysis: AN-271
-> Formula: FC-471
-> Mathematics: MF-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Candidate KOs implied: Operational Risk Capital Change, SMA Rationale, Legacy Approach Limitation. |
| Capabilities | Candidate capabilities implied: regulatory rationale analysis, architecture implication assessment. |
| Evidence | No explicit EVD references. |
| Cross References | Links to all major Bundle-007 source layers. |
| Related Documents | Related Documents block includes all major source layers. |
| Current Traceability Status | Strong layer traceability; evidence and KO/CAP mapping pending. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear explanatory narrative and good connection from regulation to architecture. |
| Weaknesses | Financial/regulatory claims are not explicitly evidenced. |
| Known Issues | Needs review for whether historical characterization is precise enough for publication. |
| Recommended Review Focus | Semantic and financial review of legacy approach descriptions and stated drivers of SMA adoption. |

---

## 4.5 MF-471 - Operational Risk Loss Distribution

## Document Information

| Item | Value |
| --- | --- |
| Document ID | MF-471 |
| File | `05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md` |
| Purpose | Explain the mathematical structure of operational risk loss distribution. |
| Layer | Mathematical Foundation |
| Intended Reader | Reader evaluating loss distribution assumptions that support LC, ILM, capital sensitivity, and implementation review. |

## Executive Summary

1. MF-471 is the mathematical foundation document for operational risk losses.
2. It explains that operational risk losses are not well captured by a simple normal distribution.
3. It identifies sparse event frequency, heavy-tailed severity, large-event dominance, and incomplete data as key properties.
4. It describes aggregate annual loss as a sum of individual loss events.
5. It introduces frequency-severity decomposition.
6. It identifies positive support, right skewness, heavy tails, and data sparsity as distribution properties.
7. It explains why tail behavior, aggregation, scenario sensitivity, and truncation matter.
8. It links loss distribution understanding to LC and ILM interpretation.
9. It supports FC-471 and IMP-471 by explaining why loss experience matters.
10. GPT should review mathematical precision and consistency with the formula layer.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | Aggregate loss, frequency, severity, heavy tail, right skewness, data sparsity, scenario sensitivity. |
| Definitions | Annual loss is represented as a sum of event losses and interpreted through frequency-severity decomposition. |
| Formula relationships | Provides conceptual support for LC and ILM; downstream to FC-471, IMP-471, and ARCH-771. |
| Risk concepts | Low-frequency high-severity losses, tail risk, data truncation, scenario losses, capital sensitivity. |

## Architecture Position

MF-471 provides the mathematical interpretation of operational loss behavior. It is upstream of formula
and implementation review, even though the bundle review chain places Formula adjacent to Mathematics.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271, KB-272
-> Analysis: AN-271
-> Mathematics: MF-471
-> Formula: FC-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Candidate KOs implied: Loss Distribution, Aggregate Loss, Frequency-Severity Decomposition, Tail Risk. |
| Capabilities | Candidate capabilities implied: loss distribution interpretation, capital sensitivity analysis. |
| Evidence | No explicit EVD references. |
| Cross References | Links to Reference, Knowledge, Analysis, Formula, Implementation, and Architecture. |
| Related Documents | Includes ARCH-771 in Related Documents after prior deterministic correction. |
| Current Traceability Status | Structurally complete; explicit KO/CAP/EVD mapping pending. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Good conceptual explanation of operational loss behavior and mathematical intuition. |
| Weaknesses | Mathematical notation is high-level; `L = sum(X_i)` references `N` but does not express limits explicitly. |
| Known Issues | Needs mathematical review for notation completeness and consistency with LC/ILM formula usage. |
| Recommended Review Focus | Validate aggregate loss notation, distribution properties, and relationship to SMA loss component. |

---

## 4.6 FC-471 - Operational Risk Capital Formula

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FC-471 |
| File | `04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md` |
| Purpose | Define the technology-neutral calculation contract for operational risk capital under SMA. |
| Layer | Formula Catalog |
| Intended Reader | Reader performing financial, formula, implementation, or architecture review of the capital calculation. |

## Executive Summary

1. FC-471 is the formal formula contract document for Bundle-007.
2. It defines Operational Risk Capital as BIC multiplied by ILM.
3. It defines BIC as a function of BI using regulatory scaling.
4. It identifies lower, middle, and upper BI ranges with 12%, 15%, and 18% coefficients.
5. It defines ILM as `ln(e - 1 + (LC / BIC)^0.8)`.
6. It defines LC as a long-term internal loss data component.
7. It describes a deterministic computation sequence from BI and loss data to capital.
8. It specifies input and output contracts.
9. It lists non-functional requirements: deterministic, traceable, reproducible, technology neutral, immutable, testable.
10. GPT should prioritize financial formula correctness and implementation sufficiency here.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | BIC, ILM, LC, BI, regulatory coefficients, loss observation window, capital calculation contract. |
| Definitions | Operational Risk Capital = BIC x ILM; BIC = f(BI); ILM depends on LC/BIC. |
| Formula relationships | Core formula source for IMP-471 and ARCH-771; conceptually depends on KB-272 and MF-471. |
| Risk concepts | Business scale, loss sensitivity, deterministic calculation, auditability, reproducibility. |

## Architecture Position

FC-471 is the calculation contract. It should be treated as the controlling formula source for
implementation and architecture. It depends on Knowledge Base and Mathematical Foundation content.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271, KB-272
-> Analysis: AN-271
-> Mathematics: MF-471
-> Formula: FC-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Candidate KOs implied: Operational Risk Capital Formula, BIC, ILM, LC, BI. |
| Capabilities | Candidate capabilities implied: deterministic capital calculation, formula validation, regulatory parameter management. |
| Evidence | No explicit EVD references. |
| Cross References | Links to Reference, Knowledge, Analysis, Mathematical Foundation, Implementation, and Architecture. |
| Related Documents | Related Documents block includes upstream layers and MF-471; cross-reference table includes IMP-471 and ARCH-771. |
| Current Traceability Status | Strong formula-to-document traceability; explicit evidence and capability mapping pending. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear formula chain, input/output contract, and non-functional requirements. |
| Weaknesses | Regulatory details are summarized; exact BIC piecewise thresholds and LC calculation details are not fully specified. |
| Known Issues | Needs financial review for exact SMA formula completeness, coefficient use, ILM edge cases, and LC definition. |
| Recommended Review Focus | Financial Review should validate formula accuracy; Architecture Review should validate implementability and auditability. |

---

## 4.7 IMP-471 - Operational Risk Implementation Guide

## Document Information

| Item | Value |
| --- | --- |
| Document ID | IMP-471 |
| File | `06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md` |
| Purpose | Define a technology-neutral procedure for implementing the operational risk capital formula. |
| Layer | Implementation Guide |
| Intended Reader | Reader reviewing implementation readiness, calculation workflow, validation, and auditability. |

## Executive Summary

1. IMP-471 converts the formula contract into a technology-neutral processing guide.
2. It covers BI calculation, loss data ingestion, BIC, LC, ILM, capital aggregation, and audit trail generation.
3. It defines implementation objectives: formula accuracy, input data validation, history preservation, and technology neutrality.
4. It describes processing from business data through result publication.
5. It identifies logical components and responsibilities.
6. It defines input and output models.
7. It describes validation levels: input validation, formula validation, data quality check, regression test.
8. It defines error handling for missing loss data, invalid BI input, inconsistent observation period, and invalid coefficients.
9. It requires traceability from input to intermediate result to final capital.
10. GPT should review whether this is sufficient for implementation and audit handoff.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | BI calculator, loss data loader, LC calculator, ILM calculator, capital calculator, audit trail writer. |
| Definitions | Implementation is a deterministic workflow that reproduces FC-471 and preserves traceability. |
| Formula relationships | Implements FC-471; relies on MF-471 for loss behavior and KB-272 for SMA semantics. |
| Risk concepts | Data validation, observation period consistency, coefficient governance, audit trail, reproducibility. |

## Architecture Position

IMP-471 is downstream of the formula and mathematics layers and upstream of architecture. It translates
formula obligations into component-level implementation responsibilities.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271, KB-272
-> Analysis: AN-271
-> Mathematics: MF-471
-> Formula: FC-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Candidate KOs implied: Implementation Workflow, Calculation Trace, Input Validation, Formula Validation. |
| Capabilities | Candidate capabilities implied: formula execution, audit trace generation, data quality validation. |
| Evidence | No explicit EVD references. |
| Cross References | Links to Reference, Knowledge, Analysis, Mathematical Foundation, Formula, and Architecture. |
| Related Documents | Includes MF-471 and FC-471 after prior deterministic correction. |
| Current Traceability Status | Strong implementation-to-formula traceability; explicit KO/CAP/EVD mapping pending. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear logical flow, component responsibilities, validation strategy, and error classes. |
| Weaknesses | Error-handling policy is conceptual; no detailed test matrix or edge-case treatment. |
| Known Issues | Needs review for whether validation and audit fields are sufficient for actual platform implementation guidance. |
| Recommended Review Focus | Architecture and publication review should assess whether workflow, validation, and traceability are concrete enough for a handbook. |

---

## 4.8 ARCH-771 - Operational Risk Architecture

## Document Information

| Item | Value |
| --- | --- |
| Document ID | ARCH-771 |
| File | `07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md` |
| Purpose | Define the system architecture supporting operational risk capital calculation. |
| Layer | Architecture Guide |
| Intended Reader | Reader reviewing component architecture, data flow, traceability, and quality attributes. |

## Executive Summary

1. ARCH-771 is the final design-layer document for Bundle-007.
2. It defines a system structure for operational risk capital calculation.
3. It covers BI data flow, loss event ingestion, capital calculation pipeline, audit trail, traceability, and reporting.
4. It lists principles: layered processing, separation of concerns, deterministic calculation, traceability, technology neutrality, reusability, governance alignment.
5. It defines logical architecture from business data to reporting and audit.
6. It assigns responsibilities to BI Engine, Loss Event Engine, Loss Component Engine, ILM Engine, Capital Engine, and Reporting/Audit.
7. It requires unidirectional data flow from source data to reports/audit logs.
8. It separates formula definition from architecture while requiring architecture to support formula inputs and outputs.
9. It identifies quality attributes: accuracy, scalability, traceability, maintainability, and reusability.
10. GPT should review architectural completeness and consistency with formula and implementation layers.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | BI Engine, Loss Event Engine, LC Engine, ILM Engine, Capital Engine, Reporting and Audit. |
| Definitions | Architecture is a deterministic, traceable, technology-neutral processing structure for capital outputs. |
| Formula relationships | Integrates FC-471 through the Capital Engine and uses IMP-471 processing responsibilities. |
| Risk concepts | Data lineage, auditability, reproducible capital calculation, regulatory reporting, scalable loss processing. |

## Architecture Position

ARCH-771 is the terminal architecture layer for Bundle-007. It should reflect the full upstream chain and
make the formula and implementation guide architecturally executable.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271, KB-272
-> Analysis: AN-271
-> Mathematics: MF-471
-> Formula: FC-471
-> Implementation: IMP-471
-> Architecture: ARCH-771
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Candidate KOs implied: Operational Risk Architecture, Capital Engine, Reporting and Audit, Traceability Architecture. |
| Capabilities | Candidate capabilities implied: architecture design, calculation pipeline execution, audit and reporting. |
| Evidence | No explicit EVD references. |
| Cross References | Cross-reference table links all major Bundle-007 source layers. |
| Related Documents | Related Documents block does not include MF-471 or IMP-471, while cross-reference table does include IMP-471 and formula relationships. |
| Current Traceability Status | Architecture chain is clear; explicit KO/CAP/EVD mapping and related-document completeness should be reviewed. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear component model, quality attributes, and traceability architecture. |
| Weaknesses | Architecture is high-level; no deployment, interface, data contract, or control-plane detail. |
| Known Issues | Needs review for whether direct dependency on IMP-471 and MF-471 should be stronger in publication metadata. |
| Recommended Review Focus | Architecture Review should validate component responsibilities, data flow, formula integration, and audit architecture sufficiency. |

---

## 4.9 BUNDLE-007 - Operational Risk Review

## Document Information

| Item | Value |
| --- | --- |
| Document ID | BUNDLE-007 |
| File | `08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md` |
| Purpose | Provide bundle closure review and completeness assessment. |
| Layer | Bundle Review |
| Intended Reader | Reader evaluating whether Bundle-007 is complete and ready for next publication workflow stage. |

## Executive Summary

1. BUNDLE-007 is the closure review document for the Operational Risk bundle.
2. It identifies Bundle-007's objective as organizing operational risk across FRKP layers.
3. It lists all planned deliverables across Reference, Knowledge, Analysis, Mathematical Foundation, Formula, Implementation, and Architecture.
4. It defines the traceability sequence from RL-170 to ARCH-771.
5. It asserts coverage for definition, SMA, capital rationale, loss distribution, formula, implementation, and architecture.
6. It asserts layer completeness across all planned layers.
7. It records compliance with FRKP document, bundle, formula, and ID standards.
8. It identifies design principles such as layer separation, determinism, traceability, reusability, and governance alignment.
9. It records overall PASS for bundle structure, layer completeness, traceability, formula consistency, architecture consistency, and governance compliance.
10. GPT should treat this as the source bundle verdict to be challenged during review, not as final publication certification.

## Key Concepts

| Area | Summary |
| --- | --- |
| Concepts | Bundle completeness, layer traceability, coverage assessment, FRKP standard compliance, final bundle verdict. |
| Definitions | Bundle-007 is a completed operational risk review bundle under FRKP structure. |
| Formula relationships | Positions MF-471 and FC-471 inside the bundle sequence and asserts formula consistency. |
| Risk concepts | Operational risk definition, SMA, loss distribution, implementation, architecture. |

## Architecture Position

BUNDLE-007 is not a domain architecture layer. It is the bundle-level review and closure artifact that
summarizes the full layer chain.

```text
Reference Library: RL-170
-> Knowledge Base: KB-271, KB-272
-> Analysis: AN-271
-> Mathematical Foundation: MF-471
-> Formula Catalog: FC-471
-> Implementation Guide: IMP-471
-> Architecture Guide: ARCH-771
-> Bundle Review: BUNDLE-007
```

## Traceability

| Item | Status |
| --- | --- |
| Knowledge Objects | Bundle-level KOs implied but not explicitly identified. |
| Capabilities | Bundle-level publication/review capabilities implied but not explicitly mapped. |
| Evidence | No explicit EVD references. |
| Cross References | Links all eight source deliverables in Related Documents. |
| Related Documents | Complete for Bundle-007 source deliverables. |
| Current Traceability Status | Strong document inventory and layer traceability; explicit KO/CAP/EVD evidence pending. |

## Publication Assessment

| Area | Assessment |
| --- | --- |
| Strengths | Clear deliverables list, traceability chain, coverage matrix, and PASS verdict. |
| Weaknesses | PASS verdict predates later traceability/evidence conditions and should not be treated as final freeze. |
| Known Issues | Needs GPT challenge against PLAN-024 through PLAN-034 workflow state. |
| Recommended Review Focus | Publication Review should reconcile bundle-level PASS with remaining traceability, evidence, and governance conditions. |

---

# 5. Bundle Overview

Bundle-007 organizes operational risk knowledge into a complete FRKP publication stack. It starts with
domain definition and framework concepts, narrows into SMA, explains why capital methodology changed,
defines mathematical and formula foundations, translates formula into implementation workflow, and ends
with architecture guidance and bundle-level closure review.

The bundle is ready for GPT review as a structured review package. It is not yet certified as final
publication freeze because semantic, financial, architecture, publication, and explicit traceability
reviews remain to be recorded.

---

# 6. Reading Order

| Order | Document | Reason |
| ---: | --- | --- |
| 1 | RL-170 | Establish top-level operational risk scope and bundle entry point. |
| 2 | KB-271 | Establish event-control-capital framework. |
| 3 | KB-272 | Establish SMA concepts and BI/BIC/LC/ILM chain. |
| 4 | AN-271 | Review rationale for moving from legacy approaches to SMA. |
| 5 | MF-471 | Review loss distribution foundations behind LC and ILM. |
| 6 | FC-471 | Review the formula contract and capital calculation sequence. |
| 7 | IMP-471 | Review technology-neutral implementation workflow. |
| 8 | ARCH-771 | Review component architecture and traceability architecture. |
| 9 | BUNDLE-007 | Reconcile source-document review findings with bundle closure verdict. |

---

# 7. Dependency Graph

```text
RL-170
  -> KB-271
    -> KB-272
      -> AN-271
        -> MF-471
          -> FC-471
            -> IMP-471
              -> ARCH-771
                -> BUNDLE-007
```

Supplemental dependency relationships:

```text
KB-272 -> FC-471
KB-272 -> IMP-471
MF-471 -> FC-471
FC-471 -> IMP-471
FC-471 -> ARCH-771
IMP-471 -> ARCH-771
BUNDLE-007 -> all Bundle-007 source documents
```

---

# 8. Document Coverage Matrix

| Document | Reference | Knowledge | Analysis | Mathematics | Formula | Implementation | Architecture | Bundle Review |
| --- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| RL-170 | PASS | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT |
| KB-271 | SUPPORT | PASS | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT |
| KB-272 | SUPPORT | PASS | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT |
| AN-271 | SUPPORT | SUPPORT | PASS | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT |
| MF-471 | SUPPORT | SUPPORT | SUPPORT | PASS | SUPPORT | SUPPORT | SUPPORT | SUPPORT |
| FC-471 | SUPPORT | SUPPORT | SUPPORT | SUPPORT | PASS | SUPPORT | SUPPORT | SUPPORT |
| IMP-471 | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | PASS | SUPPORT | SUPPORT |
| ARCH-771 | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | PASS | SUPPORT |
| BUNDLE-007 | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | SUPPORT | PASS |

---

# 9. Coverage Matrix

| Coverage Area | Primary Documents | Status | Review Need |
| --- | --- | --- | --- |
| Operational risk definition | RL-170, KB-271 | PASS | Semantic consistency check. |
| Event/control/capital framework | KB-271 | PASS | Semantic and architecture consistency check. |
| SMA concept | KB-272, FC-471 | PASS | Financial review required. |
| Capital change rationale | AN-271 | PASS | Semantic and financial review required. |
| Loss distribution foundation | MF-471 | PASS | Mathematical review required. |
| Formula contract | FC-471 | CONDITIONAL PASS | Financial formula detail review required. |
| Implementation workflow | IMP-471 | PASS | Architecture/implementation sufficiency review required. |
| Architecture design | ARCH-771 | PASS | Architecture review required. |
| Bundle completeness | BUNDLE-007 | PASS | Publication review required. |
| KO/CAP/EVD traceability | All documents | CONDITIONAL PASS | Explicit mapping review required. |

---

# 10. Cross Reference Matrix

| Document | Upstream References | Downstream References | Observed Status |
| --- | --- | --- | --- |
| RL-170 | Bundle-007 | KB-271, KB-272, AN-271, FC-471, MF-471 | Related block does not directly include IMP-471 or ARCH-771. |
| KB-271 | RL-170 | KB-272, AN-271, MF-471, FC-471, IMP-471, ARCH-771 | Cross-reference table is broad and coherent. |
| KB-272 | RL-170, KB-271 | AN-271, MF-471, FC-471, IMP-471, ARCH-771 | Cross-reference table is broad and coherent. |
| AN-271 | RL-170, KB-271, KB-272 | MF-471, FC-471, IMP-471, ARCH-771 | Cross-reference table is broad and coherent. |
| MF-471 | RL-170, KB-271, KB-272, AN-271 | FC-471, IMP-471, ARCH-771 | Includes corrected downstream architecture reference. |
| FC-471 | RL-170, KB-271, KB-272, AN-271, MF-471 | IMP-471, ARCH-771 | Formula-to-implementation linkage is clear. |
| IMP-471 | RL-170, KB-271, KB-272, AN-271, MF-471, FC-471 | ARCH-771 | Includes corrected MF-471 reference. |
| ARCH-771 | RL-170, KB-271, KB-272, AN-271, FC-471 | IMP-471 | Cross-reference table includes IMP-471; Related Documents block does not include MF-471 or IMP-471. |
| BUNDLE-007 | All Bundle-007 source documents | Future publication workflow | Related Documents block includes all eight source deliverables. |

---

# 11. Formula Coverage

| Formula Item | Covered By | Status | GPT Review Focus |
| --- | --- | --- | --- |
| Business Indicator | KB-272, FC-471, IMP-471, ARCH-771 | PASS | Confirm BI component completeness and terminology. |
| Business Indicator Component | KB-272, FC-471, IMP-471, ARCH-771 | CONDITIONAL PASS | Confirm exact regulatory piecewise thresholds and coefficients. |
| Loss Component | KB-272, MF-471, FC-471, IMP-471, ARCH-771 | CONDITIONAL PASS | Confirm LC definition, observation window, exclusions, and data treatment. |
| Internal Loss Multiplier | KB-272, FC-471, IMP-471, ARCH-771 | CONDITIONAL PASS | Confirm ILM formula, exponent, edge cases, and interpretation. |
| Operational Risk Capital | KB-272, FC-471, IMP-471, ARCH-771 | PASS | Confirm final capital equation and audit trace. |
| Determinism and reproducibility | FC-471, IMP-471, ARCH-771 | PASS | Confirm whether enough implementation constraints are specified. |

---

# 12. Knowledge Coverage

| Knowledge Area | Documents | Status | GPT Review Focus |
| --- | --- | --- | --- |
| Operational risk definition | RL-170, KB-271 | PASS | Confirm definition consistency. |
| Loss events | RL-170, KB-271, MF-471, IMP-471, ARCH-771 | PASS | Confirm event terminology and data lifecycle. |
| Control environment | RL-170, KB-271, AN-271 | PASS | Confirm downstream implementation and architecture coverage. |
| Risk governance | KB-271, AN-271, IMP-471, ARCH-771 | PASS | Confirm governance and audit alignment. |
| Regulatory capital | RL-170, KB-271, KB-272, FC-471 | PASS | Confirm financial correctness. |
| SMA | KB-272, AN-271, FC-471, IMP-471, ARCH-771 | CONDITIONAL PASS | Confirm regulatory details. |
| Explicit KO mapping | All documents | CONDITIONAL PASS | Identify candidate KO references for later governance approval. |

---

# 13. Architecture Coverage

| Architecture Area | Documents | Status | GPT Review Focus |
| --- | --- | --- | --- |
| Data flow | IMP-471, ARCH-771 | PASS | Confirm one-way pipeline and intermediate result traceability. |
| Component responsibility | IMP-471, ARCH-771 | PASS | Confirm separation of BI, loss, LC, ILM, capital, reporting/audit components. |
| Formula integration | FC-471, IMP-471, ARCH-771 | PASS | Confirm architecture satisfies formula inputs and outputs. |
| Audit trail | IMP-471, ARCH-771 | PASS | Confirm audit trail completeness expectations. |
| Error handling | IMP-471 | CONDITIONAL PASS | Confirm missing data, coefficient, observation period, and data quality handling. |
| Scalability and maintainability | ARCH-771 | PASS | Confirm quality attributes are adequate for publication level. |
| Interface/data contracts | IMP-471, ARCH-771 | CONDITIONAL PASS | Review whether publication should include more explicit contracts later. |

---

# 14. Publication Readiness

| Area | Verdict | Justification |
| --- | --- | --- |
| Document inventory | PASS | All nine Bundle-007 documents are present. |
| Layer completeness | PASS | Reference, Knowledge, Analysis, Mathematical Foundation, Formula, Implementation, Architecture, and Bundle Review layers are present. |
| Navigation/cross references | CONDITIONAL PASS | Most cross references are broad; some Related Documents blocks may need review for completeness. |
| Formula completeness | CONDITIONAL PASS | Formula chain exists but regulatory details require financial review. |
| Semantic consistency | CONDITIONAL PASS | No engineering blocker found; GPT semantic review has not been performed. |
| Financial correctness | CONDITIONAL PASS | SMA and ILM formula require domain review. |
| Architecture consistency | CONDITIONAL PASS | Architecture is coherent but high-level; architecture review has not been performed. |
| KO/CAP/EVD traceability | CONDITIONAL PASS | Explicit traceability identifiers are absent and require review/scaffold. |
| Publication index readiness | CONDITIONAL PASS | Prior plans identify master index synchronization as a remaining governance condition. |
| Final publication freeze | FAIL | Freeze is out of scope and cannot pass before GPT review and governance conditions are resolved. |

Overall publication readiness: CONDITIONAL PASS.

Justification: Bundle-007 is structurally complete and ready for GPT review. It is not ready for final
publication freeze because semantic review, financial review, architecture review, explicit traceability
mapping, and governance publication-index decisions remain open.

---

# 15. Open Review Areas

| Area | Review Type | Documents | Focus |
| --- | --- | --- | --- |
| Operational risk definition consistency | Semantic Review | RL-170, KB-271 | Confirm definition and scope consistency. |
| SMA regulatory correctness | Financial Review | KB-272, FC-471 | Validate BI/BIC/LC/ILM descriptions and equation details. |
| Legacy approach narrative | Semantic and Financial Review | AN-271 | Confirm historical and regulatory characterization. |
| Loss distribution notation | Mathematical Review | MF-471 | Validate aggregate loss notation and frequency-severity framing. |
| Formula edge cases | Financial and Architecture Review | FC-471, IMP-471 | Review BIC zero/low values, LC data gaps, coefficient errors, observation period handling. |
| Implementation sufficiency | Architecture Review | IMP-471 | Confirm workflow, validation, error handling, and traceability requirements. |
| Architecture completeness | Architecture Review | ARCH-771 | Confirm component model, data flow, auditability, and quality attributes. |
| Publication metadata | Publication Review | All documents | Review Related Documents completeness, standards references, and bundle closure statements. |
| KO/CAP/EVD mapping | Semantic, Governance, and Traceability Review | All documents | Identify explicit mapping candidates for later approval. |
| Bundle PASS reconciliation | Publication Review | BUNDLE-007 and PLAN-024 through PLAN-034 | Reconcile historical PASS with remaining conditional workflow items. |

---

# 16. Recommended GPT Review Order

| Order | Review Step | Documents | Output Expected |
| ---: | --- | --- | --- |
| 1 | Semantic baseline review | RL-170, KB-271 | Definition and framework consistency findings. |
| 2 | SMA concept review | KB-272 | Regulatory concept findings. |
| 3 | Rationale review | AN-271 | Narrative and claim consistency findings. |
| 4 | Mathematical review | MF-471 | Loss distribution notation and interpretation findings. |
| 5 | Formula review | FC-471 | Formula correctness, missing detail, and edge-case findings. |
| 6 | Implementation review | IMP-471 | Workflow, validation, traceability, and audit findings. |
| 7 | Architecture review | ARCH-771 | Component, data-flow, and quality attribute findings. |
| 8 | Publication review | BUNDLE-007 plus all source documents | Metadata, cross-reference, readiness, and closure-verdict findings. |
| 9 | Traceability mapping review | All documents | KO/CAP/EVD candidate mapping recommendations. |
| 10 | Final GPT verdict | Whole package | GO, CONDITIONAL GO, or NO-GO recommendation for remediation planning. |

---

# 17. Recommended PLAN-035B

| Field | Recommendation |
| --- | --- |
| Plan ID | PLAN-035B |
| Title | Bundle-007 GPT Semantic, Financial, Architecture, and Publication Review |
| Objective | Execute GPT review using this Review Package as the interface between Engineering Review and Semantic Review. |
| Scope | Semantic consistency, financial/regulatory formula review, architecture consistency, publication readiness, traceability mapping candidates, and final GPT review verdict. |
| Inputs | `BUNDLE-007_REVIEW_PACKAGE.md`; Bundle-007 source documents; PLAN-024 through PLAN-034 workflow context. |
| Outputs | GPT Review Report; issue matrix; KO/CAP/EVD candidate mapping; recommended remediation plan. |
| Constraint | Do not modify Bundle-007 source documents during PLAN-035B. |

---

# 18. Final Verdict

GO — Review Package Ready for GPT Review
