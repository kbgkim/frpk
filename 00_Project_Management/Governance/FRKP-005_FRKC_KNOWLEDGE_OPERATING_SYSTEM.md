# FRKP-005 — FRKC Knowledge Operating System

---

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FRKP-005 |
| Document Name | FRKC Knowledge Operating System |
| Version | 1.0.0 |
| Status | Active |
| Plan | PLAN-014 |
| Owner | FRKC Knowledge Office |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Purpose | Define FRKC as the canonical Knowledge Operating System (Knowledge OS) of FAEP — the knowledge platform upon which all engines, platforms, and agents depend |

---

# 1. Purpose

This document defines **FRKC (Financial Risk Knowledge Corpus)** as the **Knowledge Operating System (Knowledge OS)** of the FAEP Program.

FRKC is the canonical knowledge hub used by every Platform within FAEP.

FRKC is NOT a document repository.

FRKC is NOT FRKP.

FRKC is the knowledge platform upon which all other engines depend — the single source of truth for financial risk knowledge, evidence, ontology, and semantic structure across the entire program ecosystem.

This specification defines:

- **What** FRKC is and is not.
- **What philosophy** governs knowledge in the FAEP Program.
- **What responsibilities** FRKC owns.
- **How** knowledge is architected, layered, and structured.
- **What objects** comprise the FRKC knowledge model.
- **What metadata** every knowledge artifact must carry.
- **What ontology** principles govern concept definitions.
- **How** the knowledge graph and evidence graph relate entities.
- **How** semantic retrieval, RAG, and AI context assembly operate.
- **How** FRKC integrates with every FAEP Platform.
- **How** versioning governs knowledge evolution.
- **How** FRKC will evolve through federation, distribution, and machine-readable knowledge APIs.

---

# 2. Vision

FRKC envisions a future where:

1. **Knowledge is the operating system of the platform.** Every engine, every agent, every computation, every publication operates on knowledge provided by FRKC. No platform component works without it.

2. **Knowledge is canonical.** Every concept, term, formula, and regulation exists in exactly one authoritative place. Duplication is forbidden. Derivation is always referenced.

3. **Knowledge is evidence-backed.** Every claim is traced to verifiable, certified evidence. No statement stands without its evidence chain.

4. **Knowledge is ontologically structured.** Concepts are related through a formal ontology. Semantic relationships enable reasoning, inference, and intelligent retrieval.

5. **Knowledge is AI-native.** Every artifact is designed for AI agent consumption. Consistent structure, machine-readable metadata, resolvable cross-references, and ontology-aware retrieval make FRKC the native knowledge substrate for all FAEP AI agents.

6. **Knowledge is versioned.** Every knowledge artifact has a version history. Every change is traceable. Every version is retrievable.

7. **Knowledge is navigable semantically.** Users and agents navigate knowledge through semantic relationships, not just directory trees. Concepts link to evidence, evidence links to formulas, formulas link to analytics, analytics link to publications.

8. **Knowledge outlives any single platform.** FRKC is independent of FRKP, Risk Platform, AI Platform, and Business Platforms. Platforms come and go. FRKC knowledge endures.

---

# 3. FRKC Philosophy

## 3.1 Knowledge First

Knowledge is the primary asset of the FAEP Program. Every artifact — evidence, formula, document, release, agent — exists to serve knowledge.

- Knowledge precedes publication.
- Knowledge is structured, cross-referenced, and versioned.
- Knowledge is the single source of truth for all derived artifacts.
- Knowledge is stored in FRKC — the authoritative knowledge corpus.

## 3.2 Canonical First

Every concept, term, definition, formula, and regulation exists in exactly one canonical location within FRKC.

- No duplication of canonical knowledge across platforms.
- All platforms reference FRKC for authoritative definitions.
- FRKC is the single source of truth — no exceptions.
- Derived artifacts always trace back to their FRKC source.

## 3.3 Evidence First

Every FRKC knowledge artifact must be traceable to verifiable evidence.

- Evidence precedes knowledge creation.
- No knowledge artifact is published without evidence mapping.
- Evidence is identified, registered, and certified before knowledge publication.
- Evidence-to-knowledge traceability is automated and auditable.

## 3.4 Ontology First

Knowledge is not a flat collection of documents. It is a structured ontology of concepts, relations, evidence, formulas, and semantics.

- Every concept is defined within a formal ontology.
- Semantic relations between concepts are explicit and typed.
- Ontology enables reasoning, inference, and intelligent retrieval.
- Ontology evolves as knowledge domains expand.

## 3.5 AI Native

All FRKC artifacts are AI-agent processable by design.

- Consistent document structure and metadata.
- Machine-readable cross-references and semantic annotations.
- Resolvable knowledge graph paths for agent navigation.
- Ontology-aware context assembly for RAG retrieval.
- All standards are checkable by automated validators.

## 3.6 Versioned Knowledge

All FRKC knowledge artifacts are versioned.

- Every knowledge item has a version history.
- Breaking changes to ontology or knowledge structure require major version increments.
- Version compatibility between FRKC and consuming platforms is documented.
- Version history is preserved and auditable.

## 3.7 Semantic Navigation

FRKC knowledge is navigable through semantic relationships, not just directory hierarchy.

- Concepts link to evidence.
- Evidence links to formulas.
- Formulas link to analytics.
- Analytics link to publications.
- Publications link to AI agents.
- AI agents link back to governance decisions.

## 3.8 Knowledge as an Operating System

FRKC is not a passive repository. It is the active knowledge substrate upon which all FAEP platforms operate.

- Every engine depends on FRKC for knowledge.
- Every governance decision references FRKC evidence.
- Every computation references FRKC formulas.
- Every publication references FRKC concepts.
- Every AI agent retrieves context from FRKC.
- Without FRKC, no platform operates.

---

# 4. Core Responsibilities

FRKC owns the following responsibilities across the FAEP Program.

| # | Responsibility | Domain | Description |
| --- | --- | --- | --- |
| 1 | Canonical Knowledge | Knowledge | Maintain the single authoritative source for all financial risk knowledge. Every concept, term, regulation, and formula exists in exactly one FRKC location. |
| 2 | Evidence | Evidence | Register, maintain, certify, and trace evidence sources. Ensure every knowledge artifact is backed by verifiable evidence. |
| 3 | Regulation | Regulatory Knowledge | Curate regulatory texts, interpretations, and mappings. Maintain regulatory-to-knowledge traceability. |
| 4 | Terminology | Glossary | Define, maintain, and govern all financial risk terminology. Every term has exactly one canonical definition in FRKC. |
| 5 | Ontology | Knowledge Structure | Define and maintain the formal ontology of financial risk concepts. Ontology includes concept types, relation types, and inheritance hierarchies. |
| 6 | Taxonomy | Classification | Define hierarchical classification of knowledge domains. Taxonomy enables navigation, filtering, and domain scoping. |
| 7 | Knowledge Graph | Graph Structure | Maintain the graph of knowledge objects — concepts, evidence, formulas, analytics, documents — with typed relationships. |
| 8 | Semantic Graph | Semantic Relationships | Maintain typed semantic relationships between knowledge objects. Enable semantic query, inference, and context assembly. |
| 9 | Metadata | Metadata Management | Define mandatory metadata schemas for all knowledge objects. Validate metadata compliance. Ensure machine-readability. |
| 10 | Cross References | Traceability | Maintain resolvable cross-references between all knowledge objects. Ensure link integrity across the entire corpus. |
| 11 | RAG Corpus | AI Retrieval | Curate the corpus used for Retrieval-Augmented Generation. Provide structured, chunked, annotated knowledge for AI agent context. |
| 12 | AI Retrieval | AI Access | Define and operate the retrieval interface for AI agents. Provide semantic search, context assembly, ranked retrieval, and citation generation. |
| 13 | Versioned Knowledge | Versioning | Version every knowledge artifact. Maintain version history. Govern breaking changes to knowledge structure. |
| 14 | Publication Source | Publishing | Provide the authoritative knowledge that all platforms consume for publication. FRKP and all consumer platforms draw knowledge from FRKC. |
| 15 | Execution Source | Computation | Provide the authoritative formula definitions, parameters, and symbols that computational engines execute. FRKC formulas are the contract between knowledge and computation. |

