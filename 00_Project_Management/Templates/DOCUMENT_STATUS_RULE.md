# Document Status Rule

## Document Information
| Field | Value |
|---|---|
| Document ID | FRKP-DSR-001 |
| Status | Approved |
| Version | v1.0.0 |
| Last Updated | YYYY-MM-DD |
| Owner | Project Architect |

## Lifecycle States

```
Draft → Review → Approved → Frozen → Published
```

### Draft
- Document is being created or actively edited.
- Not yet ready for formal review.
- May contain incomplete sections marked with `TODO`.
- No formal approval required to edit.

### Review
- Document is complete and submitted for peer / stakeholder review.
- Changes tracked via review comments.
- May not be edited without reviewer coordination.
- Reviewers provide feedback within agreed timeline.

### Approved
- Document has passed review and received formal approval.
- Editable only with documented justification.
- Ready for publication preparation.

### Frozen
- Document is finalized and no further changes are permitted.
- Only critical errata may be addressed (via separate errata document).
- Ready for publication.

### Published
- Document has been formally released.
- Immutable; any updates require a new version cycle.
- Superseded versions moved to 99_Archive.

## Transition Rules

| From | To | Requires |
|---|---|---|
| Draft | Review | Author submits for review |
| Review | Approved | All review items resolved + approver sign-off |
| Approved | Frozen | Final formatting + completeness check |
| Frozen | Published | Publication trigger (sprint end / release) |
| Published | Draft | New version cycle initiated |
| Any | Archive | Superseded or deprecated |

## Status Metadata
Every document must include a metadata block at the top:

```markdown
---
id: FRKP-KB-0001
status: Draft
version: v0.1.0
updated: YYYY-MM-DD
owner: [Name]
---
```

## Change History
| Date | Version | Author | Change |
|---|---|---|---|
| YYYY-MM-DD | v1.0.0 | | Initial status rule |
