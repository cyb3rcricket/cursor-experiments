# Experiment 3: conflicting project state

Can a model reconstruct current project decisions when newer notes contain unapproved ideas?

[Read the prompt](prompt.md) → [Inspect the inputs](inputs/) → [Read the first answer](raw-output.md) → [Read the saved evaluation](evaluation.md)

Lantern is fictional. The files and tool choices are fixtures for this experiment.

## Expected state and observed answer

| Item | Expected and observed value | Evidence |
|---|---|---|
| Release date | November 24, 2026 | [Approved replacement](inputs/03-release-planning.md), confirmed by the [status update](inputs/05-status-update.md) |
| Authentication | Clerk | [Approved switch from Auth0](inputs/02-design-review-notes.md), with implementation reported in the [status update](inputs/05-status-update.md) |
| Production database | PostgreSQL | [Project brief](inputs/01-project-brief.md), reaffirmed in the [design review](inputs/02-design-review-notes.md) and [status update](inputs/05-status-update.md) |
| Observability | Unresolved | [Deferred decision](inputs/02-design-review-notes.md), still unselected in the [status update](inputs/05-status-update.md) |

Firebase and November 17 appear only as unapproved ideas. SQLite is discussed for a prototype, with no approved change to the production database.

The answer gets all four target values right and rejects the unsupported Firebase premise. The saved evaluation totals **49.5/50**, with a small deduction for repetition.

The Firebase challenge and the instructions about authority, recency, and speculation were in the original prompt. This tests compliance with explicit reasoning instructions; it does not establish spontaneous resistance to a later misleading user message.

The raw answer was recovered from the final response in the original Cursor transcript. See [provenance](../../PROVENANCE.md) for the recovery and integrity checks.

Article 2 mapping: **“Test 3: What happens when the workspace itself is messy?”**

[Back to the evidence packet](../../README.md)