---

# 5. Knowledge Architecture

## 5.1 Knowledge Layers

FRKC knowledge is organized in six layers. Each layer serves a distinct purpose in the knowledge lifecycle.

```
┌──────────────────────────────────────────────────────────────┐
│                     AI LAYER                                   │
│  Chunks · Embeddings · Retrieval Context · Agent Annotations  │
│  Purpose: Make knowledge AI-accessible                        │
├──────────────────────────────────────────────────────────────┤
│                   EXECUTION LAYER                              │
│  Executable Formulas · Runtime Parameters · Computation Maps   │
│  Purpose: Bridge knowledge to computation                     │
├──────────────────────────────────────────────────────────────┤
│                  PUBLICATION LAYER                             │
│  Published Documents · Navigation · Indexes · Cross-References │
│  Purpose: Package knowledge for human consumption              │
├──────────────────────────────────────────────────────────────┤
│                   SEMANTIC LAYER                               │
│  Ontology · Knowledge Graph · Semantic Relations · Annotations │
│  Purpose: Structure knowledge for machine understanding        │
├──────────────────────────────────────────────────────────────┤
│                   EVIDENCE LAYER                               │
│  Evidence IDs · Registers · Mappings · Certifications         │
│  Purpose: Ground knowledge in verifiable evidence              │
├──────────────────────────────────────────────────────────────┤
│                   CANONICAL LAYER                              │
│  Concepts · Definitions · Glossary · Formulas · Regulations    │
│  Purpose: Authoritative knowledge — single source of truth     │
└──────────────────────────────────────────────────────────────┘
```

### 5.1.1 Canonical Layer

The Canonical Layer is the single source of truth. It contains:

- Authoritative concept definitions
- Canonical glossary terms
- Regulatory text and interpretations
- Formula specifications and derivations
- Mathematical foundations and symbols
- Domain knowledge across all financial risk domains

**Properties:** Immutable after certification. Versioned. Self-contained.

### 5.1.2 Evidence Layer

The Evidence Layer grounds all canonical knowledge in verifiable evidence. It contains:

- Evidence IDs and registers
- Evidence-to-knowledge mappings
- Evidence certification records
- Source document references (regulatory texts, research papers)
- Evidence lifecycle state

**Properties:** Append-only. Certified. Traceable.

### 5.1.3 Semantic Layer

The Semantic Layer provides machine-understandable structure. It contains:

- Ontology definitions (concept types, relation types)
- Knowledge graph (nodes and typed edges)
- Semantic annotations and metadata
- Inference rules and reasoning paths
- Context assembly templates for AI retrieval

**Properties:** Schema-governed. Evolvable. Queryable.

### 5.1.4 Publication Layer

The Publication Layer packages knowledge for human consumption. It contains:

- Published documents (RL, KB, AN, FC, MF, IMP, ARCH)
- Navigation structures and indexes
- Cross-reference tables and maps
- Document registers and manifests
- Publication-ready markdown artifacts

**Properties:** Derived from Canonical + Evidence layers. Stable. Navigable.

### 5.1.5 Execution Layer

The Execution Layer bridges knowledge to computation. It contains:

- Executable formula contracts
- Runtime parameter definitions
- Computation map specifications
- Symbol-to-value mappings
- Execution context documents

**Properties:** Machine-consumable. Version-pinned. Deterministic.

### 5.1.6 AI Layer

The AI Layer makes knowledge accessible to AI agents. It contains:

- Knowledge chunks optimized for RAG
- Embedding vectors and vector store
- Retrieval context assembly templates
- Agent annotation objects
- Citation and attribution metadata
- Relevance ranking configurations

**Properties:** Computed from lower layers. Optimized for retrieval. Updated on knowledge change.

---

# 6. Knowledge Objects

FRKC defines the following knowledge object contracts. Every object type has mandatory fields, lifecycle, and governance rules.

## 6.1 Knowledge Item

A discrete unit of canonical knowledge.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `knowledge_id` | String | Yes | Unique identifier (e.g., RL-170, KB-271) |
| `title` | String | Yes | Human-readable title |
| `layer` | Enum | Yes | Canonical layer (RL, KB, AN, FC, MF, IMP, ARCH) |
| `domain` | String | Yes | Risk domain (e.g., Operational Risk, Credit Risk) |
| `version` | String | Yes | Semantic version |
| `status` | Enum | Yes | Draft, Review, Approved, Frozen, Superseded, Archived |
| `evidence_ids` | List | Yes | At least one evidence source |
| `ontology_nodes` | List | Yes | One or more ontology node references |
| `glossary_terms` | List | Recommended | Terms defined or used |
| `cross_references` | List | Recommended | Links to related knowledge items |
| `created` | Date | Yes | Creation date |
| `updated` | Date | Yes | Last modification date |
| `metadata` | Object | Yes | See Metadata Model (Section 7) |

## 6.2 Evidence Item

A verifiable source that supports knowledge claims.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `evidence_id` | String | Yes | Unique evidence identifier (e.g., EVD-000340) |
| `title` | String | Yes | Description of the evidence |
| `source_type` | Enum | Yes | Regulation, Research, Internal, External |
| `source_reference` | String | Yes | Full citation or URL |
| `status` | Enum | Yes | Identified, Registered, Mapped, Certified, Superseded, Archived |
| `knowledge_ids` | List | Yes | Knowledge items this evidence supports |
| `certification` | Object | Recommended | Certification date, authority, method |
| `created` | Date | Yes | Creation date |
| `metadata` | Object | Yes | See Metadata Model |

## 6.3 Formula Knowledge

A mathematical or logical formula with full derivation context.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `formula_id` | String | Yes | Unique formula identifier |
| `knowledge_id` | String | Yes | Links to the canonical Knowledge Item |
| `symbols` | Map | Yes | Symbol definitions with types and units |
| `derivation` | String | Yes | Mathematical derivation text or reference |
| `parameters` | List | Yes | Input parameters with descriptions |
| `output` | Object | Yes | Output description, type, and units |
| `evidence_ids` | List | Yes | Evidence supporting the formula |
| `status` | Enum | Yes | Specified, Derived, Cataloged, Implemented, Validated, Frozen, Superseded |
| `version` | String | Yes | Semantic version |
| `metadata` | Object | Yes | See Metadata Model |

## 6.4 Regulation

A regulatory text or interpretation with FRKC mappings.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `regulation_id` | String | Yes | Unique regulation identifier |
| `title` | String | Yes | Full regulatory title |
| `jurisdiction` | String | Yes | Regulatory jurisdiction |
| `effective_date` | Date | Yes | Effective date |
| `knowledge_ids` | List | Yes | Canonical knowledge items derived from this regulation |
| `evidence_ids` | List | Yes | Evidence items this regulation provides |
| `status` | Enum | Yes | Active, Superseded, Proposed, Archived |
| `metadata` | Object | Yes | See Metadata Model |

## 6.5 Definition

A canonical definition of a concept or term.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `definition_id` | String | Yes | Unique definition identifier |
| `term` | String | Yes | The term being defined |
| `definition` | String | Yes | Authoritative definition text |
| `domain` | String | Yes | Risk domain |
| `knowledge_id` | String | Yes | Source knowledge item |
| `evidence_ids` | List | Yes | Supporting evidence |
| `ontology_node` | String | Yes | Ontology node reference |
| `synonyms` | List | Recommended | Alternative terms |
| `status` | Enum | Yes | Draft, Approved, Frozen, Superseded |
| `version` | String | Yes | Semantic version |

## 6.6 Glossary

