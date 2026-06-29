# FAEP-STD-003 - Evidence Standard

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-STD-003 |
| Document Name | Evidence Standard |
| Version | 1.0.0 |
| Status | Active |
| Owner | Evidence Governance Board |
| Related Documents | FAEP-STD-000; FAEP-STD-001; FAEP-STD-002; FAEP-STD-004; FRKP-FRKC-001; FRKP-005; FAEP-002 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-015 |

---

# 1. Purpose

This standard defines the FAEP-wide evidence lifecycle, metadata, traceability, integrity, versioning, and canonical evidence policy.

Evidence is authoritative source material that supports knowledge, decisions, formulas, publications, releases, and AI outputs.

---

# 2. Evidence Lifecycle

```text
Identified -> Registered -> Mapped -> Verified -> Certified -> Frozen -> Superseded -> Archived
```

| State | Meaning |
| --- | --- |
| Identified | Source located but not yet governed |
| Registered | Evidence ID assigned and metadata recorded |
| Mapped | Evidence linked to one or more governed artifacts |
| Verified | Source authenticity and relevance reviewed |
| Certified | Evidence approved for governed use |
| Frozen | Evidence baseline locked for a bundle or release |
| Superseded | Replaced by a newer or stronger evidence item |
| Archived | Retained for audit |

---

# 3. Evidence Metadata

Every evidence item must include:

| Field | Required | Description |
| --- | --- | --- |
| Evidence ID | Yes | Stable evidence identifier |
| Title | Yes | Human-readable title |
| Source Type | Yes | Regulation, research, internal, external, generated, or project artifact |
| Source Reference | Yes | Citation, path, URL, or source locator |
| Owning Authority | Yes | Evidence registry owner |
| Status | Yes | Evidence lifecycle state |
| Version | Yes | Evidence version or source version |
| Certification Status | Yes | Verification and certification state |
| Supported Artifacts | Yes | Documents, bundles, formulas, decisions, or releases supported |
| Integrity Marker | Recommended | Hash, checksum, stable citation, or immutable source marker |
| Created | Yes | Registration date |
| Last Reviewed | Required for certified evidence | Review date |

---

# 4. Evidence Traceability

Minimum traceability chain:

```text
Artifact -> Evidence Mapping -> Evidence ID -> Source Reference -> Certification Record
```

Rules:

- Every published knowledge claim must be traceable to evidence.
- Every certified evidence item must be mapped to at least one governed artifact or retained as explicitly unassigned source evidence.
- Every release and freeze baseline identifies the evidence set used for certification.
- AI-generated outputs cannot be evidence unless separately registered and verified as project artifacts.

---

# 5. Evidence Integrity

Integrity rules:

- Certified evidence records are append-only.
- Source references must be stable or include retrieval context.
- Material source changes require new evidence versioning or supersession.
- Evidence mappings must be maintained when supported artifacts change.
- Integrity failures block certification unless formally deferred by the Evidence Governance Board.

---

# 6. Evidence Versioning

| Change Type | Version Action |
| --- | --- |
| Source correction that changes meaning | New MAJOR version or supersession |
| Additional mapping without source change | MINOR version |
| Metadata correction without meaning change | PATCH version |
| Source replaced by new authority | Supersede old evidence and register replacement |

---

# 7. Canonical Evidence Policy

FRKC is the canonical knowledge and evidence platform for FAEP financial risk knowledge. Other platforms may maintain local evidence registers, but canonical evidence must be linked back to FRKC or to an FAEP-approved evidence authority.

Rules:

- Canonical evidence has one authoritative registry.
- Derived publications reference canonical evidence rather than duplicating it.
- Cross-project evidence use identifies evidence authority, ID, version, and certification status.
- Local evidence may support local decisions but must be elevated for FAEP-wide reuse.

---

# 8. Reference Implementation Mapping

| Source Rule | Classification | Reason |
| --- | --- | --- |
| Evidence precedes publication | FAEP Core Standard | Required by Core philosophy and Evidence Engine |
| Evidence-driven publishing workflow | FAEP Core Standard with FRKP/FRKC reference workflow | General rule applies program-wide; workflow actors are local |
| FRKC preserves source knowledge | FRKC-specific | Canonical corpus responsibility |
| FRKP publishes documents from evidence | FRKP-specific Reference Implementation | Publishing role is FRKP-specific |
| Evidence certification before knowledge publication | FAEP Core Standard | Required for trustworthy knowledge lifecycle |
| Evidence graph lifecycle | FRKC-specific with FAEP dependency | Graph operation belongs to FRKC, lifecycle is reusable |

---

# 9. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial FAEP Evidence Standard created by PLAN-015 |
