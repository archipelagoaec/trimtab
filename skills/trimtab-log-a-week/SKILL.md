---
name: trimtab-log-a-week
description: Guide a complete weekly time-logging workflow in Trimtab over MCP. Use when someone logs, dictates or reviews a week of hours, or submits or approves a timesheet.
---

# Log a week

Confirm project, item or task, and date range before writing. When exactly one organization is
visible, omit `orgId` and let Trimtab resolve it. When several are visible, call
`organization.discover` and ask which organization by name; carry its discovered ID in the tool
call. Never ask the person for an organization ID. Read the target structure first and never guess
a record UUID. Use `timeEntry.create` with integer minutes and the user's facts;
choose `normal`, `extra` with `kindReason`, or `non_billable` rather than silently classifying.

Read `time_entries` after each batch using `entry_date` and returned fields such as `minutes`,
`kind`, `effective_kind`, `item_in_fee`, and `note`. Derive an open extra when
`effective_kind=extra`; absorption records are not exposed, so this is the observable signal. Do
not expect a `warnings` field from MCP. Confirm resolution with the user or by the refusal from
`timeEntry.absorb`, since an extra can be absorbed only once. Surface cap and completeness facts
only when a real read returns them. Calendar suggestions are optional evidence and require user
direction before acceptance.
Use `timeEntry.move` for filing, `timeEntry.rekind` only for an authorised change to another
person's kind, and `timesheet.submit` only when the user explicitly asks to submit.
When explaining flagged entries, say that entries need attention when the item is not in the fee.
Approval is a separate human MRTR step: `timesheet.approve` and `timesheet.approveMany` both stop
for confirmation on MCP and the CLI door. For `approveMany`, present the elicitation's selected
week count and total hours to the human; never approve on the agent's own authority.
For a single-week approval, disclose the week summary and flagged count, and bind the confirmation to that count.

For dictation, turn the user's notes into proposed entries, confirm ambiguous project, item, date,
minutes, and kind choices, then submit the same typed `timeEntry.create` calls.
