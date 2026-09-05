# Tracing a flow

**Serves:** [Major Principle 2](../01-principles/02-design-the-engineering-system.md)
(design the engineering system, not the handoffs) and
[Major Principle 3](../01-principles/03-organization-is-an-implementation-detail.md).

**Method move:** 2. Trace. See the
[initial application method](README.md).

You cannot diagnose a path you have not written down. Tracing produces
the raw material for later moves.

**Trace reality, not the org chart.**

Prefer what actually happened when you can see it. A documented process
is not evidence that the process occurred.

## What a trace can rest on

A trace is an ordered sequence of interactions. The **kind of evidence**
behind it is not always the same. Name the basis honestly. These labels
are for epistemic honesty, not a maturity ladder, and they are not
equally strong.

| Basis | What it is | Strength |
| --- | --- | --- |
| **Instance** | What actually happened in a specific case you can follow (tickets, timestamps, messages, people who unblocked it) | Strongest |
| **Workflow** | A documented or repeatedly observed workflow when individual-instance detail is unavailable | Weaker than an instance; do not treat it as one |
| **Reconstruction** | Best-supported reconstruction from available evidence when a direct trace is unavailable | Weakest; **not** an observed instance |

Prefer an actual instance when available. Do not relabel a reconstruction
or a workflow as an observed instance.

When evidence is incomplete:

- Mark unknowns.
- Distinguish documented behavior from inferred behavior.
- Do not invent missing transitions.
- Do not treat an intended process as proof that it actually ran.

**Unknown is valid.** See the [application record](application-record.md).

## Recurring work

For **recurring** work, trace more than one recent instance when practical
so one unusual case is not mistaken for the normal system. That is
guidance, not a universal count. An illustrative example is two or
three recent cases — not a required sample size for every pass.

An averaged flow hides the exceptions, and the exceptions are usually
where the expertise and the friction both live.

## Singular events

Some bounded analyses are **one actual sequence**, not a recurring
delivery path. Examples: incidents, outages, migrations, exceptional
delivery events, other named events.

For a singular event, **trace that event**. Do not manufacture extra
instances. A timestamped incident timeline is valid trace evidence
**for that incident**.

One incident does **not**, by itself, establish a recurring
organizational pattern. If you later claim a pattern, you need more
than that one event.

## Trace what happens, not what is documented

| Documented process | Observed or reconstructed flow |
| --- | --- |
| The runbook, the wiki page, the intake form | What the instance, workflow, or reconstruction actually supports |
| Steps someone intended | Steps including the ones people route around — if you saw them |
| Owners on paper | Whoever actually unblocked it — if you saw them |
| Stated duration | Elapsed time, including waiting — if you have it |

A reconstruction is not an observed instance. If you only have the wiki,
say so.

Start from evidence you can point to, not from an org chart.

## Choosing the flow

Pick one [intent](../02-capabilities/intent.md) that is currently painful,
understood well enough to describe, and attached to someone who will own
the outcome of changing it — **or** pick the named singular event that is
the object of analysis.

For a first pass on recurring work, do not open with the hardest flow in
the organization. A first trace is partly a way of learning to trace.

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
| Whether the answer was ever different | Repetition of an identical answer is a signal — when you have more than one case |

That last field does more work than the rest **when you have repeating
work**. An approval that has returned the same answer many times is
describing something different from an approval that genuinely varies.
On a singular event, the field may be unknown or not applicable.

## The output

An ordered list of interactions with those fields filled in. A page of
notes or a table is enough. Copy it into the
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
  tribal knowledge that made the tickets possible — when those are in
  evidence.
- Treating a documented workflow or a reconstruction as if it were an
  observed instance.
- Inventing extra “instances” so a singular event looks like a recurring
  sample.
- Treating the trace as an indictment of the people in it. Competence is
  usually not the variable. See
  [The problem](../00-foundations/problem.md).

## Fragment

Intent: a product engineer needs relational storage for a new feature.
This fragment is **recurring work**, not a singular incident.

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
