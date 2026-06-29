# PLAN-014 — FRKC Knowledge Operating System Architecture

## Document Information

| Item | Value |
| --- | --- |
| Plan ID | PLAN-014 |
| Title | FRKC Knowledge Operating System Architecture |
| Status | Completed |
| Category | Architecture Definition; Governance Definition |
| Owner | Codex |
| Bundle | None (Knowledge Platform Architecture) |
| Related Documents | PLAN-001; PLAN-011; PLAN-012; PLAN-013; PROJECT_STATE.md; PLAN_INDEX.md; active.md; CURRENT_WORK.md; next-session.md; FAEP-000; FAEP-001; FAEP-002; FRKP-003; FRKP-004; FRKP-005; FRKP-FRKC-001; FRKP-000; FRKP-001; FRKP-002; FRKP-ID-001; FRKP-DOC-001 |
| Created | 2026-06-28 |
| Target Completion | 2026-06-28 |
| Completion Date | 2026-06-28 |

## Objective

Define FRKC as the Knowledge Operating System (Knowledge OS) of FAEP. Clarify its responsibility, architecture, contracts, lifecycle, metadata, ontology, evidence model, semantic model, AI retrieval model, and integration model. FRKC is NOT a document repository. FRKC is NOT FRKP. FRKC is the canonical knowledge platform upon which all other engines depend.

## Scope

**Included:**

- Define FRKC as the Knowledge Operating System (Knowledge OS) of FAEP.
- Define FRKC Philosophy: Knowledge First, Canonical First, Evidence First, Ontology First, AI Native, Versioned Knowledge, Semantic Navigation, Knowledge as an Operating System.
- Define 15 Core Responsibilities: Canonical Knowledge, Evidence, Regulation, Terminology, Ontology, Taxonomy, Knowledge Graph, Semantic Graph, Metadata, Cross References, RAG Corpus, AI Retrieval, Versioned Knowledge, Publication Source, Execution Source.
- Define 6-layer Knowledge Architecture: Canonical, Evidence, Semantic, Publication, Execution, AI.
- Define 11 Knowledge Object contracts: Knowledge Item, Evidence Item, Formula Knowledge, Regulation, Definition, Glossary, Concept, Semantic Relation, Ontology Node, Knowledge Collection, Knowledge Version.
- Define mandatory Metadata Model with 18 fields, 10 validation rules, and 5 schema evolution rules.
- Define Ontology Model with 8 principles, 6 concept types, 10 relation types, and lifecycle.
- Define Knowledge Graph relationship model across 6 traversal hops: Concept → Evidence → Formula → Risk Analytics → Runtime → Publication → AI Agent.
- Define Evidence Graph with 6-stage lifecycle, 6 relationship types, 6 versioning rules, and 6 integrity rules.
- Define Semantic Retrieval model: AI retrieval interface (5 operations), RAG corpus preparation (6 steps), context assembly (7 rules, structured output), knowledge ranking (6 factors with weights), citation model (6 rules with machine-parseable format).
- Define Integration Contracts with FAEP Core, FRKP, Risk Platform, AI Platform, and Business Platforms (4 integration points each).
- Define Version Strategy for Knowledge, Evidence, Ontology, Semantic, and Publication versions.
- Define Future Evolution: Knowledge Federation, Distributed Knowledge, External Regulatory Sources, Machine-readable Knowledge, Knowledge APIs.
- Document 20 Architecture Decisions (AD-001 through AD-020).
- Document 10 Open Issues (OPI-FRKC-001 through OPI-FRKC-010).
- Document 12 Deferred Items (DEF-FRKC-001 through DEF-FRKC-012).
- Define 5-Phase Future Roadmap (Phase 1: Knowledge OS → Phase 5: Independent FRKC Platform) with milestones.
- Create FRKP-005 governance document.
- Update PLAN_INDEX.md, active.md, CURRENT_WORK.md, next-session.md, PROJECT_STATE.md.

**Excluded:**