A collection of term-definition pairs with cross-references.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `glossary_id` | String | Yes | Unique glossary identifier |
| `domain` | String | Yes | Risk domain this glossary covers |
| `terms` | List | Yes | List of defined terms |
| `knowledge_ids` | List | Yes | Source knowledge items |
| `version` | String | Yes | Semantic version |
| `status` | Enum | Yes | Draft, Published, Frozen, Superseded |

## 6.7 Concept

An atomic unit of meaning within the FRKC ontology.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `concept_id` | String | Yes | Unique concept identifier |
| `name` | String | Yes | Concept name |
| `description` | String | Yes | Description of the concept |
| `concept_type` | Enum | Yes | Event, Entity, Measure, Process, Relation, Rule |
| `ontology_parent` | String | Recommended | Parent concept in ontology hierarchy |
| `semantic_relations` | List | Recommended | Typed relations to other concepts |
| `knowledge_ids` | List | Yes | Knowledge items that define or use this concept |
| `status` | Enum | Yes | Draft, Active, Deprecated, Archived |
| `version` | String | Yes | Semantic version |

## 6.8 Semantic Relation

A typed relationship between two knowledge objects.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `relation_id` | String | Yes | Unique relation identifier |
| `source_id` | String | Yes | Source object ID |
| `target_id` | String | Yes | Target object ID |
| `relation_type` | Enum | Yes | is_a, part_of, defined_by, supported_by, derived_from, computed_by, published_in, referenced_by, version_of, supersedes |
| `weight` | Float | Recommended | Relationship strength for ranking (0.0-1.0) |
| `metadata` | Object | Yes | See Metadata Model |

## 6.9 Ontology Node

A node in the FRKC ontology graph.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `node_id` | String | Yes | Unique ontology node identifier |
| `name` | String | Yes | Node name |
| `node_type` | Enum | Yes | Concept, Class, Property, Relation, Domain |
| `parent_id` | String | Recommended | Parent node in ontology hierarchy |
| `children` | List | Recommended | Child node IDs |
| `properties` | Map | Recommended | Node-specific properties schema |
| `version` | String | Yes | Semantic version |
| `status` | Enum | Yes | Draft, Active, Deprecated, Archived |

## 6.10 Knowledge Collection

A named group of knowledge objects.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `collection_id` | String | Yes | Unique collection identifier |
| `name` | String | Yes | Collection name |
| `description` | String | Yes | Purpose and scope |
| `object_ids` | List | Yes | Member object IDs |
| `collection_type` | Enum | Yes | Bundle, Domain, Volume, Appendix, Analysis |
| `version` | String | Yes | Semantic version |
| `metadata` | Object | Yes | See Metadata Model |

## 6.11 Knowledge Version

A versioned snapshot of the entire FRKC knowledge state.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `version_id` | String | Yes | Unique version identifier |
| `version` | String | Yes | Semantic version of the corpus |
| `date` | Date | Yes | Version creation date |
| `object_versions` | Map | Yes | Map of object IDs to their versions in this snapshot |
| `changelog` | String | Yes | Summary of changes from previous version |
| `status` | Enum | Yes | Draft, Released, Frozen, Superseded |
| `metadata` | Object | Yes | See Metadata Model |

---

# 7. Metadata Model

Every FRKC knowledge object must carry the following mandatory metadata.

## 7.1 Mandatory Metadata Fields

| Field | Type | Description |
| --- | --- | --- |
| `id` | String | Unique identifier within the object type namespace |
| `type` | Enum | Object type (Knowledge Item, Evidence, Formula, etc.) |
| `title` | String | Human-readable title |
| `version` | String | Semantic version (MAJOR.MINOR.PATCH) |
| `status` | Enum | Current lifecycle state |
| `created_by` | String | Creator entity (human or agent) |
| `created_date` | Date | ISO 8601 date of creation |
| `updated_by` | String | Last modifier entity |
| `updated_date` | Date | ISO 8601 date of last modification |
| `owner` | String | Responsible domain or knowledge office |
| `domain` | String | Risk domain identifier |
| `layer` | Enum | Knowledge layer (Canonical, Evidence, Semantic, Publication, Execution, AI) |
| `evidence_ids` | List of String | At least one evidence source ID |
| `ontology_nodes` | List of String | Ontology node references |
| `tags` | List of String | Classification tags |
| `cross_references` | List of Object | `{ target_id, relation_type, description }` |
| `hash` | String | Content hash for integrity verification |
| `metadata_version` | String | Schema version for this metadata (currently "1.0.0") |

## 7.2 Metadata Validation Rules

| Rule | Description |
| --- | --- |
| MV-001 | All mandatory fields must be present and non-null |
| MV-002 | `id` must be unique within the object type |
| MV-003 | `version` must follow semantic versioning |
| MV-004 | `evidence_ids` must reference at least one registered evidence item |
| MV-005 | `ontology_nodes` must reference active ontology nodes |
| MV-006 | `cross_references` must target resolvable object IDs |
| MV-007 | `created_date` must precede `updated_date` |
| MV-008 | `hash` must match the content hash computed at validation time |
| MV-009 | `status` transitions must follow the defined lifecycle |
| MV-010 | `metadata_version` must match the current metadata schema |

## 7.3 Metadata Schema Evolution

| Rule | Description |
| --- | --- |
| MSE-001 | New mandatory fields may only be added in a major metadata version increment |
| MSE-002 | New optional fields may be added in any version increment |
| MSE-003 | Deprecated fields must remain in the schema for at least one major version |
| MSE-004 | Field removal is a breaking change requiring major version increment |
| MSE-005 | `metadata_version` in the object tracks which schema version it conforms to |

---

# 8. Ontology Model

## 8.1 Ontology Principles

| Principle | Description |
| --- | --- |
| Single Inheritance | Every concept has exactly one parent, forming a strict hierarchy |
| Typed Relations | All relationships between concepts are explicitly typed |
| Domain Isolation | Ontology domains are isolated; cross-domain relations are explicit |
| Versioned Ontology | The ontology itself is versioned; breaking changes require major version |
| AI-Readable | Ontology is machine-readable with resolvable identifiers |
| Minimal Commitment | The ontology defines only what is necessary; avoid over-modeling |
| Progressive Refinement | Ontology starts coarse and refines as knowledge deepens |
| Evidence Anchoring | Every ontology node is traceable to at least one evidence item |

## 8.2 Concept Types

| Type | Description | Example |
| --- | --- | --- |
| Event | An occurrence that can be observed or measured | Operational Loss Event, Market Shock |
| Entity | A thing with distinct existence | Legal Entity, Financial Instrument, Risk Factor |
| Measure | A quantifiable metric or indicator | Value at Risk, Expected Loss, Risk Weight |
| Process | A sequence of actions or operations | Risk Assessment, Capital Calculation, Reporting |
| Relation | A connection between two or more concepts | Correlation, Dependence, Causal Link |
| Rule | A constraint or requirement | Capital Requirement, Limit, Threshold |

## 8.3 Relation Types

| Type | Description | Example |
| --- | --- | --- |
| is_a | Taxonomic subsumption | Operational Loss is_a Loss Event |
| part_of | Mereological composition | Market Risk is part_of Financial Risk |
| defined_by | Definitional dependency | VaR is defined_by Confidence Level |
| supported_by | Evidential support | Capital Requirement is supported_by Basel Regulation |
| derived_from | Derivational chain | PD derived_from Historical Defaults |
| computed_by | Computational dependency | Capital computed_by Risk Weight Formula |
| measured_by | Measurement relation | Credit Risk measured_by Expected Loss |
| governed_by | Governance relation | Risk Process governed_by Policy |
| triggers | Causal relation | Loss Event triggers Reporting Obligation |
| mitigates | Control relation | Hedge mitigates Market Risk |

## 8.4 Ontology Lifecycle

```
Proposed → Draft → Review → Active → Deprecated → Archived
```

| Stage | Description |
| --- | --- |
| Proposed | Ontology change identified but not specified |
| Draft | Ontology change specified with rationale |
| Review | Ontology change reviewed by Knowledge Office |
| Active | Ontology change accepted and in effect |
| Deprecated | Ontology change superseded; consumers warned |
| Archived | Ontology change removed from active ontology |

