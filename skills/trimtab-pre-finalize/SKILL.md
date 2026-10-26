---
name: trimtab-pre-finalize
description: Prepare a Trimtab invoice for human approval without finalizing it. Use when a draft invoice is about to be finalized or sent, or someone asks whether an invoice is ready.
---

# Pre-finalize checklist

Read the draft and preview it. Report identity snapshots, period, T&M and fixed-fee work,
billable-cost lines, separate GST/HST and PST, terms and due date, incomplete weeks, late entries,
and tax treatment. Week completeness is not readable via MCP because timesheets are not an exposed
resource. Derive an open extra from time-entry reads when `effective_kind=extra`; absorption records
are not exposed, so this is the observable signal. Confirm resolution with the user or by the
refusal from `timeEntry.absorb`, since an extra can be absorbed only once. Do not expect a
`warnings` field or invoice section labels from MCP; the `Fees`, `Sub-consultants`, and
`Disbursements` names belong to PDF rendering. Check the correction hint and QBO readiness where a
real read exposes it.

This skill never finalizes, sends, voids, approves timesheets, or claims human approval. Finalize,
send, and timesheet approval are human MRTR round trips. Preserve `isError` results and their
registry hints.
