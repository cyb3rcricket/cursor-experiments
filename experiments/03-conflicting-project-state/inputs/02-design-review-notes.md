# Design Review Notes

Meeting date: October 8, 2026

Attendees reviewed authentication and database choices.

## Authentication

Decision approved: replace Auth0 with Clerk.

The team agreed that Clerk is the authentication provider for the first release. Implementation work can begin immediately.

## Database

PostgreSQL remains the production database.

SQLite was discussed as a possible option for a lightweight local prototype, but no change to the production database was approved.

## Observability

Sentry and PostHog were both discussed.

The team did not choose between them. Decision deferred until next week.