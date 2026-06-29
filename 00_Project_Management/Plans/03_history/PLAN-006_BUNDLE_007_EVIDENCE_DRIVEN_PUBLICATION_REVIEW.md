# PLAN-006 - Bundle-007 Evidence-Driven Publication Review

## Document Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-006 |
| Title | Bundle-007 Evidence-Driven Publication Review |
| Status | Completed |
| Category | Bundle Review; Publishing Review; Quality Review |
| Owner | Codex |
| Bundle | Bundle-007 Operational Risk |
| Related Documents | PLAN-005; PROJECT_STATE.md; PLAN_INDEX.md; active.md; CURRENT_WORK.md; next-session.md; RL-170; KB-271; KB-272; AN-271; MF-471; FC-471; IMP-471; ARCH-771; BUNDLE-007 |
| Created | 2026-06-28 |
| Target Completion | 2026-06-28 |
| Completion Date | 2026-06-28 |

## Objective

Review Bundle-007 Operational Risk publication readiness using the evidence register (EVD-000340 through EVD-000349) and publishing mapping created in PLAN-005. Determine whether Bundle-007 may proceed to human publication review.

## Scope

Included:

- Evidence traceability review against EVD-000340 through EVD-000349 for all 8 target documents and the bundle review document.
- Canonical vocabulary consistency across the bundle.
- Basel operational risk alignment (SMA, BIC, BI, ILM, LC, loss data terminology).
- Knowledge graph relationship consistency with PLAN-005 definitions.
- Publication readiness (navigation, cross-references, document structure, metadata).
- Gap identification and gap treatment recommendations.
- Final publication review verdict.

Excluded:

- Bundle freeze (requires separate human review).
- FRKP Version 1.0.0 frozen material modification.
- Document ID, navigation convention, markdown link standard, or FRKP structural changes.
- Non-Operational Risk bundle review.
- Governance changes outside the planning framework.

## Evidence Basis

All reviews use evidence IDs EVD-000340 through EVD-000349 as defined in PLAN-005:

| Evidence ID | Canonical Concept | Target Layer |
| --- | --- | --- |
| EVD-000340 | Operational Risk | RL / KB |
| EVD-000341 | Historical Basel Operational Risk Evolution | AN / KB |
| EVD-000342 | Standardized Measurement Approach | KB / FC |
| EVD-000343 | Business Indicator | KB / FC / IMP |
| EVD-000344 | Business Indicator Component | KB / FC |
| EVD-000345 | Loss Component | KB / MF / FC |
| EVD-000346 | Internal Loss Multiplier | KB / FC |
| EVD-000347 | Operational Loss Data | MF / IMP |
| EVD-000348 | Implementation Considerations | IMP |
| EVD-000349 | Architecture Considerations | ARCH |

## Lifecycle Stage

Bundle Review (per PLAN_STANDARD Section 2: Bundle or Document Review stage).

## Documents Reviewed

| Document ID | File Path |
| --- | --- |
| RL-170 | `01_Reference_Library/07_Operational_Risk/RL-170_OPERATIONAL_RISK_OVERVIEW.md` |
| KB-271 | `02_Knowledge_Base/07_Operational_Risk/KB-271_OPERATIONAL_RISK_FRAMEWORK.md` |
| KB-272 | `02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md` |
| AN-271 | `03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md` |
| MF-471 | `05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md` |
| FC-471 | `04_Formula_Catalog/07_Operational_Risk/FC-471_OPERATIONAL_RISK_CAPITAL_FORMULA.md` |
| IMP-471 | `06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md` |
| ARCH-771 | `07_Architecture/07_Operational_Risk/ARCH-771_OPERATIONAL_RISK_ARCHITECTURE.md` |
| BUNDLE-007 | `08_Bundles/BUNDLE-007_OPERATIONAL_RISK_REVIEW.md` |

## Review Criteria

### 1. Evidence Traceability

Every major operational risk claim should map to an evidence ID (EVD-000340 through EVD-000349) or accepted FRKP internal standard.

| Document | Evidence ID Mapping (per PLAN-005) | Inline EVD References | Result |
| --- | --- | --- | --- |
| RL-170 | EVD-000340; EVD-000341; EVD-000342 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| KB-271 | EVD-000340; EVD-000341; EVD-000347 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| KB-272 | EVD-000342; EVD-000343; EVD-000344; EVD-000345; EVD-000346 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| AN-271 | EVD-000341; EVD-000342; EVD-000347 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| MF-471 | EVD-000345; EVD-000347 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| FC-471 | EVD-000342; EVD-000343; EVD-000344; EVD-000345; EVD-000346 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| IMP-471 | EVD-000343; EVD-000347; EVD-000348 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| ARCH-771 | EVD-000348; EVD-000349 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |
| BUNDLE-007 | EVD-000340 through EVD-000349 | None | No inline evidence IDs. Mapping exists in PLAN-005 only. |

**Finding**: No Bundle-007 document contains inline EVD evidence ID references. The PLAN-005 publishing mapping provides document-level evidence traceability. Inline evidence ID citation is not standard across existing FRKP documents. The PLAN-005 mapping is sufficient for evidence-driven publication review.

