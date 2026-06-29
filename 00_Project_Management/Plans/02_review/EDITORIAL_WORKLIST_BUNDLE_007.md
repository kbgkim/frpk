# EDITORIAL_WORKLIST — Bundle-007 Operational Risk

## Document Information

| Item | Value |
| --- | --- |
| Worklist ID | EWL-BUNDLE-007-001 |
| Bundle | Bundle-007 — Operational Risk |
| Created | 2026-06-29 |
| Source | PLAN-024 Repository Audit |
| Owner | Codex / GPT (per AI operating model) |

---

## Priority Classification

| Priority | Definition | Action Required |
| --- | --- | --- |
| P1 | Blocking — Must fix before any further publication activity | Immediate correction |
| P2 | Required — Must fix for publication readiness gate passage | Before release |
| P3 | Recommended — Quality improvement, non-blocking | When convenient |

---

## P1 — Critical Corrections

### P1-001: Add Cross References Section to AN-271

| Field | Value |
| --- | --- |
| Document | `03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md` |
| Location | After §8 (Relationship with Bundle-007), before §9 (Summary) |
| Action | Add formal Cross References table listing RL-170, KB-271, KB-272, MF-471, FC-471, IMP-471, ARCH-771 |
| Rationale | AN-271 is missing the formal Cross References section that other Bundle-007 documents have |

### P1-002: Add Cross References Section to MF-471

| Field | Value |
| --- | --- |
| Document | `05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md` |
| Location | After §9 (Relationship with Bundle-007), before §10 (Summary) |
| Action | Add formal Cross References table listing RL-170, KB-271, KB-272, AN-271, FC-471, IMP-471, ARCH-771 |
| Rationale | MF-471 is missing the formal Cross References section |

### P1-003: Complete KB-272 Cross References

| Field | Value |
| --- | --- |
| Document | `02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md` |
| Location | §11 Cross References |
| Action | Add IMP-471 and ARCH-771 to the Cross References table |
| Rationale | KB-272 §11 currently omits IMP-471 and ARCH-771 |

### P1-004: Complete KB-272 Related Documents

| Field | Value |
| --- | --- |
| Document | `02_Knowledge_Base/07_Operational_Risk/KB-272_STANDARDIZED_MEASUREMENT_APPROACH.md` |
| Location | Navigation > Related Documents |
| Action | Add IMP-471 and ARCH-771 references |
| Rationale | KB-272 navigation block omits downstream implementation and architecture documents |

### P1-005: Complete AN-271 Related Documents

| Field | Value |
| --- | --- |
| Document | `03_Analysis/07_Operational_Risk/AN-271_WHY_OPERATIONAL_RISK_CAPITAL_CHANGED.md` |
| Location | Navigation > Related Documents |
| Action | Add IMP-471 and ARCH-771 references |
| Rationale | AN-271 navigation block omits downstream implementation and architecture documents |

---

## P2 — Required Improvements

### P2-001: Add ARCH-771 to MF-471 Related Documents

| Field | Value |
| --- | --- |
| Document | `05_Mathematical_Foundation/07_Operational_Risk/MF-471_OPERATIONAL_RISK_LOSS_DISTRIBUTION.md` |
| Location | Navigation > Related Documents |
| Action | Add ARCH-771 reference |

### P2-002: Add MF-471 to IMP-471 Related Documents

| Field | Value |
| --- | --- |
| Document | `06_Implementation_Guide/07_Operational_Risk/IMP-471_OPERATIONAL_RISK_IMPLEMENTATION.md` |
| Location | Navigation > Related Documents |
| Action | Add MF-471 reference |

### P2-003: Add FRKC Evidence Traceability

| Field | Value |
| --- | --- |
| Documents | All 8 Bundle-007 documents + BUNDLE-007 review |
| Action | Add FRKC evidence references (EVD-*) to each document following FRKP-FRKC-001 evidence-driven publishing workflow |
| Source | FRKC evidence register (EVD-000340 through EVD-000349 per PLAN-006) |
| Guidance | Add Evidence section or traceability block per FRKP-PROGRAM-002 §5 |