- Modify Version 1.0.0 frozen artifacts (NOT PERMITTED).
- Modify Bundle-007 frozen artifacts (NOT PERMITTED).
- Modify existing Bundle IDs (NOT PERMITTED).
- Modify existing Document IDs (NOT PERMITTED).
- Modify navigation standards (NOT PERMITTED).
- Modify Markdown link standards (NOT PERMITTED).
- Modify repository structure (NOT PERMITTED).
- Modify existing Release artifacts (NOT PERMITTED).
- Create new projects (NOT PERMITTED — architecture only).
- Migrate repositories (NOT PERMITTED).
- Implement knowledge graph database (NOT PERMITTED).
- Implement ontology serialization (NOT PERMITTED).
- Implement RAG corpus or vector store (NOT PERMITTED).
- Implement Knowledge API (NOT PERMITTED).
- Implement AI retrieval interface (NOT PERMITTED).
- Implement external regulatory source ingestion (NOT PERMITTED).
- Create Git commit, tag, or Release (NOT PERMITTED).
- Resolve Version 1.1 release blockers (BLK-RC-001 through BLK-RC-005) (NOT PERMITTED).
- Implementation work of any kind (NOT PERMITTED — architecture and governance specification only).

---

## Part 1: Files Created

| # | File | Description |
| --- | --- | --- |
| 1 | `00_Project_Management/Governance/FRKP-005_FRKC_KNOWLEDGE_OPERATING_SYSTEM.md` | FRKC Knowledge Operating System governance document — defines FRKC as the canonical knowledge platform of FAEP, including philosophy, responsibilities, architecture, knowledge objects, metadata model, ontology model, knowledge graph, evidence graph, semantic retrieval, integration contracts, version strategy, future evolution, architecture decisions, open issues, deferred items, and future roadmap |

## Part 2: Files Updated

| # | File | Change |
| --- | --- | --- |
| 1 | `00_Project_Management/Plans/PLAN_INDEX.md` | Added PLAN-014 entry |
| 2 | `00_Project_Management/Plans/active.md` | Added PLAN-014 to Recently Completed |
| 3 | `00_Project_Management/Plans/CURRENT_WORK.md` | Added PLAN-014 completion record |
| 4 | `00_Project_Management/Plans/next-session.md` | Updated current state and next recommended actions |
| 5 | `00_Project_Management/Sessions/PROJECT_STATE.md` | Updated current plan, verdict, next recommended plan |

---

## Part 3: Knowledge OS Summary

FRKC is defined as the **Knowledge Operating System (Knowledge OS)** of FAEP — the canonical knowledge hub used by every Platform within FAEP. It is NOT a document repository. It is NOT FRKP. It is the active knowledge substrate upon which all other engines depend.

### Philosophy Summary

| Philosophy | Core Principle |
| --- | --- |
| Knowledge First | Knowledge is the primary asset; all artifacts serve knowledge |
| Canonical First | Every concept exists in exactly one authoritative location |
| Evidence First | Every claim is traceable to verifiable evidence |
| Ontology First | Knowledge is a structured ontology, not a flat collection |
| AI Native | All artifacts are AI-agent processable by design |
| Versioned Knowledge | All knowledge artifacts are versioned |
| Semantic Navigation | Knowledge is navigable through typed semantic relationships |
| Knowledge as an Operating System | FRKC is the active knowledge substrate; without it, no platform operates |

### Responsibility Summary

| Domain | Responsibility |
| --- | --- |
| Knowledge | Canonical Knowledge maintenance |
| Evidence | Evidence registration, certification, traceability |
| Regulatory | Regulation curation and mapping |
| Glossary | Terminology and definition governance |
| Structure | Ontology definition and evolution |
| Classification | Taxonomy and domain hierarchy |
| Graph | Knowledge Graph and Semantic Graph maintenance |
| Metadata | Metadata schema definition and validation |
| AI | RAG Corpus curation, AI Retrieval interface |
| Versioning | Version management for all knowledge objects |
| Integration | Publication Source for FRKP, Execution Source for Risk Platform |

---

## Part 4: Knowledge Architecture

### Six-Layer Architecture