**Treatment**: Accept as-is. Future enhancements may add inline EVD annotations when the FRKP evidence citation standard matures.

### 2. Terminology Consistency

Canonical vocabulary terms from PLAN-005 must be used consistently across the bundle.

| Term | RL-170 | KB-271 | KB-272 | AN-271 | MF-471 | FC-471 | IMP-471 | ARCH-771 | Result |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Operational Risk | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | Consistent |
| Standardized Measurement Approach / SMA | ✔ | ✔ | ✔ | ✔ | — | ✔ | — | — | Consistent where applicable |
| Business Indicator / BI | — | — | ✔ | — | — | ✔ | ✔ | ✔ | Consistent where applicable |
| Business Indicator Component / BIC | — | — | ✔ | — | — | ✔ | ✔ | ✔ | Consistent where applicable |
| Loss Component / LC | — | — | ✔ | — | ✔ | ✔ | ✔ | ✔ | Consistent where applicable |
| Internal Loss Multiplier / ILM | — | — | ✔ | — | ✔ | ✔ | ✔ | ✔ | Consistent where applicable |
| Operational Loss / Loss Data | ✔ | ✔ | — | — | ✔ | ✔ | ✔ | ✔ | Consistent where applicable |

**Finding**: Canonical vocabulary is used consistently. Each document uses the terms appropriate to its layer. No terminology conflicts or incorrect usage detected. The Korean-language definitions align with the English canonical terms.

### 3. Basel Operational Risk Alignment

| Check | RL-170 | KB-271 | KB-272 | AN-271 | MF-471 | FC-471 | IMP-471 | ARCH-771 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SMA correctly described | ✔ | ✔ | ✔ | ✔ | — | ✔ | — | — |
| BI as business-scale measure | — | — | ✔ | — | — | ✔ | ✔ | ✔ |
| BIC piecewise regulatory scaling | — | — | ✔ | — | — | ✔ | ✔ | ✔ |
| LC from internal loss data | — | — | ✔ | — | ✔ | ✔ | ✔ | ✔ |
| ILM as LC/BIC relationship | — | — | ✔ | — | ✔ | ✔ | ✔ | ✔ |
| Capital = BIC x ILM | — | — | ✔ | — | — | ✔ | ✔ | ✔ |
| Loss data observation window | — | — | ✔ (10yr) | — | — | ✔ | ✔ | — |
| BCBS D424 alignment | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |

**Finding**: All documents are correctly aligned with BCBS D424 (Basel III: Finalising post-crisis reforms). The SMA formula structure in FC-471 correctly states `BIC x ILM` with `ILM = ln(e - 1 + (LC/BIC)^0.8)`. The BIC marginal coefficients (12%/15%/18%) match the regulatory ranges.

### 4. Knowledge Graph Relationship Consistency

| Relationship (per PLAN-005) | Evidence | Coverage in Bundle | Result |
| --- | --- | --- | --- |
| Operational Risk -> SMA | EVD-000340; EVD-000342 | RL-170, KB-271, KB-272, AN-271 | Consistent |
| Historical Evolution -> AMA -> SMA | EVD-000341; EVD-000342 | RL-170, KB-271, KB-272, AN-271 | Consistent |
| SMA -> BI | EVD-000342; EVD-000343 | KB-272, FC-471, IMP-471 | Consistent |
| BI -> BIC | EVD-000343; EVD-000344 | KB-272, FC-471 | Consistent |
| Operational Loss Data -> LC | EVD-000345; EVD-000347 | KB-272, MF-471, FC-471, IMP-471 | Consistent |
| BIC + LC -> ILM | EVD-000344; EVD-000345; EVD-000346 | KB-272, FC-471, IMP-471 | Consistent |
| BIC + ILM -> Capital | EVD-000342; EVD-000344; EVD-000346 | FC-471, IMP-471 | Consistent |
| Capital -> Implementation | EVD-000348 | IMP-471 | Consistent |
| Implementation -> Architecture | EVD-000348; EVD-000349 | IMP-471, ARCH-771 | Consistent |

**Finding**: Knowledge graph relationships defined in PLAN-005 are consistently represented across the bundle documents.

### 5. Publishing Readiness

#### Document Structure

| Document | Doc Info | Navigation | FRKP-NAV markers | Layer paths | Revision History | Result |
| --- | --- | --- | --- | --- | --- | --- |
| RL-170 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| KB-271 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| KB-272 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| AN-271 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| MF-471 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| FC-471 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| IMP-471 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| ARCH-771 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |
| BUNDLE-007 | ✔ | ✔ | ✔ | ✔ | ✔ | Ready |

#### Navigation Cross-Reference Completeness