---

# 9. Knowledge Graph

## 9.1 Relationship Model

The FRKC Knowledge Graph connects all knowledge objects through typed, bidirectional relationships. The canonical traversal path is:

```
Concept
   │
   ▼
Evidence
   │
   ▼
Formula
   │
   ▼
Risk Analytics
   │
   ▼
Runtime
   │
   ▼
Publication
   │
   ▼
AI Agent
```

### 9.1.1 Concept → Evidence

| Relation Type | Description | Cardinality |
| --- | --- | --- |
| defined_by | Concept definition is grounded in evidence | 1:N |
| supported_by | Concept is supported by evidence | M:N |
| referenced_in | Concept is referenced in evidence text | M:N |

### 9.1.2 Evidence → Formula

| Relation Type | Description | Cardinality |
| --- | --- | --- |
| supports | Evidence supports the formula derivation | 1:N |
| mandates | Regulation evidence mandates formula use | 1:N |
| defines_parameter | Evidence defines a formula parameter | 1:M |

### 9.1.3 Formula → Risk Analytics

| Relation Type | Description | Cardinality |
| --- | --- | --- |
| computed_by | Analytics are computed using the formula | 1:N |
| parameterized_by | Analytics use parameters from formula definitions | M:N |
| validated_against | Analytics validated against formula outputs | M:N |

### 9.1.4 Risk Analytics → Runtime

| Relation Type | Description | Cardinality |
| --- | --- | --- |
| executed_in | Analytics execute within a runtime context | 1:N |
| produced_by | Runtime produces analytics output | N:1 |
| depends_on | Analytics depend on runtime configuration | M:N |

### 9.1.5 Runtime → Publication

| Relation Type | Description | Cardinality |
| --- | --- | --- |
| documented_in | Runtime results are documented in publications | 1:N |
| published_as | Analytics are published in documents | N:M |
| referenced_by | Publications reference runtime specifications | M:N |

### 9.1.6 Publication → AI Agent

| Relation Type | Description | Cardinality |
| --- | --- | --- |
| consumed_by | Publications are consumed by AI agents | 1:N |
| retrieved_from | AI agents retrieve context from publications | N:M |
| cited_as | AI agents cite publications as sources | N:M |

## 9.2 Graph Query Rules

| Rule | Description |
| --- | --- |
| GQ-001 | All graph traversals follow typed edges |
| GQ-002 | Bidirectional traversal is supported (no directed-only paths) |
| GQ-003 | Path length from Concept to AI Agent must not exceed 7 hops |
| GQ-004 | Cycles are permitted for cross-reference completeness |
| GQ-005 | Graph queries must return evidence IDs for provenance |
| GQ-006 | Query results include relation type and weight for ranking |
| GQ-007 | Graph paths must include version information for each node |

## 9.3 Graph Operations

| Operation | Description | Governance |
| --- | --- | --- |
| Node Creation | Add a new knowledge object to the graph | Knowledge Review |
| Edge Creation | Add a typed relationship between two nodes | Automated validation |
| Node Update | Update node metadata or content | Knowledge Review |
| Edge Update | Update relationship type or weight | Automated validation |
| Node Deprecation | Mark node as deprecated (no deletion) | Knowledge Office |
| Graph Query | Traverse the graph with filters and weights | Open (unrestricted) |

---

# 10. Evidence Graph

## 10.1 Evidence Lifecycle

```
Identified → Registered → Mapped → Certified → Superseded → Archived
```

| Stage | Description | Gate |
| --- | --- | --- |
| Identified | Evidence source located and documented | Source quality check |
| Registered | Evidence ID assigned and metadata recorded | Metadata validation |
| Mapped | Evidence linked to one or more knowledge objects | Mapping completeness check |
| Certified | Evidence independently verified | Independent verification |
| Superseded | Evidence replaced by newer version | Supersession notice |
| Archived | Evidence removed from active register | Archive record |

## 10.2 Evidence Relationships

Evidence items relate to each other and to knowledge objects through typed relationships.

| Relation Type | Description | Example |
| --- | --- | --- |
| supports | Evidence supports a knowledge claim | Regulation text supports capital definition |
| contradicts | Evidence contradicts another evidence item | Divergent regulatory interpretations |
| supersedes | Evidence replaces prior evidence | New regulation replaces old |
| extends | Evidence extends or amends prior evidence | Amendment to regulation |
| depends_on | Evidence depends on another evidence source | Implementation standard depends on framework regulation |
| referenced_by | Evidence is referenced by another evidence item | Cross-regulatory references |

## 10.3 Evidence Versioning

| Rule | Description |
| --- | --- |
| EV-001 | Every evidence item has a unique, immutable ID |
| EV-002 | Evidence content changes produce a new version; the ID chain traces ancestry |
| EV-003 | Evidence supersession is recorded as a typed relationship, not deletion |
| EV-004 | Evidence mappings are versioned with the knowledge object, not the evidence |
| EV-005 | Evidence certification is per-version; a new version requires recertification |
| EV-006 | Evidence registers are published as snapshots at each knowledge version |

## 10.4 Evidence Integrity Rules

| Rule | Description |
| --- | --- |
| EI-001 | Every knowledge object must map to at least one certified evidence item |
| EI-002 | Evidence-to-knowledge mappings must be resolvable in both directions |
| EI-003 | Evidence certification must include a verification method and date |
| EI-004 | Uncertified evidence may be mapped but must be flagged as uncertified |
| EI-005 | Evidence supersession triggers a review of all dependent knowledge objects |
| EI-006 | Orphaned evidence (mapped to no knowledge object) is flagged for review |

---

# 11. Semantic Retrieval

## 11.1 AI Retrieval

FRKC provides a structured retrieval interface for AI agents. The retrieval model supports:

- **Semantic Search:** Retrieve knowledge objects by meaning, not just keyword match.
- **Graph Traversal:** Navigate the knowledge graph along typed edges for context expansion.
- **Evidence-Anchored Results:** Every retrieved result includes its evidence chain.
- **Version-Aware Queries:** Retrieve specific versions of knowledge objects.
- **Ontology-Expanded Queries:** Automatically expand queries using ontology relationships.

### Retrieval Interface

| Operation | Input | Output |
| --- | --- | --- |
| `search(query, filters, limit)` | Natural language query | Ranked list of knowledge objects with relevance scores |
| `retrieve(object_id, version)` | Object ID and optional version | Full knowledge object with metadata |
| `traverse(start_id, relation_types, depth)` | Start node, relation types, depth limit | Graph path from start to related nodes |
| `evidence_chain(object_id)` | Knowledge object ID | Complete evidence chain from object to evidence sources |
| `context_assembly(query, max_tokens)` | Query and context window | Assembled context block with citations |
| `ontology_query(concept, relation_types)` | Concept and relation filter | Related concepts with typed relationships |

## 11.2 RAG (Retrieval-Augmented Generation)

FRKC is the authoritative RAG corpus for all FAEP AI agents.

### Corpus Preparation

| Step | Description |
| --- | --- |
| Chunking | Knowledge documents are split into semantically coherent chunks |
| Metadata Tagging | Each chunk carries FRKC metadata (domain, layer, evidence IDs) |
| Embedding | Chunks are embedded into vector space for semantic retrieval |
| Indexing | Chunks indexed by keyword, metadata, ontology node, and embedding |
| Versioning | The RAG corpus is versioned with each FRKC knowledge version |

### Retrieval for RAG

| Component | Description |
| --- | --- |
| Query Analyzer | Analyzes the agent query for domain, concepts, and intent |
| Retriever | Multi-strategy retrieval (semantic, keyword, graph, metadata) |
| Ranker | Ranks results by relevance score, evidence strength, and freshness |
| Context Assembler | Assembles retrieved chunks into a coherent context block |
| Citation Generator | Generates inline citations linking back to FRKC evidence |
| Quality Filter | Filters results below relevance threshold |