```
┌──────────────────────────────────────┐
│           AI LAYER                    │
│  Chunks · Embeddings · Retrieval      │
├──────────────────────────────────────┤
│        EXECUTION LAYER                │
│  Executable Formulas · Runtime Maps   │
├──────────────────────────────────────┤
│       PUBLICATION LAYER               │
│  Published Docs · Navigation          │
├──────────────────────────────────────┤
│        SEMANTIC LAYER                  │
│  Ontology · Knowledge Graph           │
├──────────────────────────────────────┤
│        EVIDENCE LAYER                 │
│  Evidence IDs · Registers · Mapings   │
├──────────────────────────────────────┤
│        CANONICAL LAYER                │
│  Concepts · Definitions · Glossary    │
└──────────────────────────────────────┘
```

### Knowledge Object Contracts

| Object | Key Fields | Lifecycle |
| --- | --- | --- |
| Knowledge Item | knowledge_id, layer, domain, evidence_ids, ontology_nodes | Draft → Review → Approved → Frozen → Superseded → Archived |
| Evidence Item | evidence_id, source_type, knowledge_ids, certification | Identified → Registered → Mapped → Certified → Superseded → Archived |
| Formula Knowledge | formula_id, symbols, derivation, parameters, evidence_ids | Specified → Derived → Cataloged → Implemented → Validated → Frozen → Superseded |
| Regulation | regulation_id, jurisdiction, effective_date, knowledge_ids | Active → Superseded → Proposed → Archived |
| Definition | definition_id, term, definition, ontology_node | Draft → Approved → Frozen → Superseded |
| Glossary | glossary_id, domain, terms | Draft → Published → Frozen → Superseded |
| Concept | concept_id, concept_type, ontology_parent, semantic_relations | Draft → Active → Deprecated → Archived |
| Semantic Relation | relation_id, source_id, target_id, relation_type, weight | Active → Deprecated |
| Ontology Node | node_id, node_type, parent_id, children, properties | Draft → Active → Deprecated → Archived |
| Knowledge Collection | collection_id, object_ids, collection_type | Draft → Published → Frozen → Archived |
| Knowledge Version | version_id, object_versions, changelog | Draft → Released → Frozen → Superseded |

### Metadata Model

| Aspect | Detail |
| --- | --- |
| Mandatory Fields | 18 fields (id, type, title, version, status, created_by, created_date, updated_by, updated_date, owner, domain, layer, evidence_ids, ontology_nodes, tags, cross_references, hash, metadata_version) |
| Validation Rules | 10 rules (MV-001 through MV-010) covering uniqueness, versioning, evidence anchoring, ontology anchoring, cross-reference resolution, temporal ordering, content integrity, lifecycle transitions, schema conformance |
| Schema Evolution | 5 rules (MSE-001 through MSE-005) governing field addition, deprecation, and removal |

### Ontology Model

| Aspect | Detail |
| --- | --- |
| Principles | 8 principles: Single Inheritance, Typed Relations, Domain Isolation, Versioned Ontology, AI-Readable, Minimal Commitment, Progressive Refinement, Evidence Anchoring |
| Concept Types | 6 types: Event, Entity, Measure, Process, Relation, Rule |
| Relation Types | 10 types: is_a, part_of, defined_by, supported_by, derived_from, computed_by, measured_by, governed_by, triggers, mitigates |
| Lifecycle | Proposed → Draft → Review → Active → Deprecated → Archived |

---

## Part 5: Knowledge Graph Summary

### Relationship Model

```
Concept
   │  defined_by, supported_by, referenced_in
   ▼
Evidence
   │  supports, mandates, defines_parameter
   ▼
Formula
   │  computed_by, parameterized_by, validated_against
   ▼
Risk Analytics
   │  executed_in, produced_by, depends_on
   ▼
Runtime
   │  documented_in, published_as, referenced_by
   ▼
Publication
   │  consumed_by, retrieved_from, cited_as
   ▼
AI Agent
```

### Evidence Graph

| Aspect | Detail |
| --- | --- |
| Lifecycle | Identified → Registered → Mapped → Certified → Superseded → Archived |
| Relationship Types | supports, contradicts, supersedes, extends, depends_on, referenced_by |
| Versioning Rules | 6 rules (EV-001 through EV-006): immutable IDs, ancestry chains, supersession through relations, mapping versioning, per-version certification, snapshot registers |
| Integrity Rules | 6 rules (EI-001 through EI-006): evidence anchoring requirement, bidirectional resolvability, certification metadata, uncertified flagging, supersession review, orphan detection |

