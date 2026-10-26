---
name: trimtab-month-end
description: Run Trimtab month-end drafting from live billable work to human review. Use when someone asks to bill for the month, draft this period's invoices, or find unbilled work across projects.
---

# Month-end drafting

Month end is a live query plus drafting, not a frozen batch. Read the requested period and each
project through `organization.discover` and generated `projects.list/show`, `time_entries.list`,
`invoices.list/show`, and `billable_costs.list/show` tools. Derive unbilled work from returned
records and fields rather than expecting a billable-work or warnings response. Draft with
`invoice.draftCreate` using `projectId`, `kind`, and `include` flags for `fees`, `timeThrough`, and
`billableCosts`. Use `item.setPercentComplete` for progress and `invoice.preview` before review.
Imported entries marked “Billed before Trimtab” stay out of the next draft until an approver clears the mark with `timeEntry.setImportBilled`, which is audited with a reason.
When importing, report warnings for deleted jobs or items and voided invoices, leaving them out or importing their history as the journey specifies.

Drafting can be unattended. `invoice.finalize` and `invoice.send` require the human MRTR flow only.
Never pass a self-confirmation boolean. On refusal, read the registry hint and correct the request
without raw table writes or blind retries.