## 11.3 Context Assembly

Context assembly produces a structured knowledge block for AI agent consumption.

### Assembly Rules

| Rule | Description |
| --- | --- |
| CA-001 | Context includes at minimum: concept definitions, evidence references, and applicable formulas |
| CA-002 | Context is scoped to the agent's declared domain |
| CA-003 | Context includes version information for all referenced objects |
| CA-004 | Context excludes deprecated or superseded knowledge |
| CA-005 | Context prioritizes certified evidence over uncertified |
| CA-006 | Context size is bounded by token limit with most relevant content first |
| CA-007 | Context includes relation graph paths for context grounding |

### Context Structure

```
{
  "query": "original agent query",
  "domain": "inferred domain",
  "knowledge_chunks": [...],
  "evidence_chain": {...},
  "ontology_context": {...},
  "formula_references": [...],
  "citations": [...],
  "retrieval_metadata": {
    "strategy": "semantic | graph | hybrid",
    "relevance_score": 0.95,
    "retrieved_version": "1.2.0",
    "total_results": 42
  }
}
```

## 11.4 Knowledge Ranking

| Factor | Weight | Description |
| --- | --- | --- |
| Semantic Similarity | 0.40 | Cosine similarity between query and chunk embedding |
| Evidence Strength | 0.20 | Number and certification status of supporting evidence |
| Ontology Relevance | 0.15 | Degree of ontology match (concept hierarchy proximity) |
| Freshness | 0.10 | Recency of knowledge version |
| Authority | 0.10 | Source authority (regulation > research > internal) |
| Graph Proximity | 0.05 | Path distance from query concept to result concept |

## 11.5 Citation Model

Every FRKC-retrieved result carries machine-readable citations.

### Citation Format

```
[FRKC:Knowledge_ID:Version:Evidence_ID:Certification_Status]
```

### Citation Rules

| Rule | Description |
| --- | --- |
| CIT-001 | Every knowledge claim includes its source FRKC ID |
| CIT-002 | Every evidence reference includes its evidence ID and certification status |
| CIT-003 | Citations are machine-parseable (structured format, not plain text) |
| CIT-004 | Citations resolve to the exact version of the referenced object |
| CIT-005 | AI agents must preserve citations when consuming FRKC knowledge |
| CIT-006 | Citation chains are preserved through transformation (e.g., summarization) |

---

# 12. Integration Contracts

FRKC integrates with every FAEP Platform through defined contracts.

## 12.1 Integration with FAEP Core

| Aspect | Contract |
| --- | --- |
| Knowledge Contract | FRKC implements CC-KNW-001 (Knowledge Contract) |
| Evidence Contract | FRKC implements CC-EVD-001 (Evidence Contract) |
| Metadata Contract | FRKC implements CC-MET-001 (Metadata Contract) |
| Version Contract | FRKC implements CC-VER-001 (Version Contract) |
| Governance | FRKC operates under FAEP Program Governance (FAEP-002) |

**Integration Points:**

| Point | Direction | Description |
| --- | --- | --- |
| IP-FRKC-001 | FAEP Core → FRKC | Core provides governance rules, contract definitions |
| IP-FRKC-002 | FRKC → FAEP Core | FRKC reports knowledge compliance, version status |

## 12.2 Integration with FRKP (Publishing Platform)

| Aspect | Contract |
| --- | --- |
| Knowledge Source | FRKP consumes canonical knowledge from FRKC for publication |
| Evidence Source | FRKP references FRKC evidence registers for publication mappings |
| Document Contract | FRKP publishes FRKC knowledge through CC-DOC-001 |
| Publishing Contract | FRKP publishes FRKC knowledge through CC-PUB-001 |

**Integration Points:**

| Point | Direction | Description |
| --- | --- | --- |
| IP-FRKP-001 | FRKC → FRKP | Canonical knowledge, evidence mappings, ontology |
| IP-FRKP-002 | FRKP → FRKC | Publication status, evidence mapping feedback, gap reports |
| IP-FRKP-003 | FRKC → FRKP | Knowledge version notifications, breaking change warnings |
| IP-FRKP-004 | FRKP → FRKC | New evidence contributions, knowledge gap requests |

## 12.3 Integration with Risk Platform

| Aspect | Contract |
| --- | --- |
| Formula Source | Risk Platform consumes FRKC formula definitions |
| Evidence Source | Risk Platform references FRKC evidence for formula validation |
| Parameter Definitions | Risk Platform consumes FRKC symbol and parameter definitions |
| Execution Context | Risk Platform returns computation results to FRKC for documentation |

**Integration Points:**

| Point | Direction | Description |
| --- | --- | --- |
| IP-RSK-001 | FRKC → Risk Platform | Formula specifications, parameter definitions, symbols |
| IP-RSK-002 | Risk Platform → FRKC | Computation results, validation data, formula execution logs |
| IP-RSK-003 | FRKC → Risk Platform | Formula version updates, deprecation warnings |
| IP-RSK-004 | Risk Platform → FRKC | New formula evidence, parameter calibration data |

## 12.4 Integration with AI Platform

| Aspect | Contract |
| --- | --- |
| RAG Corpus | AI Platform consumes FRKC as authoritative RAG corpus |
| Semantic Retrieval | AI Platform uses FRKC retrieval interface for agent context |
| Ontology | AI Platform consumes FRKC ontology for agent reasoning |
| Citation Model | AI Platform embeds FRKC citations in agent outputs |

**Integration Points:**

| Point | Direction | Description |
| --- | --- | --- |
| IP-AI-001 | FRKC → AI Platform | RAG corpus, retrieval API, ontology graph, evidence chain |
| IP-AI-002 | AI Platform → FRKC | Retrieval queries, context assembly requests, citation usage metadata |
| IP-AI-003 | FRKC → AI Platform | Knowledge version updates, corpus refresh notifications |
| IP-AI-004 | AI Platform → FRKC | Agent knowledge gap reports, retrieval quality feedback |

## 12.5 Integration with Business Platforms

| Aspect | Contract |
| --- | --- |
| Domain Knowledge | Business Platforms consume FRKC domain knowledge |
| Glossary | Business Platforms consume FRKC canonical terminology |
| Regulatory Context | Business Platforms consume FRKC regulatory mappings |
| Evidence Traceability | Business Platforms consume FRKC evidence chains for audit |

**Integration Points:**

| Point | Direction | Description |
| --- | --- | --- |
| IP-BIZ-001 | FRKC → Business Platform | Domain knowledge, glossary, regulatory mappings, evidence |
| IP-BIZ-002 | Business Platform → FRKC | Domain-specific knowledge contributions, evidence contributions |
| IP-BIZ-003 | FRKC → Business Platform | Knowledge version updates, domain ontology changes |
| IP-BIZ-004 | Business Platform → FRKC | Usage analytics, knowledge gap feedback, quality reports |

---

# 13. Version Strategy

## 13.1 Knowledge Version

The FRKC knowledge corpus is versioned using semantic versioning.

| Component | Version Increment | Trigger |
| --- | --- | --- |
| MAJOR | Breaking change to knowledge structure or ontology | Ontology restructuring; breaking semantic changes; evidence model changes |
| MINOR | Additive knowledge changes | New knowledge items; new evidence; new ontology nodes; non-breaking metadata changes |
| PATCH | Corrections and fixes | Typo fixes; metadata corrections; evidence linkage corrections; formatting |

**Rules:**

| Rule | Description |
| --- | --- |
| KV-001 | The FRKC corpus version is distinct from individual object versions |
| KV-002 | A MAJOR corpus version implies all objects may have breaking changes |
| KV-003 | A MINOR corpus version implies additive changes; existing objects remain compatible |
| KV-004 | A PATCH corpus version implies no functional changes to any object |
| KV-005 | Corpus version is recorded in the FRKC version manifest |
| KV-006 | Consuming platforms declare their FRKC version dependency |

## 13.2 Evidence Version