---

## Part 6: Ontology Summary

| Aspect | Status |
| --- | --- |
| Ontology principles | Defined (8 principles) |
| Concept types | Defined (6 types: Event, Entity, Measure, Process, Relation, Rule) |
| Relation types | Defined (10 types: is_a, part_of, defined_by, supported_by, derived_from, computed_by, measured_by, governed_by, triggers, mitigates) |
| Ontology lifecycle | Defined (Proposed → Draft → Review → Active → Deprecated → Archived) |
| Version independence | Defined — ontology version independent of knowledge corpus version |
| Progressive refinement | Defined — ontology starts coarse and refines as knowledge deepens |

---

## Part 7: Integration Summary

| FAEP Platform | Integration Points | Key Contracts |
| --- | --- | --- |
| FAEP Core | IP-FRKC-001 (Core → FRKC), IP-FRKC-002 (FRKC → Core) | CC-KNW-001, CC-EVD-001, CC-MET-001, CC-VER-001 |
| FRKP (Publishing) | IP-FRKP-001 (FRKC → FRKP), IP-FRKP-002, IP-FRKP-003, IP-FRKP-004 | Knowledge Source, Evidence Source, Publication Feedback |
| Risk Platform | IP-RSK-001 (FRKC → Risk), IP-RSK-002, IP-RSK-003, IP-RSK-004 | Formula Source, Parameter Definitions, Execution Context |
| AI Platform | IP-AI-001 (FRKC → AI), IP-AI-002, IP-AI-003, IP-AI-004 | RAG Corpus, Semantic Retrieval, Ontology, Citation Model |
| Business Platforms | IP-BIZ-001 (FRKC → Biz), IP-BIZ-002, IP-BIZ-003, IP-BIZ-004 | Domain Knowledge, Glossary, Regulatory Mappings, Evidence Traceability |

---

## Part 8: Architecture Decisions

| AD ID | Title | Decision |
| --- | --- | --- |
| AD-001 | FRKC as Knowledge Operating System | FRKC is the Knowledge OS of FAEP — not a document repository, not FRKP |
| AD-002 | Six-Layer Knowledge Architecture | FRKC knowledge organized into Canonical, Evidence, Semantic, Publication, Execution, AI layers |
| AD-003 | Canonical First — Single Source of Truth | Every concept exists in exactly one canonical FRKC location; no duplication |
| AD-004 | Evidence-Anchored Knowledge | Every artifact traceable to at least one certified evidence source |
| AD-005 | Formal Ontology with Typed Relations | FRKC defines a formal ontology with typed relations and single inheritance |
| AD-006 | Knowledge Graph as Primary Navigation | Knowledge graph is the primary navigation model; directory hierarchy is secondary |
| AD-007 | Separate Evidence Graph | Evidence objects have their own graph with independent lifecycle and versioning |
| AD-008 | AI-Native Knowledge Design | All FRKC artifacts designed for AI agent consumption by default |
| AD-009 | RAG Corpus as Derived Artifact | RAG corpus is computed from canonical layers, not separately maintained |
| AD-010 | Semantic Versioning for All Objects | Every knowledge object uses semantic versioning (MAJOR.MINOR.PATCH) |
| AD-011 | Integration Through Contracts | FRKC integrates through defined contracts, not direct access |
| AD-012 | FRKC as Separate Repository | FRKC maintained as separate repository; no platform owns the knowledge |
| AD-013 | Evidence Chain in Retrieval Results | Every retrieval result includes the complete evidence chain |
| AD-014 | Knowledge Lifecycle with Freeze | Knowledge objects follow lifecycle with Frozen state for stable baselines |
| AD-015 | Progressive Ontology Refinement | Ontology starts coarse and progressively refines |
| AD-016 | Ontology and Knowledge Version Independence | Ontology version independent of knowledge corpus version |
| AD-017 | Evidence Certification Precedes Publication | Evidence must be certified before dependent knowledge objects can publish |
| AD-018 | Multi-Strategy Retrieval | FRKC retrieval combines semantic, keyword, graph, and metadata strategies |
| AD-019 | Machine-Parseable Citation Model | All citations use structured machine-parseable format |
| AD-020 | Context Assembly with Ranking | Context assembly uses weighted ranking model (6 factors) |