| Document | Related Documents Listed | Missing References |
| --- | --- | --- |
| RL-170 | KB-271, KB-272, AN-271, FC-471, MF-471 | IMP-471, ARCH-771 |
| KB-271 | RL-170, KB-272, AN-271, FC-471, MF-471 | IMP-471, ARCH-771 |
| KB-272 | RL-170, KB-271, AN-271, FC-471, MF-471 | IMP-471, ARCH-771 |
| AN-271 | RL-170, KB-271, KB-272, MF-471, FC-471 | IMP-471, ARCH-771 |
| MF-471 | RL-170, KB-271, KB-272, FC-471, IMP-471 | AN-271, ARCH-771 |
| FC-471 | RL-170, KB-271, KB-272, AN-271, MF-471 | IMP-471, ARCH-771 |
| IMP-471 | RL-170, KB-271, KB-272, AN-271, FC-471 | MF-471, ARCH-771 |
| ARCH-771 | RL-170, KB-271, KB-272, AN-271, FC-471 | MF-471, IMP-471 |
| BUNDLE-007 | RL-170, KB-271, KB-272, AN-271, MF-471, FC-471, IMP-471, ARCH-771 | None |

**Finding**: Most documents omit downstream IMP-471 and/or ARCH-771 from their navigation-related-documents sections. This is a minor completeness gap. All documents remain navigable via the FRKP layer hierarchy and bundle review document.

#### Cross References Section Completeness

| Document | Cross References Present | Completeness |
| --- | --- | --- |
| RL-170 | No Cross References section | N/A (Reference Library top-layer) |
| KB-271 | Section 10 | ✔ (all Bundle-007 docs) |
| KB-272 | Section 11 | Missing IMP-471, ARCH-771 |
| AN-271 | No Cross References section | N/A |
| MF-471 | No Cross References section | N/A |
| FC-471 | Section 13 | ✔ (all Bundle-007 docs) |
| IMP-471 | Section 12 | ✔ (all Bundle-007 docs) |
| ARCH-771 | Section 11 | ✔ (all Bundle-007 docs) |

**Finding**: KB-272 is missing IMP-471 and ARCH-771 from its Cross References table. Minor gap.

### 6. Remaining Gaps

| Gap | Severity | Affected Documents | Recommendation |
| --- | --- | --- | --- |
| No inline evidence ID citations | Low | All documents | Accept as-is. PLAN-005 provides document-level mapping. Consider inline EVD citations in future standard. |
| Navigation Related Documents missing IMP-471 and/or ARCH-771 | Low | RL-170, KB-271, KB-272, AN-271, MF-471, FC-471, IMP-471, ARCH-771 | Add missing references for completeness. Not publication-blocking. |
| KB-272 Cross References missing IMP-471 and ARCH-771 | Low | KB-272 | Add missing references for completeness. Not publication-blocking. |
| Jurisdiction-specific national implementation options (from PLAN-005) | Low | None (deferred) | Accepted gap from PLAN-005. Not required for Bundle-007 baseline. |
| Human regulatory review | Medium | All documents | Required before freeze, not before publication review. Accept for this stage. |

## Corrections Made

No content edits were made to any Bundle-007 document. All findings are recorded in this review for human consideration.

**Rationale**: Identified gaps are minor and do not impede publication review. Inline evidence IDs are not an established FRKP document convention. Cross-reference gaps in navigation sections do not prevent user navigation via the FRKP layer hierarchy and bundle review document. Making additive edits would improve quality but is not required for publication review readiness.

## Final Verdict

**CONDITIONAL GO** — Publication review may proceed.

### Conditions

1. **Navigation cross-references**: Humans conducting publication review should note that some navigation Related Documents sections do not list all Bundle-007 documents (IMP-471 and ARCH-771 are most frequently omitted). This does not block review but may be corrected before freeze.
2. **Evidence traceability**: All documents have PLAN-005 evidence mappings at the document level. Inline evidence ID citations are absent. Humans may decide whether inline citations are needed before freeze.
3. **Terminology and content**: No corrections needed. The bundle is terminologically consistent and Basel-aligned.
4. **Boundary**: Bundle is within scope. No unrelated bundles or V1.0.0 changes detected.

### Verdict Rationale

- Evidence traceability: PASS (document-level mapping via PLAN-005 is sufficient for this stage).
- Canonical vocabulary: PASS (consistent across all layers).
- Basel operational risk alignment: PASS (SMA, BI, BIC, LC, ILM correctly described).
- Knowledge graph consistency: PASS (relationships verified against PLAN-005).
- Publication readiness: PASS WITH OBSERVATIONS (minor cross-reference gaps; no structural issues).
- Boundary discipline: PASS (no unrelated changes).

## Recommended Next PLAN

PLAN-007 — Bundle-007 Freeze Preparation and Human Review Coordination.

PLAN-007 should:
1. Address navigation cross-reference gaps identified in PLAN-006.
2. Prepare evidence alignment summary for human reviewers.
3. Define freeze acceptance criteria.
4. Coordinate human review of Bundle-007 content.
5. Recommend freeze or further revision.

## Closure Summary

PLAN-006 completed an evidence-driven publication review of all 9 Bundle-007 documents (8 target documents + 1 bundle review) against evidence IDs EVD-000340 through EVD-000349, canonical vocabulary, Basel operational risk alignment, knowledge graph consistency, and publication readiness. Six minor gaps were identified. No content edits were made. The verdict is CONDITIONAL GO. The recommended next plan is PLAN-007.

No FRKP Bundle-007 content was modified and no commit was created.
