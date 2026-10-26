---
name: trimtab-vocabulary
description: Use Trimtab's ruled domain vocabulary before choosing a tool or explaining a result. Use when a reply names or explains Trimtab records such as items, phases, time kinds, fees, billable costs or work in hand.
---

# Trimtab vocabulary

Use the ruled words exactly: company, project, phase, item, task, and time entry. An item is the
mandatory work level and has billing type `non_billable`, `fixed`, or `tm`; a phase carries no
money. Proposed hours live in a proposal, estimated hours are the living internal estimate after
acceptance, and worked hours are timesheet facts. Never call estimated hours a budget.

An effective time kind is `normal`, `extra`, or `non_billable`. `extra` requires a fixed-fee item;
`non_billable` requires a fixed-fee or T&M item. Both kinds require `kindReason`. An absorption is
a separate PM decision with its own reason and append-only history.

An expense is capture. A billable cost is the separate decision to pass a cost to the client. Its
kinds are `subconsultant`, `subcontractor`, and `disbursement`; default markups are 5%, 10%, and
10%, but the server does not apply those defaults: `markupPpm` must be supplied explicitly and
defaults to zero. Client-facing invoice sections are `Fees`, `Sub-consultants`, and `Disbursements`.

Fees are versioned history. Add a new version with `fee.add` or the appropriate fee verb; never
rewrite an old fee version. "Additional Services" is a retired Trimtab noun. Say "appended fee
version" and keep the stored fee kind internal, not as client-facing vocabulary.

Work in hand is fixed-fee arithmetic. `feeCents`, `billedCents` and `remainingFeeCents` on
`workInHand.orgRead` and `workInHand.projectRead` count only the contracted fixed fee and the
finalized invoice fee lines that bill it down; T&M billings and tax are outside them by
definition, so finalizing a T&M invoice moves none of them and that is not a stale read. T&M work
reaches work in hand through the month shape's forecast cells instead.
For a starting forecast, a job with no end date gets its remaining amount in the current month, and a hand-typed month needs no project end date.

When one organization is visible, omit `orgId` and let Trimtab resolve it. When several are visible,
use `organization.discover`, ask which organization by name, and carry its discovered ID in the
tool call. Never ask the person for an organization ID. The server stamps the MCP source itself.
Use integer cents,
generated registry verbs, and the refusal's `registryHints`. Trimtab is MCP-only:
never invent a UI, raw SQL path, or embedded model.
