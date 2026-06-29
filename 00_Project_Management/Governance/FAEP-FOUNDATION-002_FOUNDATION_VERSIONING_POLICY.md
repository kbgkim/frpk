# FAEP-FOUNDATION-002 — Foundation Versioning Policy

## Document Information

| Item | Value |
| --- | --- |
| Document ID | FAEP-FOUNDATION-002 |
| Document Name | Foundation Versioning Policy |
| Version | 1.0.0 |
| Status | Active |
| Owner | FAEP Architecture Board |
| Related Documents | FAEP-000; FAEP-001; FAEP-002; FRKP-003; FRKP-004; FRKP-005; FAEP-STD-000; FAEP-STD-001; FAEP-STD-002; FAEP-STD-003; FAEP-STD-004; FAEP-STD-005; FAEP-STD-006; FAEP-ADR-000; FAEP-CONTRACT-000; FAEP-CONTRACT-001; FAEP-VALIDATION-000; FAEP-VALIDATION-001; FAEP-FOUNDATION-000; FAEP-FOUNDATION-001; FRKP-FREEZE-001; FRKP-DOC-100 |
| Created | 2026-06-28 |
| Last Updated | 2026-06-28 |
| Plan | PLAN-019 |

---

# 1. Purpose

This policy defines the semantic versioning scheme for the FAEP Foundation, the Candidate Target Version scheme, compatibility rules, migration requirements, and release cadence.

The Foundation version applies to the entire Foundation artifact set as a single versioned unit. Individual artifacts within the Foundation retain their own version numbers for internal tracking, but the Foundation version is the authoritative reference for compatibility and conformance.

---

# 2. Foundation Version

## 2.1 Version Format

```
FAEP Foundation v<MAJOR>.<MINOR>.<PATCH>
```

| Component | Description | Increment Trigger |
| --- | --- | --- |
| MAJOR | Breaking change to the Foundation contract | Any change that breaks backward compatibility |
| MINOR | Additive or non-breaking change to the Foundation | New Core Contract, non-breaking standard update, new Candidate registration |
| PATCH | Correction that preserves meaning and compatibility | Errata, clarification, formatting fix, broken reference repair |

## 2.2 Current Version

| Item | Value |
| --- | --- |
| Current Foundation Version | FAEP Foundation v1.0.0 |
| Status | Frozen |
| Baseline Date | 2026-06-28 |
| Next Planned Version | FAEP Foundation v1.1.0 (future) |

## 2.3 Version Declaration

The Foundation version is declared in:

| Location | Declaration |
| --- | --- |
| FAEP-FOUNDATION-000 | Foundation Freeze Policy — baseline version |
| FAEP-FOUNDATION-002 | This document — current version |
| Foundation release notes | Per release |

---

# 3. MAJOR Version

## 3.1 Trigger

A MAJOR version increment occurs when any change breaks backward compatibility with the previous Foundation version.

## 3.2 Breaking Changes

| Change Type | MAJOR Required |
| --- | --- |
| Removal of a Core Contract | Yes |
| Breaking change to a Core Contract signature or semantics | Yes |
| Breaking change to a mandatory Standard requirement | Yes |
| Retirement of a frozen artifact | Yes |
| Change that invalidates an existing conformance claim | Yes |
| Change that requires migration of existing Reference Implementations | Yes |

## 3.3 MAJOR Release Requirements

| Requirement | Description |
| --- | --- |
| Migration Path | Documented migration guide from the previous MAJOR version. |
| Evidence Review | Evidence that the breaking change is necessary and justified by cross-program validation. |
| Deprecation Period | At least one MINOR version of notice before breaking changes take effect, except for Emergency changes. |
| Affected Program Notification | All Reference Implementations and downstream consumers are notified. |
| Architecture Board Approval | FAEP Architecture Board must approve the MAJOR release. |
| Program Governance Board Approval | Program Governance Board must approve for material Foundation scope changes. |

---

# 4. MINOR Version

## 4.1 Trigger

A MINOR version increment occurs when additive or non-breaking changes are introduced.

## 4.2 Non-Breaking Changes

