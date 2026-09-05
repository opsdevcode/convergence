# Tracing a flow

**Serves:** [Major Principle 2](../01-principles/02-design-the-engineering-system.md)
(design the engineering system, not the handoffs) and
[Major Principle 3](../01-principles/03-organization-is-an-implementation-detail.md).

**Method move:** 2. Trace. See the
[initial application method](README.md).

You cannot diagnose a delivery path you have not written down. Tracing
produces the raw material for later moves.

Start from a **real or representative instance**, not from an org chart.

## Choosing the flow

Pick one [intent](../02-capabilities/intent.md) that is recurring,
currently painful, understood well enough to describe, and attached to
someone who will own the outcome of changing it.

Do not open with the hardest flow in the organization. A first trace is
partly a way of learning to trace.

## Trace what happens, not what is documented

| Documented process | Observed flow |
| --- | --- |
| The runbook, the wiki page, the intake form | What three recent instances actually did |
| Steps someone intended | Steps including the ones people route around |
| Owners on paper | Whoever actually unblocked it |
| Stated duration | Elapsed time, including waiting |

Trace specific instances. An averaged flow hides the exceptions, and the
exceptions are usually where the expertise and the friction both live.

## What to record for each interaction

An interaction is any point where the work stops, changes hands, waits,
or requires a decision. For each one, record:

| Field | Why it matters later |
| --- | --- |
| What it decides | Distinguishes a decision from a relay |
| Who holds authority | Feeds [Major Principle 5](../01-principles/05-distribute-execution.md) |
| What expertise it applies | Distinguishes judgment from lookup |
| What evidence it produces | Some interactions exist to create a record |
| What it waits on | Separates queue time from work time |
| Why it waits (hypothesis) | Distinguishes judgment, control, tech, capacity, missing information, routing, accidental process, unknown — categories may overlap |
| Whether the answer was ever different | Repetition of an identical answer is a signal |

That last field does more work than the rest. An approval that has
returned the same answer forty times in a row is describing something
different from an approval that genuinely varies.

## The output

A **delivery trace**: an ordered list of interactions with those fields
filled in. A page of notes or a table is enough. Copy it into the
[application record](application-record.md). It is not an artifact
that needs a tool, a schema, or a review board.

The trace is evidence for a conversation, not a deliverable to be signed.

## Traps

- Stopping at the first team boundary because the rest is "their process".
- Interviewing only the consumer, which produces a story about friction
  with no view of the risk being managed.
- Interviewing only the provider, which produces a story about controls
  with no view of the cost of reaching them.
- Recording tickets but not the Slack messages, hallway questions, and
  tribal knowledge that made the tickets possible.
- Treating the trace as an indictment of the people in it. Competence is
  usually not the variable. See
  [The problem](../00-foundations/problem.md).

## Fragment

Intent: a product engineer needs relational storage for a new feature.

| # | Interaction | Decides | Authority | Waits on |
| --- | --- | --- | --- | --- |
| 1 | Ask in a team channel which team owns databases | Nothing | None | Someone answering |
| 2 | Ticket to infrastructure for an instance | Size and placement | Infrastructure | Queue |
| 3 | Ticket to networking for connectivity | Subnet and rules | Networking | Queue |
| 4 | Ticket to identity for credentials | Credential issuance | Identity | Queue |
| 5 | Security review of data class | Whether the data class is permitted | Security | Reviewer availability |
| 6 | Ticket to the database group for parameters | Engine settings | Database | Queue |

Interaction 1 decides nothing and applies no expertise. Interaction 5
decides something real. Both take days. Their similarity in cost says
nothing about their similarity in value, which is what
[evaluating interactions](evaluating-interactions.md) is for.
