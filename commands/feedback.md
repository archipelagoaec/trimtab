---
description: Send feedback about using Trimtab to the Trimtab team.
argument-hint: [what you want to pass on]
---

# Send feedback

The person is passing on an observation about using Trimtab. They are not reporting a wrong result
and they are not asking for a capability Trimtab does not have.

Their words, if they typed any with the command: $ARGUMENTS

If what they describe is a wrong result, say so in one sentence and offer `/trimtab:bug-report`. If
they are asking for something Trimtab cannot do yet, offer `/trimtab:feature-request`. The person
chooses. Never change the kind on your own.

## Sending it

1. If you cannot write a report a stranger could act on, ask one plain question. Do not interview
   them.
2. Show the draft first. The draft is everything that will be sent and nothing else: the kind
   (`feedback`), the body, and every key of the context object. The body is the person's own words.
   Tidy their typing if you must, never rewrite what they said into your own summary.
3. Wait. Let them accept or correct the draft. A correction replaces the draft; show it again.
4. Call the Trimtab MCP tool `feedback.submit`:
   - `orgId`: the organization they are working in. Use `organization.discover` if you do not
     already have it in this conversation.
   - `kind`: `feedback`
   - `body`: the accepted draft body
   - `context`: the object from the draft, or `{}`
5. Read the result. Tell them it is recorded as feedback in Trimtab and give them the one-line summary
   of what you captured. Say that it is queued for the Trimtab team. Do not tell them an issue was
   opened, and do not offer a time, unless the result carries a `forwarded_issue_number`; at the
   moment of submission it does not.

## When it does not go through

Say what did not happen and why, in the words the refusal gives you. Then print their text back to
them so it is not lost, and offer to try again. Never present a failed send as delivered.

A refusal that says you are not authorized for the organization means the account is not an active
member of it. A refusal that says the token is read-only means this connection cannot write; the
person needs a connection that can.