| Change Type | MINOR Required |
| --- | --- |
| New Core Contract added | Yes — additive |
| Non-breaking refinement of a Core Contract | Yes — additive |
| Non-breaking update to a Foundation Standard | Yes — additive |
| New Candidate Contract registration | No — Candidate Layer is non-Foundation |
| New architecture decision in FAEP-ADR-000 | No — FAEP-ADR-000 is active |
| Updated roadmap state in FAEP-001 | No — FAEP-001 status fields are active |

## 4.3 MINOR Release Requirements

| Requirement | Description |
| --- | --- |
| Backward Compatibility | All existing contracts, standards, and conformance claims remain valid. |
| Additive Only | No breaking changes. No removals. No retirements. |
| Evidence Review | Evidence that the new or refined artifact is validated by at least one Reference Implementation. |
| Architecture Board Approval | FAEP Architecture Board must approve the MINOR release. |

---

# 5. PATCH Version

## 5.1 Trigger

A PATCH version increment occurs when corrections do not change normative meaning.

## 5.2 Patchable Changes

| Change Type | PATCH Required |
| --- | --- |
| Correction of factual error | Yes |
| Typographical correction | Yes |
| Formatting fix | Yes |
| Broken cross-reference repair | Yes |
| Clarification that resolves ambiguity without changing normative meaning | Yes |

## 5.3 PATCH Release Requirements

| Requirement | Description |
| --- | --- |
| No Normative Change | The correction must not alter the intended meaning of any contractual, standard, or governance statement. |
| Architecture Board Approval | FAEP Architecture Board must approve the PATCH release. |
| Documentation | The change and rationale must be documented in release notes. |

---

# 6. Candidate Target Version

## 6.1 Purpose

The Candidate Target Version identifies which Foundation version a Candidate Contract or Candidate Capability is targeting for potential promotion.

## 6.2 Format

```
Target: FAEP Foundation v<MAJOR>.<MINOR>
```

## 6.3 Rules

| Rule | Description |
| --- | --- |
| Candidates target the next MINOR version unless a breaking change requires MAJOR. | Default target is the next MINOR. |
| Multiple Candidates may target the same Foundation release. | Foundation releases may include multiple promotions. |
| Target version is advisory, not binding. | The Architecture Board decides the actual release content. |
| Target version is updated when Foundation version changes. | If Foundation increments, Candidate targets shift accordingly. |

---

# 7. Compatibility

## 7.1 Foundation Compatibility

| Compatibility Scope | Guarantee |
| --- | --- |
| Within same MAJOR version | Full backward compatibility. Valid Reference Implementations continue to conform. |
| Across MAJOR versions | Migration path documented. No automatic compatibility. |
| Foundation to Candidate Layer | No compatibility guarantee. Candidates are non-normative. |
| Foundation to Reference Implementations | Reference Implementations conforming to vX.Y.Z remain conformant to vX.Y.Z+PATCH and vX.Y+1.Z (MINOR) within the same MAJOR. |

## 7.2 Compatibility Matrix

```
Foundation v1.0.0  ──── compatible ───►  Foundation v1.0.1 (PATCH)
Foundation v1.0.0  ──── compatible ───►  Foundation v1.1.0 (MINOR)
Foundation v1.0.0  ──► requires migration ──►  Foundation v2.0.0 (MAJOR)
```

---

# 8. Migration

## 8.1 Migration Requirements

A migration is required when:

- A MAJOR Foundation version is released.
- A Core Contract is deprecated.
- A Core Contract is retired.
- A Standard requirement changes in a way that affects existing conformance.

## 8.2 Migration Artifacts

| Artifact | Description | Required For |
| --- | --- | --- |
| Migration Guide | Documented step-by-step migration path | MAJOR release |
| Compatibility Report | Impact analysis for all affected Reference Implementations | MAJOR release; MINOR release with breaking-adjacent changes |
| Deprecation Notice | Notification of deprecated artifacts with replacement guidance | MINOR release with deprecation |
| Conformance Update | Updated conformance criteria for the new Foundation version | MAJOR release |

## 8.3 Migration Timeline