| Component | Version Increment | Trigger |
| --- | --- | --- |
| MAJOR | Evidence source replacement or content change | Regulation superseded; evidence retracted |
| MINOR | Evidence metadata or mapping changes | New mappings; metadata corrections; certification updates |
| PATCH | Evidence register corrections | Register formatting; citation corrections |

**Rules:**

| Rule | Description |
| --- | --- |
| EVV-001 | Evidence IDs are immutable; versioning is through evidence-ID-version pairs |
| EVV-002 | Evidence version changes trigger review of dependent knowledge objects |
| EVV-003 | Evidence certification is per-evidence-version, not per-ID |

## 13.3 Ontology Version

| Component | Version Increment | Trigger |
| --- | --- | --- |
| MAJOR | Ontology restructuring | Concept hierarchy changes; relation type changes; breaking node changes |
| MINOR | Ontology additions | New concept types; new relation types; new nodes |
| PATCH | Ontology corrections | Node metadata fixes; relation corrections; deprecation status changes |

**Rules:**

| Rule | Description |
| --- | --- |
| OV-001 | Ontology version is independent of knowledge corpus version |
| OV-002 | MAJOR ontology changes require a knowledge corpus MAJOR version |
| OV-003 | MINOR ontology changes may accompany a knowledge corpus MINOR version |
| OV-004 | Consuming platforms declare ontology version dependency separately |

## 13.4 Semantic Version

The semantic model (embeddings, retrieval configuration, ranking weights) is independently versioned.

| Component | Version Increment | Trigger |
| --- | --- | --- |
| MAJOR | Semantic model architecture change | Embedding model replacement; ranking algorithm change |
| MINOR | Semantic configuration changes | Weight adjustments; threshold changes; new index fields |
| PATCH | Semantic model corrections | Bug fixes; metadata corrections; index rebuilds |

## 13.5 Publication Version

FRKC publications (documents, reports, manifests) are versioned.

| Component | Version Increment | Trigger |
| --- | --- | --- |
| MAJOR | Publication restructuring | New publication format; breaking change to navigation |
| MINOR | Publication content additions | New sections; new tables; new cross-references |
| PATCH | Publication corrections | Typo fixes; link corrections; formatting |

---

# 14. Future Evolution

## 14.1 Knowledge Federation

FRKC will evolve from a single corpus to a federated knowledge ecosystem.

| Capability | Description | Target Phase |
| --- | --- | --- |
| Multi-Corpus Federation | Multiple FRKC instances federate into a unified knowledge graph | Phase 4 |
| Cross-Corpus Queries | Queries span federated corpuses with unified results | Phase 4 |
| Distributed Ontology | Ontology nodes distributed across federation members | Phase 4 |
| Federated Evidence | Evidence chains span multiple corpuses with cross-corpus trust | Phase 4 |

## 14.2 Distributed Knowledge

FRKC knowledge objects will be distributable across repositories and platforms.

| Capability | Description | Target Phase |
| --- | --- | --- |
| Distributed Storage | Knowledge objects stored across multiple repositories | Phase 4 |
| Replicated Nodes | High-value knowledge objects replicated for availability | Phase 4 |
| Geo-Distribution | Knowledge objects distributed across geographic regions | Phase 5 |
| Offline Capability | Knowledge corpus available for offline consumption | Phase 5 |

## 14.3 External Regulatory Sources

FRKC will integrate with external regulatory sources for automated evidence ingestion.

| Capability | Description | Target Phase |
| --- | --- | --- |
| Automated Ingestion | External regulatory texts ingested directly into FRKC | Phase 3 |
| Change Detection | External source changes detected and flagged for review | Phase 3 |
| Cross-Regulatory Mapping | Correlations between regulatory sources across jurisdictions | Phase 4 |
| Regulatory Intelligence | Automated analysis of regulatory changes and impact assessment | Phase 5 |

## 14.4 Machine-readable Knowledge

FRKC knowledge will be available through formal machine-readable formats.

| Capability | Description | Target Phase |
| --- | --- | --- |
| JSON Schema | All knowledge objects defined in JSON Schema | Phase 3 |
| Knowledge API | RESTful API for FRKC query and retrieval | Phase 3 |
| GraphQL Interface | GraphQL API for knowledge graph traversal | Phase 4 |
| Event Stream | Knowledge change events published as a stream | Phase 4 |
| gRPC Contracts | High-performance gRPC contracts for knowledge retrieval | Phase 5 |

## 14.5 Knowledge APIs

FRKC will expose formal APIs for programmatic knowledge access.

| API | Description | Target Phase |
| --- | --- | --- |
| Knowledge Query API | Structured query for knowledge objects | Phase 3 |
| Graph Traversal API | Knowledge graph traversal and path finding | Phase 3 |
| Evidence Chain API | Evidence chain resolution from any knowledge object | Phase 3 |
| Ontology Query API | Ontology query, expansion, and inference | Phase 4 |
| Context Assembly API | AI context assembly with ranking and citation | Phase 3 |
| Version API | Knowledge version query and diff | Phase 4 |
| Federation API | Cross-corpus query and federation | Phase 4 |

---

# 15. Architecture Decisions

### AD-001: FRKC as Knowledge Operating System

**Decision:** FRKC is defined as the Knowledge Operating System (Knowledge OS) of FAEP — not a document repository, not FRKP, not a passive archive. All FAEP platforms depend on FRKC for knowledge, evidence, ontology, and semantic retrieval.

**Rationale:** The Knowledge OS model ensures that knowledge is the active substrate of the platform, not a passive artifact. Every engine, agent, and computation operates on FRKC knowledge. This elevates FRKC from a corpus to a platform.

**Status:** Accepted.

### AD-002: Six-Layer Knowledge Architecture

**Decision:** FRKC knowledge is organized into six layers: Canonical, Evidence, Semantic, Publication, Execution, AI.

**Rationale:** Six layers separate concerns that would otherwise conflate: authoritative content (Canonical), verifiability (Evidence), machine understanding (Semantic), human delivery (Publication), computational integration (Execution), and AI accessibility (AI). Each layer serves distinct consumers with distinct requirements.

**Status:** Accepted.

### AD-003: Canonical First — Single Source of Truth

**Decision:** Every concept, term, definition, formula, and regulation exists in exactly one canonical location within FRKC. No duplication is permitted.

**Rationale:** Duplication creates inconsistency, versioning complexity, and trust erosion. A single canonical source ensures that every consuming platform references the same authoritative definition.

**Status:** Accepted.

### AD-004: Evidence-Anchored Knowledge

**Decision:** Every FRKC knowledge artifact must be traceable to at least one certified evidence source. Evidence precedes knowledge publication.

**Rationale:** Evidence anchoring is the foundation of platform trustworthiness. Unanchored knowledge has no provenance and cannot be verified or audited.

**Status:** Accepted.

### AD-005: Formal Ontology with Typed Relations

**Decision:** FRKC defines a formal ontology with typed relations, single inheritance, and explicit domain isolation.

**Rationale:** A formal ontology enables semantic reasoning, intelligent retrieval, and AI context assembly that flat metadata cannot provide. Typed relations give semantic meaning to graph edges, enabling inference and query expansion.

**Status:** Accepted.

### AD-006: Knowledge Graph as Primary Navigation Model

**Decision:** The FRKC knowledge graph is the primary navigation model for both human and AI consumers. Directory hierarchy is secondary.

**Rationale:** Graph navigation enables semantic path traversal (Concept → Evidence → Formula → Analytics) that directory trees cannot represent. AI agents traverse graphs naturally; humans benefit from guided semantic paths.

**Status:** Accepted.

### AD-007: Separate Evidence Graph from Knowledge Graph

**Decision:** Evidence objects are maintained in a separate evidence graph with its own lifecycle, relationships, and versioning. The knowledge graph references but does not contain evidence.

**Rationale:** Evidence has a distinct lifecycle (identification, registration, mapping, certification) that differs from knowledge lifecycle (draft, review, approve, freeze). Separating the graphs allows independent governance while maintaining cross-graph traceability.

