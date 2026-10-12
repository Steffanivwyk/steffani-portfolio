# CRM Data & Attribution Framework

## The problem

Commercial teams often see different numbers in their CRM, advertising platforms and reporting tools. Without clear ownership rules, the team can spend more time debating the numbers than acting on them.

## Framework

The approach I use is to define which platform is authoritative for each metric and then use automation to reconcile, summarise and surface exceptions.

### Example source-of-truth rules

- **CRM:** leads, contact records, opportunity stages, bookings and customer outcomes
- **Advertising platforms:** spend, impressions, clicks and campaign delivery
- **Behavioural analytics:** site behaviour and interaction evidence
- **Reporting layer:** summaries, period comparisons, exceptions and management visibility

## Data-quality controls

- Standardised client and company keys
- Required configuration checks before a workflow runs
- Consistent date and timezone handling
- UTM and campaign-field mapping
- Duplicate and record-match logic
- Visible missing-data states
- Period-over-period comparisons
- Error and sync logging

## Attribution approach

Rather than treating platform-reported conversions as the final commercial truth, I compare acquisition data with downstream CRM outcomes.

This makes it easier to answer questions such as:

- Which campaigns are generating actual leads?
- Which sources are driving booked appointments or qualified opportunities?
- Where is attribution missing or inconsistent?
- Which campaigns are improving or slowing down over time?
- Is a performance issue really a media problem, or is it a CRM / tracking problem?

## RevOps value

This framework helps create a more trustworthy reporting layer for leadership while making data-quality problems visible enough to fix.

> Public version only. No client identifiers, credentials or private customer data are included.
