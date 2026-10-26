---
name: trimtab-corrections
description: Choose the correct Trimtab correction verb by export state. Use when someone wants to fix, undo or correct something already recorded in Trimtab, such as voiding or crediting an invoice, reversing a payment, or moving or re-kinding a time entry.
---

# Correction etiquette

Read status, export state, and correction hint first. Drafts use draft update or delete. Finalized
documents use `invoice.void` or `creditNote.issue` according to intent and export state. Payments
use append-only reversal or allocation corrections. Time uses update, move, re-kind, or absorption
reversal for the corresponding fact. Never edit finalized money, un-finalize, use raw tables, or
repeat a refused verb blindly.
