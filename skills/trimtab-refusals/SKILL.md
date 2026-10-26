---
name: trimtab-refusals
description: Recover safely from Trimtab MCP refusal results and registry hints. Use when a Trimtab tool returns isError true or a refusal.
---

# Refusal etiquette

Treat `isError: true` as a normal tool result. Read its text and `_meta.registryHints`, stop the
refused operation, and correct only what the schema and hint make unambiguous. Missing authority,
identity, amount, or intent requires one focused user question. When `resolveOrgId` refuses
because more than one organization is visible, call
`organization.discover` and ask which organization by its returned name (for example, “Example Studio or
the other firm?”). Never ask the person for an organization ID. After the person chooses, pass that
organization's discovered `id` as `orgId` on the retry. Never probe another org, retry a refused
money verb unchanged, forge confirmation state, or replace a refusal with success.
Refusals for unknown verbs or resources do not guess a near-match and direct the person to the registered list.