---

## Part 9: Risks

| Risk ID | Description | Probability | Impact | Mitigation |
| --- | --- | --- | --- | --- |
| RISK-FRKC-001 | Knowledge OS abstraction too abstract for practical implementation | Medium | Medium | Grounded in existing FRKC patterns and FRKP reference implementation |
| RISK-FRKC-002 | Six-layer architecture over-engineers current knowledge corpus | Low | Low | Layers are logical; can merge in implementation |
| RISK-FRKC-003 | Ontology modeling effort disproportionate to current knowledge scope | Medium | Low | Progressive refinement principle; ontology starts coarse |
| RISK-FRKC-004 | Knowledge graph implementation deferred too long | Medium | Medium | File-based graph sufficient; graph database deferral explicit in DEF-FRKC-001 |
| RISK-FRKC-005 | AI retrieval and RAG corpus specification premature | Low | Low | AI retrieval defined abstractly; implementation deferred to Phase 3 |
| RISK-FRKC-006 | FRKC identity confusion with FRKP knowledge layers | Low | Low | Document explicitly states FRKC is NOT FRKP; relationship contracts defined |
| RISK-FRKC-007 | Integration contracts too abstract without reference implementations | Medium | Medium | Contracts grounded in FAEP platform specifications; integration validated through FRKP |

---

## Part 10: Lessons Learned

| Lesson | Description |
| --- | --- |
| LL-001 | The Knowledge OS framing elevates FRKC from a passive corpus to an active platform. This reframing is essential for cross-platform adoption but requires clear communication to prevent confusion with FRKP. |
| LL-002 | Six knowledge layers provide clearer separation than a flat corpus model. Each layer serves distinct consumers (humans, AI agents, computational engines, publishing platforms) with distinct requirements. |
| LL-003 | Defining ontology, knowledge graph, and evidence graph as separate concerns before implementation avoids conflating them. FRKP's existing evidence-driven publishing workflow (FRKP-FRKC-001) provides a concrete reference for the evidence graph. |
| LL-004 | Version independence of ontology and knowledge corpus is critical. Ontology restructuring (new concept types, relation types) can occur without changing knowledge content and vice versa. |
| LL-005 | The RAG corpus as a derived artifact (not separately maintained) eliminates synchronization risk. This principle should be maintained throughout implementation. |
| LL-006 | Multi-strategy retrieval with weighted ranking is more complex than single-strategy retrieval but produces significantly better AI agent context. The ranking model weights (semantic similarity 0.40, evidence strength 0.20, etc.) provide a starting point that can be empirically validated in Phase 3. |
| LL-007 | Integration contracts with all FAEP platforms must be defined before any platform consumes FRKC. The 4-point integration model (bidirectional, with version notifications and feedback) prevents tight coupling. |

---

## Part 11: Recommended Next PLAN

### Recommended PLAN-015: FRKP Governance Standards Extraction

**Description:** Begin extraction of governance standards from FRKP into FAEP Core framework. Consolidate FRKP-ID-001, FRKP-DOC-001, FRKP-BUNDLE-001, FRKP-ARCH-001, and FRKP-FRKC-001 into FAEP Core governance contracts. This advances the FAEP Program towards Phase 2 (Hybrid) of the repository evolution strategy.

**Priority:** P1 (immediate next)

### Recommended PLAN-016: IB Project Bootstrap Definition

**Description:** Bootstrap the first Business Platform on FAEP Core. With program governance established (PLAN-013) and FRKC Knowledge OS defined (PLAN-014), the first Business Platform (IB Project) can now be defined as a FAEP-conformant project. Create IB Project architecture document, define IB-specific knowledge structure, and initialize governance under the FAEP Program framework.

**Priority:** P2

