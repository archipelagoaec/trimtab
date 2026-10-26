---
name: trimtab-proposal-deposit
description: Guide the proposal to accepted deposit flow using Trimtab verbs. Use when someone prepares, finalizes, sends or records acceptance of a proposal, or asks about its deposit.
---

# Proposal to deposit

Read the project, company, proposal, roles, item fees, proposed hours, validity, and deposit policy
with `organization.discover` and generated `proposals.list/show` tools. Use the corresponding
`proposal.*` verbs for edits, read the returned proposal and invoice draft, and require human
direction for finalize, send, and accept. `proposal.accept` is the transition that graduates the
project and may issue a deposit according to the effective setting **and the caller's effective
`invoice.finalize` authority**. If a member lacks that authority, acceptance is still recorded and
the deposit remains a draft for an approver, with the pending disposition explained to the person.
Proposed hours become estimated hours only through acceptance. Never edit history or imitate
acceptance with an invoice write.
