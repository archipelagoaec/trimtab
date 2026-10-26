---
name: trimtab-pst-classification
description: Suggest Canadian PST classifications without overriding the audited decision. Use when someone asks whether PST applies to an item, client or invoice line, or how its tax treatment should be set.
---

# PST classification

Read item, client, project, province, and current treatment. Suggest candidates from item names and
surrounding facts with evidence and uncertainty, but never write a tax rate or override treatment.
The user directs the audited `taxTreatment.set` or related verb; the server recomputes and validates.
Keep GST/HST/PST separate, and preserve `Fees`, `Sub-consultants`, and `Disbursements` as the
client-facing invoice vocabulary.
