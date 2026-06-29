# FAEP-STD-004 - Navigation and Cross-Reference Standard

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-STD-004 |
| Document Name | Navigation and Cross-Reference Standard |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-STD-000; FAEP-STD-001; FAEP-STD-003; FRKP-DOC-001; FRKP-DOC-100; FRKP-005 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-015 |

---

# 1. Purpose

This standard defines FAEP-wide navigation rules, cross-reference rules, semantic links, knowledge links, publication links, and machine-readable navigation requirements.

---

# 2. Navigation Rules

Navigation must support both human readers and AI agents.

Rules:

- Every governed document includes Document Information.
- Every document identifies related standards, specifications, or upstream artifacts when applicable.
- Platform-local navigation may use existing link blocks and breadcrumb conventions.
- Navigation must not require proprietary markdown extensions.
- Existing FRKP navigation conventions are preserved for FRKP documents.

---

# 3. Cross-Reference Rules

Cross-references must include:

| Element | Requirement |
| --- | --- |
| Target ID | Required |
| Target title or description | Recommended |
| Link path or locator | Required where repository-local |
| Version or status | Required for frozen, released, or cross-project references |
| Relationship type | Required for machine-readable maps |

Rules:

- References use stable relative links inside a repository.
- Cross-repository references include repository or authority context.
- Broken links block release readiness unless formally deferred.
- A document title may change without changing the referenced ID.

---

# 4. Semantic Links

Semantic links describe the meaning of a relationship.

Minimum relationship types:

| Type | Meaning |
| --- | --- |
| supports | Evidence or artifact supports a claim or decision |
| derives-from | Artifact is derived from another artifact |
| supersedes | Artifact replaces another artifact |
| depends-on | Artifact requires another artifact |
| implements | Reference Implementation implements a standard or contract |
| validates | Artifact validates a standard or contract |
| cites | Artifact cites source evidence |
| governs | Standard governs artifact behavior |

---

# 5. Knowledge Links

Knowledge links connect platform artifacts to canonical knowledge.

Rules:

- FAEP knowledge references identify knowledge authority, knowledge ID, version, and evidence chain where applicable.
- FRKC knowledge links are canonical for financial risk knowledge.
- Publications reference canonical knowledge rather than duplicating governance claims.
- AI retrieval outputs preserve knowledge ID, version, evidence ID, and certification status.

---

# 6. Publication Links

Publication links connect generated or published artifacts to source knowledge, evidence, and release baselines.

Rules:

- Published documents identify source knowledge or evidence mappings.
- Bundle reviews identify included publication artifacts.
- Release notes identify included bundles and frozen baselines.
- Publication artifacts are derived outputs unless explicitly designated canonical.

---

# 7. Machine-Readable Navigation

Minimum machine-readable navigation can be represented in markdown tables until formal schemas are introduced.

Required fields for navigation registers:

| Field | Required |
| --- | --- |
| Source ID | Yes |
| Target ID | Yes |
| Relationship Type | Yes |
| Target Locator | Yes |
| Target Version | Required for released/frozen/cross-project |
| Status | Yes |

Future formalization may define JSON Schema or graph serialization, but markdown registers remain valid during early FAEP phases.

---

# 8. Reference Implementation Mapping

| Source Rule | Classification | Reason |
| --- | --- | --- |
| Document Information table | FAEP Core Standard | Required for AI-readable document processing |
| FRKP breadcrumb block | FRKP-specific | Local navigation convention |
| Stable relative links | FAEP Core Standard | Required for repository-local navigation |
| FRKC knowledge graph navigation | FRKC-specific with FAEP dependency | Graph model belongs to FRKC; semantic linking is reusable |
| Machine-readable citations | FAEP Core Standard | Required by AI-native traceability |
| Publication mapping | FAEP Core Standard with FRKP reference | General traceability rule; FRKP workflow is implementation |

---

# 9. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Navigation and Cross-Reference Standard created by PLAN-015 |