### Recommended PLAN-017: FAEP Core Contract Formalization

**Description:** Progressively formalize FAEP Core Contracts with machine-readable schemas. Start with the most mature contracts (Project, Bundle, Document). This enables automated compliance verification.

**Priority:** P3

---

## Part 12: Final Verdict

**GO — FRKC Knowledge Operating System Defined.**

### Verdict Rationale

| Criterion | Result |
| --- | --- |
| FRKC defined as Knowledge Operating System (not document repository, not FRKP) | PASS |
| FRKC Philosophy defined (8 philosophies) | PASS |
| Core Responsibilities defined (15 responsibilities) | PASS |
| Knowledge Architecture defined (6 layers) | PASS |
| Knowledge Object contracts defined (11 objects) | PASS |
| Metadata Model defined (18 fields, 10 validation rules, 5 schema evolution rules) | PASS |
| Ontology Model defined (8 principles, 6 concept types, 10 relation types, lifecycle) | PASS |
| Knowledge Graph defined (6-hop relationship model) | PASS |
| Evidence Graph defined (lifecycle, relationships, versioning, integrity) | PASS |
| Semantic Retrieval model defined (AI retrieval, RAG, context assembly, ranking, citation) | PASS |
| Integration Contracts defined (5 platforms, 4 integration points each) | PASS |
| Version Strategy defined (5 version domains) | PASS |
| Future Evolution defined (5 evolution tracks) | PASS |
| Architecture Decisions documented (20 decisions) | PASS |
| Open Issues documented (10 issues) | PASS |
| Deferred Items documented (12 items) | PASS |
| Future Roadmap defined (5 phases with milestones) | PASS |
| FRKP-005 governance document created | PASS |
| PLAN-014 history document created | PASS |
| PLAN_INDEX.md updated | PASS |
| active.md updated | PASS |
| CURRENT_WORK.md updated | PASS |
| next-session.md updated | PASS |
| PROJECT_STATE.md updated | PASS |
| Modified Version 1.0.0 frozen artifacts | PASS — None modified |
| Modified Bundle-007 frozen artifacts | PASS — None modified |
| Modified existing Bundle IDs | PASS — None modified |
| Modified existing Document IDs | PASS — None modified |
| Modified navigation standards | PASS — None modified |
| Modified Markdown link standards | PASS — None modified |
| Modified repository structure | PASS — None modified |
| Modified existing Release artifacts | PASS — None modified |
| Created new projects | PASS — None created |
| Migrated repositories | PASS — None migrated |
| Implemented knowledge graph database | PASS — None implemented |
| Implemented ontology serialization | PASS — None implemented |
| Implemented RAG corpus or vector store | PASS — None implemented |
| Implemented Knowledge API | PASS — None implemented |
| Implemented AI retrieval interface | PASS — None implemented |
| Created Git commit, tag, or Release | PASS — None created |
| Resolved V1.1 release blockers | PASS — None resolved |
| Preserved existing FRKP identifiers and conventions | PASS |

### Verdict Statement

**FRKC Knowledge Operating System has been successfully defined as the canonical knowledge platform of FAEP.** PLAN-014 created one governance document (FRKP-005 — FRKC Knowledge Operating System, 19 sections, 1710+ lines) and one plan history document, and updated five planning records. FRKC is formally defined as the Knowledge OS of FAEP — not a document repository, not FRKP, but the active knowledge substrate upon which all FAEP platforms depend. The specification defines 8 philosophies, 15 core responsibilities, a 6-layer knowledge architecture, 11 knowledge object contracts, a complete metadata model, an ontology model with 8 principles, 6 concept types, and 10 relation types, knowledge graph and evidence graph models, a semantic retrieval model for AI agents with multi-strategy ranking and machine-parseable citations, integration contracts with 5 FAEP platforms, a 5-domain version strategy, and a 5-phase future roadmap with milestones. 20 architecture decisions, 10 open issues, and 12 deferred items are documented. No implementation work was performed. All existing identifiers, frozen artifacts, navigation standards, and conventions are preserved.

---

**Final Verdict: GO — FRKC Knowledge Operating System Defined.**
