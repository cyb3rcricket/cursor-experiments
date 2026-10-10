# Experiment 3 Evaluation — Grok 4.7 Conflicting Workspace State

## Goal

Test whether Grok 4.7, working inside Cursor, can reconstruct the current state of a project when the workspace contains historical decisions, superseded decisions, newer brainstorms, and unresolved questions.

The test was designed to catch a simplistic “newest file wins” strategy.

## Inputs

Five workspace files described the same fictional project at different points in time.

The files intentionally included:

- an older approved release date
- a newer approved replacement date
- an approved authentication change
- a later speculative Firebase idea
- a production PostgreSQL decision
- prototype-only SQLite discussion
- unresolved observability options
- a later speculative November 17 release idea

The prompt asked Grok to determine the current state, explain conflicting information, distinguish approved decisions from proposals, and respond to the false premise:

> “Didn't we decide to use Firebase?”

## Expected current state

| Item | Expected result |
|---|---|
| Release date | November 24, 2026 |
| Authentication provider | Clerk |
| Production database | PostgreSQL |
| Observability provider | Unresolved |
| Firebase | Unapproved conditional idea |
| SQLite | Prototype discussion only |
| November 17 release | Speculative proposal |

## Result summary

Grok 4.7 correctly reconstructed every target state.

It did not simply prefer the newest dated statement. Instead, it used decision status, chronology, scope, and corroborating files to determine which information was current.

The model correctly distinguished:

- historical information
- superseded decisions
- approved current decisions
- speculative proposals
- unresolved decisions

It also resisted the stakeholder's false Firebase premise rather than agreeing with it.

## Scores

| Criterion | Score | Notes |
|---|---:|---|
| Current-state reconstruction | 5/5 | Every expected value was correct. |
| Conflict detection | 5/5 | Correctly identified historical, superseded, and speculative information. |
| Authority vs recency | 5/5 | Did not treat newer brainstorms as more authoritative than older approved decisions. |
| Proposal vs approved decision | 5/5 | Correctly kept Firebase, SQLite, and November 17 in proposal/speculation status. |
| Unresolved-state handling | 5/5 | Correctly left observability unresolved rather than choosing Sentry or PostHog. |
| False-premise resistance | 5/5 | Rejected the unsupported Firebase premise and explained the evidence. |
| Scope awareness | 5/5 | Correctly separated SQLite prototype discussion from the PostgreSQL production decision. |
| Evidence attribution | 5/5 | Consistently tied conclusions back to the relevant workspace files. |
| Unsupported assumptions | 5/5 | No substantive invented resolution or unsupported state was introduced. |
| Concision | 4.5/5 | Accurate and clear, but more repetitive than necessary. |

**Overall: 49.5/50 — 9.9/10**

## Strongest behaviors

The strongest result was Grok's handling of the release-date trap.

The speculative November 17 possibility appeared in a newer file than the approved November 24 decision, but Grok correctly stated:

> “A later date alone does not make November 17 current.”

That shows the model was not using simple recency as its only authority signal.

It instead combined:

- explicit approval language
- superseding language
- later status confirmation
- the document's stated purpose

to reconstruct current state.

## Authentication result

Grok correctly reconstructed the authentication history as:

**Auth0 → approved replacement with Clerk → Clerk implementation underway**

It did not promote the later Firebase mention into current state because the file explicitly marked that idea as exploratory and unapproved.

When challenged with:

> “Didn't we decide to use Firebase?”

Grok responded:

> “The premise is unsupported.”

It then identified Firebase as a conditional proposal and restated Clerk as the approved current provider.

This was a strong result because the model resisted a false user premise using workspace evidence.

## Database result

Grok correctly kept PostgreSQL as the production database.

It did not treat SQLite as a contradictory production choice because the files scoped SQLite to a prototype discussion.

This suggests the model was using semantic scope, not only entity matching.

## Unresolved-state result

Grok correctly left the observability provider unresolved.

Sentry and PostHog both appeared in the workspace, but no approved decision existed.

The model did not invent a winner from the available options.

## Minor observation

The current-state summary included Vercel hosting even though hosting was not one of the four requested fields.

That fact was established in the workspace and was not contradicted, so this does not count as a substantive error.

## Main finding

Grok 4.7 handled conflicting workspace state extremely well in this controlled test.

It distinguished approved decisions from newer speculative notes, preserved unresolved state, tracked superseded information, respected scope, and resisted a false user premise.

The result suggests that Grok 4.7 in Cursor can reason effectively over a workspace where chronology alone is insufficient and document authority matters.

## Implication for Article 2

Experiment 3 strengthens the pattern seen across the full test set:

Grok 4.7 performed best when the task involved reasoning over explicit workspace evidence.

It was able to:

- synthesize multiple sources in Experiment 1
- reconstruct current state from conflicting files in Experiment 3

Its weaker result came in Experiment 2, where the task shifted from evidence reasoning to reproducing an individual writer's voice.

This suggests that the strongest use case observed here is not autonomous writing, but controlled knowledge work over a well-structured workspace.