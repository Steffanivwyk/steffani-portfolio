# n8n Workflow Patterns

These examples describe reusable patterns I use in CRM, marketing operations and reporting workflows. They are deliberately generic and sanitised.

## 1. Configuration-first workflow

Before a workflow calls an external system, it checks whether the required client configuration exists.

Typical checks include:

- CRM location / account identifier
- API credential availability
- advertising account identifier
- timezone
- currency
- feature enablement flags

If configuration is incomplete, the workflow should return a clear exception rather than failing deeper in the process.

## 2. Retrieve → normalise → validate → upsert

A common data pattern is:

`Retrieve source data → normalise fields → validate required values → match existing record → update or create`

This reduces duplicate records and makes downstream reporting more consistent.

## 3. Current vs previous period comparison

For recurring reporting, workflows can retrieve two defined periods and calculate changes before writing the result into the reporting layer.

Typical comparisons include:

- lead volume
- spend
- cost per lead
- appointments
- bookings
- pipeline movement
- campaign performance

The goal is to produce decision-ready information rather than simply copying raw rows.

## 4. Visible failure states

A workflow should not quietly leave old data in place when a sync fails.

Useful controls include:

- sync timestamp
- success / warning / failure status
- error message
- affected client or process key
- retry count
- missing-configuration reason

This makes system health part of the reporting layer.

## 5. Source-of-truth preservation

Automation should not create unnecessary copies of full operational databases.

A lean pattern is to keep detailed source records in their authoritative platform and move only the fields, summaries and exceptions needed elsewhere.

## 6. Human-in-the-loop controls

Not every automated action should execute without review.

I prefer approval gates for actions that can materially affect customers, campaigns, client communication or live systems.

Examples include:

- publishing campaigns
- sending sensitive client communications
- changing lifecycle or sales logic
- acting on ambiguous AI-generated output

## 7. AI-assisted build, manually validated

AI can speed up JSON generation, JavaScript snippets, mapping logic, documentation and troubleshooting. I use it as part of the build process, but workflows are manually tested against expected inputs and edge cases before being treated as reliable.

## Security note

No production credentials, access tokens, API keys, customer records or private client identifiers are included in this repository.