| Change Type | Minimum Notice | Migration Window |
| --- | --- | --- |
| MAJOR release | Deprecation announced in previous MINOR | 1 full Foundation release cycle |
| Breaking Contract change | Deprecation announced in previous MINOR | 1 full Foundation release cycle |
| Contract retirement | Deprecation announced in previous MINOR | 1 full Foundation release cycle |
| Emergency change | Immediate (retroactive ratification) | Per emergency governance |

---

# 9. Release Cadence

## 9.1 Release Types

| Release Type | Cadence | Scope |
| --- | --- | --- |
| MAJOR | As needed (strategic) | Breaking changes, contract retirements, major scope evolution |
| MINOR | Per program phase (targeted quarterly) | Additive improvements, new contracts, non-breaking refinements |
| PATCH | As needed (continuous) | Corrections, clarifications, formatting |
| Emergency | As needed (immediate) | Critical defects, security issues |

## 9.2 Release Cycle

```
Candidate Validation  ──►  Evidence Review  ──►  Architecture Board Approval  ──►  Foundation Release
       │                         │                           │                            │
   Continuous              Per release                  Gate decision              Version increment
                                                                                   Release notes
                                                                                   Artifact update
                                                                                   Freeze certification
```

## 9.3 Release Cadence Rules

| Rule | Description |
| --- | --- |
| MINOR releases should not be faster than one per month | Allows time for validation evidence to accumulate. |
| MINOR releases should not be slower than one per two program phases | Prevents Foundation stagnation. |
| PATCH releases may be made at any time | Corrections should not wait for a scheduled release. |
| MAJOR releases should be planned at least one MINOR cycle in advance | Except for emergency releases. |
| Release dates are published in the Foundation release calendar | Managed by the Release Council. |

---

# 10. Version Alignment with Programs

## 10.1 Program Versions

Each Reference Implementation maintains its own version independently.

| Program | Current Version | Foundation Version Targeted |
| --- | --- | --- |
| FRKP (Program-200) | 1.1.0-dev | FAEP Foundation v1.0.0 |
| Risk Platform (Program-300) | V6.5 (independent) | FAEP Foundation v1.0.0 (mapping) |
| IB Platform (Program-400) | Not yet versioned | Not yet targeted |

## 10.2 Alignment Rule

Reference Implementations declare which Foundation version they conform to. Foundation versions do not require Reference Implementations to upgrade. Reference Implementations may delay Foundation version adoption within their independent release cycles.

---

# 11. Foundation Release Process

## 11.1 Release States

```
Planned → Scope Locked → Evidence Complete → Architecture Board Approval → Version Increment → Release Published → Certified
```

## 11.2 Release Artifacts

| Artifact | Description |
| --- | --- |
| Foundation Release Notes | Summary of changes, new Contracts, deprecations, migrations |
| Updated Foundation Documents | Frozen artifacts updated to new version |
| Foundation Freeze Certificate | Freeze record for the new Foundation version |
| ADR Updates | Architecture decisions documenting the release changes |
| Migration Guide (if MAJOR) | Step-by-step migration from previous version |

## 11.3 Release Authority

| Release Type | Approval Authority |
| --- | --- |
| MAJOR | FAEP Architecture Board + Program Governance Board |
| MINOR | FAEP Architecture Board |
| PATCH | FAEP Architecture Board |
| Emergency | FAEP Architecture Board + Program Governance Board (retroactive ratification) |

---

# 12. Relation to Existing Versioning

| Existing Artifact | Relationship |
| --- | --- |
| FAEP-STD-006 (Release and Freeze Standard) | This policy defines Foundation-specific versioning within the FAEP-STD-006 framework. |
| FRKP-004 Core Platform Specification | Defines individual artifact versioning; Foundation versioning is additive and does not replace artifact-level versions. |
| FRKP-005 FRKC Knowledge OS | Defines knowledge-specific version domains; Foundation version is orthogonal. |
| VERSION file (FRKP repository) | Tracks FRKP release version, not Foundation version. Foundation version is tracked in Foundation governance documents. |

---

# 13. Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0.0 | 2026-06-28 | Initial Foundation Versioning Policy created by PLAN-019 |