**Status:** Accepted.

### AD-008: AI-Native Knowledge Design

**Decision:** All FRKC artifacts are designed for AI agent consumption by default. This includes consistent structure, machine-readable metadata, resolvable cross-references, and ontology-aware retrieval.

**Rationale:** AI agents are first-class platform citizens in FAEP. Designing knowledge for AI consumption ensures that agents can effectively retrieve, understand, and cite FRKC knowledge without custom parsing or human intervention.

**Status:** Accepted.

### AD-009: RAG Corpus as Derived Artifact

**Decision:** The FRKC RAG corpus is a derived artifact computed from the canonical knowledge layers, not a separately maintained corpus.

**Rationale:** Maintaining a separate RAG corpus creates synchronization risk. Deriving it from canonical knowledge ensures consistency, simplifies versioning, and eliminates drift between the authoritative knowledge and the AI-retrievable knowledge.

**Status:** Accepted.

### AD-010: Semantic Versioning for All Knowledge Objects

**Decision:** Every FRKC knowledge object, the corpus itself, and all derived artifacts use semantic versioning (MAJOR.MINOR.PATCH).

**Rationale:** Semantic versioning communicates the nature of changes to consumers. MAJOR signals breaking changes requiring consumer attention. MINOR signals additive changes. PATCH signals corrections. This enables safe dependency management across the FAEP ecosystem.

**Status:** Accepted.

### AD-011: Integration Through Contracts, Not Direct Access

**Decision:** FRKC integrates with all FAEP platforms through defined contracts and integration points. No platform directly accesses FRKC internals.

**Rationale:** Contract-based integration ensures that FRKC internals can evolve without breaking consumers. Integration points define contracts that both sides respect, enabling independent evolution.

**Status:** Accepted.

### AD-012: FRKC as Separate Repository

**Decision:** FRKC is maintained as a separate repository (github.com/kbgkim/frkp-knowledge) from FRKP and other platforms. The hybrid repository strategy applies.

**Rationale:** A separate repository ensures FRKC independence from any single platform. No platform owns the knowledge. FRKC can evolve at its own pace. Cross-repository integration is managed through version contracts.

**Status:** Accepted.

### AD-013: Evidence Chain in Retrieval Results

**Decision:** Every retrieval result from FRKC must include the complete evidence chain from knowledge object to evidence source.

**Rationale:** Evidence traceability is fundamental to platform trust. Including evidence chains in retrieval results ensures that AI agents and human consumers can always verify the provenance of FRKC knowledge.

**Status:** Accepted.

### AD-014: Knowledge Lifecycle with Freeze

**Decision:** FRKC knowledge objects follow a lifecycle that includes a Frozen state. Frozen objects are immutable.

**Rationale:** The freeze state provides a stable baseline for consuming platforms. Consuming platforms can depend on frozen knowledge without fear of unannounced changes. Freeze certification provides audit evidence of stability.

**Status:** Accepted.

### AD-015: Progressive Ontology Refinement

**Decision:** The FRKC ontology starts coarse and progressively refines as knowledge deepens. Initial ontology covers major concept types and relation types only.

**Rationale:** Over-modeling the ontology upfront creates maintenance burden and risks incorrect modeling. Progressive refinement allows the ontology to evolve organically with knowledge domain expansion while maintaining backward compatibility where possible.

**Status:** Accepted.

### AD-016: Ontology and Knowledge Version Independence

**Decision:** The FRKC ontology version is independent of the knowledge corpus version. Consuming platforms declare both dependencies separately.

**Rationale:** Ontology changes (concept restructuring) may occur independently of knowledge content changes. Separating versions enables consuming platforms to upgrade ontology and knowledge on independent schedules.

**Status:** Accepted.

### AD-017: Evidence Certification Precedes Knowledge Publication

**Decision:** Evidence must be certified before the knowledge objects it supports can be published from draft status.

**Rationale:** Uncertified evidence cannot ground trustworthy knowledge. Requiring evidence certification before knowledge publication ensures that all published FRKC knowledge is verifiably supported.

**Status:** Accepted.

### AD-018: Multi-Strategy Retrieval

**Decision:** FRKC retrieval uses a multi-strategy approach combining semantic (embedding), keyword, graph traversal, and metadata filtering.

**Rationale:** No single retrieval strategy is optimal for all queries. Semantic retrieval handles conceptual questions. Keyword retrieval handles exact term searches. Graph traversal handles relationship questions. Metadata filtering handles domain-scoped queries. Combining strategies produces better results than any single approach.

**Status:** Accepted.

### AD-019: Citation Model with Machine-Parseable Format

**Decision:** All FRKC citations use a machine-parseable structured format that includes knowledge ID, version, evidence ID, and certification status.

**Rationale:** Machine-parseable citations enable AI agents to verify sources, resolve chains, and preserve attribution through transformation. Human-readable citations are generated from the structured format.

**Status:** Accepted.

### AD-020: Context Assembly with Ranking

**Decision:** FRKC context assembly uses a weighted ranking model (semantic similarity, evidence strength, ontology relevance, freshness, authority, graph proximity) to select and order retrieved chunks.

**Rationale:** Simple retrieval without ranking produces context that may include low-relevance or low-authority content. Weighted ranking ensures that AI agents receive the most relevant, authoritative, and timely knowledge within their context window.

**Status:** Accepted.

---

# 16. Open Issues

| Issue ID | Description | Impact | Proposed Resolution | Owner |
| --- | --- | --- | --- | --- |
| OPI-FRKC-001 | Knowledge graph storage and query engine not specified | Medium | Evaluate graph database options (Neo4j, ArangoDB, or file-based) | FRKC Knowledge Office |
| OPI-FRKC-002 | Embedding model selection for semantic retrieval deferred | Medium | Evaluate embedding models (text-embedding-3, BGE, E5) for RAG quality | AI Platform |
| OPI-FRKC-003 | Machine-readable ontology serialization format not selected | Low | Choose between OWL, RDF/S, or custom JSON Schema | FRKC Knowledge Office |
| OPI-FRKC-004 | Context window size and chunk strategy not parameterized | Medium | Determine optimal chunk size and overlap for financial knowledge RAG | AI Platform |
| OPI-FRKC-005 | Cross-repository evidence chain resolution not specified | Medium | Define evidence chain protocol for multi-repo traceability | FAEP Architecture Board |
| OPI-FRKC-006 | Knowledge API authentication and authorization model | Low | Define API security model for FRKC access | FAEP Governance |
| OPI-FRKC-007 | Federation protocol for multi-corpus knowledge graph | Low | Define federation protocol and trust model | FAEP Architecture Board |
| OPI-FRKC-008 | Evidence certification standard (what constitutes sufficient verification) | Medium | Define evidence certification criteria and acceptable verification methods | Evidence Governance Board |
| OPI-FRKC-009 | Ontology inference engine not specified | Low | Determine inference capabilities (transitive closure, rule-based, ML-based) | FRKC Knowledge Office |
| OPI-FRKC-010 | FRKC performance and scale requirements not defined | Low | Determine query latency, corpus size, and concurrency requirements | FRKC Knowledge Office |

---

# 17. Deferred Items