### P2-004: Add FAEP Capability References

| Field | Value |
| --- | --- |
| Documents | All 8 Bundle-007 documents |
| Action | Add FAEP Capability (CAP-*) references appropriate to each document's content layer |
| Source | FAEP-CAP-001 Candidate Capability Registry |
| Guidance | Add Capability Mapping block per FRKP-PROGRAM-002 §5.2 |

### P2-005: Add Knowledge Object References

| Field | Value |
| --- | --- |
| Documents | All 8 Bundle-007 documents |
| Action | Add Knowledge Object (KO-*) references appropriate to each document's content layer |
| Source | FRKP-005 (FRKC Knowledge OS) knowledge object contract definitions |
| Guidance | Add KO Reference block per FRKP-PROGRAM-002 §5.1 |

### P2-006: Synchronize FRKP-DOC-100 Master Index

| Field | Value |
| --- | --- |
| Action | Add Bundle-007 documents to FRKP-DOC-100 master document index |
| Scope | All 8 documents + bundle review |
| Note | Verify FRKP-DOC-100 currently lists Bundle-007 entries |

---

## P3 — Quality Enhancements

### P3-001: Align Summary Section Language

| Field | Value |
| --- | --- |
| Documents | RL-170 (§10), KB-271 (§11), KB-272 (§12), AN-271 (§9), MF-471 (§10), FC-471 (§14), IMP-471 (§13), ARCH-771 (§12) |
| Action | Standardize summary language. Currently: RL, KB, AN, MF summaries in Korean; FC, IMP, ARCH summaries in English |
| Recommendation | Use bilingual format or consistent English (per publication standard) |

### P3-002: Verify All Relative Links Resolve Correctly

| Field | Value |
| --- | --- |
| Documents | All Bundle-007 documents |
| Action | Systematic link validation across all navigation blocks and cross references |
| Tool | Manual or script-based relative link checker |

### P3-003: Align with FRKP-PROGRAM-002 Editorial Standard

| Field | Value |
| --- | --- |
| Documents | All Bundle-007 documents |
| Action | Review against FRKP-PROGRAM-002 editorial rules: heading depth, line length, prohibited patterns, terminology, glossary references |
| Note | Bundle-007 documents predate FRKP-PROGRAM-002; compliance gap expected |

### P3-004: Review Navigation Previous/Next Consistency

| Field | Value |
| --- | --- |
| Documents | All Bundle-007 documents |
| Action | Evaluate whether inter-document Previous/Next chaining should be across layers (e.g., KB-272 → AN-271) |
| Note | Current convention uses Previous/Next within same layer only |

### P3-005: Evaluate Against FRKP-PROGRAM-004 Quality Gate

| Field | Value |
| --- | --- |
| Documents | Bundle-007 review document |
| Action | Run formal quality gate assessment across 8 dimensions (Technical Accuracy, Architecture Consistency, Knowledge Traceability, Evidence Traceability, Editorial Completeness, Publishing Standards Compliance, AI Readiness, IB Readiness) |

---

## Summary

| Priority | Count | Key Actions |
| --- | --- | --- |
| P1 | 5 | Cross References sections, missing document links in navigation |
| P2 | 6 | Evidence traceability, capability mapping, KO references, master index |
| P3 | 5 | Language alignment, link validation, editorial standard compliance |
| **Total** | **16** | |

## GPT Assignment Notes

GPT (ChatGPT) should perform:
- Cross References section authoring (P1-001, P1-002)
- Evidence, capability, and KO reference mapping (P2-003, P2-004, P2-005)
- Editorial language alignment (P3-001)
- Quality gate assessment (P3-005)

Codex should perform:
- Navigation block editing (P1-003, P1-004, P1-005, P2-001, P2-002)
- Link validation (P3-002)
- FRKP-DOC-100 synchronization (P2-006)
