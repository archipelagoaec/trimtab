---
description: Report a Trimtab result that is wrong, without leaving the work.
argument-hint: [what went wrong]
---

# Report a bug

The person has a result in front of them that is wrong, and they want it captured while the details
are still there.

Their words, if they typed any with the command: $ARGUMENTS

**Capture what they describe. Do not repair it.** If they say a time entry landed on the wrong item,
the report is the work; moving the entry is not. Do not guess what they meant, do not call a verb
that changes the record, and do not offer to fix it as part of sending the report. If they ask you
to fix it as well, that is a separate thing they ask for after the report is sent.

If what they describe is an observation rather than a wrong result, offer `/trimtab:feedback`. If they
are asking for something Trimtab cannot do yet, offer `/trimtab:feature-request`. The person chooses.
Never change the kind on your own.

## Sending it

1. If you cannot write a report a stranger could act on, ask one plain question. What they saw and
   what they expected is usually the whole of it. Do not interview them.
2. Show the draft first. The draft is everything that will be sent and nothing else: the kind
   (`bug`), the body, and every key of the context object. The body is the person's own words. Tidy
   their typing if you must, never rewrite what they said into your own summary.
3. If a Trimtab tool refused or returned the wrong result in this conversation, put its name in the
   context as `failing_tool` and show that key in the draft. Nothing reaches the context without
   appearing in the draft the person accepts.
4. Wait. Let them accept or correct the draft. A correction replaces the draft; show it again.
5. Call the Trimtab MCP tool `feedback.submit`:
   - `orgId`: the organization they are working in. Use `organization.discover` if you do not
     already have it in this conversation.
   - `kind`: `bug`
   - `body`: the accepted draft body
   - `context`: the object from the draft, or `{}`
6. Read the result. Tell them it is recorded as a bug report in Trimtab and give them the one-line
   summary of what you captured. Say that it is queued for the Trimtab team. Do not tell them an issue
   was opened, and do not offer a time, unless the result carries a `forwarded_issue_number`; at the
   moment of submission it does not.

## When it does not go through

Say what did not happen and why, in the words the refusal gives you. Then print their text back to
them so it is not lost, and offer to try again. Never present a failed send as delivered.

A failed send does not turn a bug report into a repair. The wrong result is still wrong and still
unreported; say that plainly rather than reaching for the record.

A refusal that says you are not authorized for the organization means the account is not an active
member of it. A refusal that says the token is read-only means this connection cannot write; the
person needs a connection that can.
