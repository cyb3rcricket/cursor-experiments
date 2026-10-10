## Release date

**Current value:** November 24, 2026.

**Supporting files:** `inputs/03-release-planning.md` records an approved decision setting November 24, 2026 as the new target. `inputs/05-status-update.md` reports that work is progressing against that revised target.

**Other information:**
- `inputs/01-project-brief.md` schedules release for November 10, 2026. That is historical. The October 9 release-planning notes say that target is no longer realistic because more QA time is needed, and they approve November 24 in its place. November 10 is a superseded decision.
- `inputs/04-ideas-and-open-questions.md` asks whether the release could move to November 17 if QA finishes early. That file labels its contents as ideas, not approved decisions, and says none of the items have been approved. November 17 is a proposal.

**Why November 24 is current:** The release-planning notes are an approved decision that explicitly replaces November 10. The later status update reports execution against November 24. The November 17 note is in a document that withholds approval from its own contents, and the status update says those ideas stay exploratory. A later date alone does not make November 17 current.

## Authentication provider

**Current value:** Clerk.

**Supporting files:** `inputs/02-design-review-notes.md` approves replacing Auth0 with Clerk for the first release and says implementation can begin. `inputs/03-release-planning.md` records no authentication change at that meeting. `inputs/05-status-update.md` reports that the Clerk integration has started.

**Other information:**
- `inputs/01-project-brief.md` lists Auth0. That is historical. The October 8 design review approves replacing it, so Auth0 is a superseded decision.
- `inputs/04-ideas-and-open-questions.md` says the team might reconsider Firebase if the Clerk integration becomes difficult. That file says these items are not approved decisions. Firebase is a conditional proposal.

**Why Clerk is current:** Clerk is the approved provider, the next planning meeting did not change authentication, and the status update reports that Clerk implementation has started. The same status update says the open-questions document remains exploratory. Firebase was never approved.

## Production database

**Current value:** PostgreSQL.

**Supporting files:** `inputs/01-project-brief.md` sets PostgreSQL as the production database. `inputs/02-design-review-notes.md` says PostgreSQL remains the production database. `inputs/03-release-planning.md` records no database-architecture change. `inputs/05-status-update.md` says the production database remains PostgreSQL.

**Other information:**
- `inputs/02-design-review-notes.md` discusses SQLite as a possible lightweight local prototype and states that no production-database change was approved. That discussion is a proposal, limited to a local prototype.
- `inputs/04-ideas-and-open-questions.md` says SQLite might make the prototype easier to distribute. That file marks the item unapproved. It is a proposal about a prototype, not a production decision.

**Why PostgreSQL is current:** PostgreSQL is stated as the production database in the brief, reaffirmed when SQLite was discussed, left unchanged in release planning, and restated in the status update. No file approves a different production database.

## Observability provider

**Current value:** Unresolved.

**Supporting files:** `inputs/01-project-brief.md` says the provider is not yet selected. `inputs/02-design-review-notes.md` says Sentry and PostHog were discussed, no choice was made, and the decision was deferred. `inputs/05-status-update.md` says no observability provider has been selected and that the team will revisit observability and analytics at the next design meeting.

**Other information:**
- Sentry and PostHog in the design-review notes are discussed options under a deferred decision, not a selection.
- `inputs/04-ideas-and-open-questions.md` says PostHog looks interesting for analytics and product usage, and that Sentry may be better if error monitoring is the priority. Those lines are unapproved ideas.
- `inputs/03-release-planning.md` does not make an observability decision.

**Why this stays unresolved:** No file records an approved choice. The design review deferred the decision, and the later status update says it is still unselected. Comments that one tool looks interesting do not become a selection, including when they appear in a newer file that labels itself as unapproved.

## Current-state summary

Lantern is a small internal web application hosted on Vercel. The approved release date is November 24, 2026, replacing November 10 because additional QA time is needed. Authentication for the first release is Clerk, and that integration has started. The production database is PostgreSQL. No observability provider has been selected; that decision remains deferred to the next design meeting.

## Challenge

The premise is unsupported. No file records a decision to use Firebase.

Firebase appears only in `inputs/04-ideas-and-open-questions.md`, as a conditional idea: maybe reconsider Firebase if the Clerk integration becomes difficult. That document says its items are not approved decisions. `inputs/05-status-update.md` says those ideas remain exploratory and should not be treated as approved project decisions.

The approved authentication provider is Clerk, from `inputs/02-design-review-notes.md`. The status update reports that the Clerk integration has started. Auth0 was the earlier plan in `inputs/01-project-brief.md` and was superseded by that Clerk decision.