| DEF ID | Description | Rationale | Target Phase |
| --- | --- | --- | --- |
| DEF-FRKC-001 | Knowledge graph database implementation | File-based knowledge graph sufficient for current scale | Phase 2 |
| DEF-FRKC-002 | Machine-readable ontology serialization (OWL/RDF) | Text-based ontology definitions sufficient for current use | Phase 3 |
| DEF-FRKC-003 | Automated embedding generation and vector store | Manual embedding sufficient for current RAG corpus size | Phase 3 |
| DEF-FRKC-004 | Knowledge API (REST/GraphQL) implementation | Knowledge access through repository clone sufficient | Phase 3 |
| DEF-FRKC-005 | External regulatory source automated ingestion | Manual evidence registration sufficient for current scope | Phase 3 |
| DEF-FRKC-006 | Knowledge federation protocol specification | Single corpus sufficient until multi-platform federation needed | Phase 4 |
| DEF-FRKC-007 | Cross-repository evidence chain resolution protocol | Single repository evidence chains sufficient | Phase 4 |
| DEF-FRKC-008 | FRKC performance benchmarking and scaling | Scale requirements not yet defined | Phase 4 |
| DEF-FRKC-009 | AI agent context assembly API | Manual context assembly through document retrieval sufficient | Phase 3 |
| DEF-FRKC-010 | Evidence certification automation (automated verification) | Manual certification sufficient for current evidence volume | Phase 3 |
| DEF-FRKC-011 | Knowledge change event stream | No event-driven consumers exist yet | Phase 4 |
| DEF-FRKC-012 | FRKC UI or knowledge browser | Knowledge accessed through repository and AI agents | Phase 5 |

---

# 18. Future Roadmap

## Phase 1: Knowledge OS (Current)

| Step | Description | Target |
| --- | --- | --- |
| 1.1 | Define FRKC Knowledge OS architecture (this document) | Complete |
| 1.2 | Establish FRKC Knowledge Office governance | Complete |
| 1.3 | Define knowledge object contracts | Complete |
| 1.4 | Define ontology principles and initial concept types | Complete |
| 1.5 | Define metadata model and validation rules | Complete |
| 1.6 | Define evidence graph and lifecycle | Complete |
| 1.7 | Define integration contracts with FAEP platforms | Complete |
| 1.8 | Define version strategy across all knowledge domains | Complete |

## Phase 2: Risk Integration

| Step | Description | Target |
| --- | --- | --- |
| 2.1 | Implement knowledge graph structure (file-based) | Next |
| 2.2 | Implement ontology node registry | Next |
| 2.3 | Implement semantic relation registry | Next |
| 2.4 | Implement evidence graph operational process | Next |
| 2.5 | Integrate FRKC evidence with Risk Platform formulas | Next |
| 2.6 | Establish cross-platform evidence chain for risk knowledge | Next |
| 2.7 | Validate FRKC knowledge graph with risk analytics traceability | Next |

### Phase 2 Milestones

| Milestone | Description | Exit Criteria |
| --- | --- | --- |
| M-FRKC-201 | Knowledge Graph Operational | Graph structure documented; node and edge registries active; graph query operational through document-based navigation |
| M-FRKC-202 | Risk Integration Complete | Risk Platform formulas traceable to FRKC evidence; evidence chains resolvable; formula-to-knowledge mappings validated |
| M-FRKC-203 | Ontology Active | Ontology defined for operational risk domain; concept types registered; relation types active; ontology versioning operational |

## Phase 3: AI Retrieval

| Step | Description | Target |
| --- | --- | --- |
| 3.1 | Implement RAG corpus derived from canonical knowledge | Future |
| 3.2 | Implement embedding generation and vector store | Future |
| 3.3 | Implement multi-strategy retrieval (semantic, keyword, graph) | Future |
| 3.4 | Implement context assembly with ranking | Future |
| 3.5 | Implement citation model in retrieval results | Future |
| 3.6 | Implement Knowledge API (RESTful) | Future |
| 3.7 | Integrate FRKC retrieval with AI Platform agents | Future |

### Phase 3 Milestones

| Milestone | Description | Exit Criteria |
| --- | --- | --- |
| M-FRKC-301 | RAG Corpus Operational | Canonical knowledge chunked, embedded, and indexed; RAG corpus versioned with FRKC knowledge version |
| M-FRKC-302 | Multi-Strategy Retrieval Active | Semantic, keyword, graph, and metadata retrieval operational; ranking model validated; context assembly producing structured results with citations |
| M-FRKC-303 | AI Platform Integration Complete | AI Platform agents retrieving FRKC knowledge through API; citations preserved in agent outputs; retrieval quality metrics collected |

## Phase 4: Knowledge Federation

| Step | Description | Target |
| --- | --- | --- |
| 4.1 | Define knowledge federation protocol | Future |
| 4.2 | Implement cross-corpus query | Future |
| 4.3 | Implement distributed ontology | Future |
| 4.4 | Implement federated evidence graph | Future |
| 4.5 | Implement GraphQL interface for graph queries | Future |
| 4.6 | Implement knowledge change event stream | Future |
| 4.7 | Integrate external regulatory sources | Future |

### Phase 4 Milestones

| Milestone | Description | Exit Criteria |
| --- | --- | --- |
| M-FRKC-401 | Federation Protocol Defined | Federation protocol specified; cross-corpus query semantics defined; distributed ontology model documented |
| M-FRKC-402 | External Sources Integrated | At least one external regulatory source ingested; change detection operational; cross-regulatory mappings active |
| M-FRKC-403 | Event Stream Active | Knowledge change events published; at least one consumer subscribed; event schema stable |

## Phase 5: Independent FRKC Platform

| Step | Description | Target |
| --- | --- | --- |
| 5.1 | FRKC operates as independent knowledge platform | Future |
| 5.2 | Full Knowledge API suite operational | Future |
| 5.3 | Geo-distributed knowledge replication | Future |
| 5.4 | Offline knowledge corpus capability | Future |
| 5.5 | Regulatory intelligence and automated impact assessment | Future |
| 5.6 | Plugin architecture for knowledge domain extensions | Future |

### Phase 5 Milestones

| Milestone | Description | Exit Criteria |
| --- | --- | --- |
| M-FRKC-501 | Independent Platform Operational | FRKC accessible through full API suite; independent of any single platform repository; consumed by 2+ FAEP platforms |
| M-FRKC-502 | Full API Suite Active | Knowledge Query, Graph Traversal, Evidence Chain, Ontology Query, Context Assembly, Version, and Federation APIs operational |
| M-FRKC-503 | Ecosystem Integration Complete | 2+ external knowledge sources federated; plugin architecture operational; regulatory intelligence active |

---

# 19. Appendix

## 19.1 Terminology

| Term | Definition |
| --- | --- |
| **FRKC** | Financial Risk Knowledge Corpus — the canonical Knowledge Operating System of FAEP |
| **Knowledge OS** | Knowledge Operating System — the active knowledge substrate upon which all FAEP platforms operate |
| **Canonical Knowledge** | Authoritative knowledge that exists in exactly one location; the single source of truth |
| **Knowledge Object** | A typed, versioned, metadata-carrying unit of knowledge within FRKC |
| **Ontology** | A formal, explicit specification of a shared conceptualization |
| **Knowledge Graph** | A graph structure where nodes are knowledge objects and edges are typed relationships |
| **Evidence Graph** | A graph structure where nodes are evidence items and edges are evidential relationships |
| **Semantic Retrieval** | Retrieval based on meaning and ontology, not just keyword matching |
| **RAG Corpus** | The derived, chunked, embedded knowledge corpus used for Retrieval-Augmented Generation |
| **Context Assembly** | The process of selecting, ordering, and formatting knowledge chunks into a coherent AI agent context window |
| **Citation Model** | The structured format for referencing FRKC knowledge and evidence in a machine-parseable way |

## 19.2 Abbreviations

| Abbreviation | Full Form |
| --- | --- |
| **FRKC** | Financial Risk Knowledge Corpus |
| **FAEP** | Financial AI Engineering Platform |
| **FRKP** | Financial Risk Knowledge Platform |
| **OS** | Operating System |
| **RAG** | Retrieval-Augmented Generation |
| **API** | Application Programming Interface |
| **RL** | Reference Library |
| **KB** | Knowledge Base |
| **AN** | Analysis |
| **FC** | Formula Catalog |
| **MF** | Mathematical Foundation |
| **IMP** | Implementation Guide |
| **ARCH** | Architecture Guide |
| **CC** | Core Contract |
| **KOS** | Knowledge Operating System |

---

## Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FRKC Knowledge Operating System Definition (PLAN-014) |
