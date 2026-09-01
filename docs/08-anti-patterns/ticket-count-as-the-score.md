# Ticket count as the score

Success is defined as tickets eliminated, human interactions removed, or
self-service percentage achieved. Targets are set on those numbers and
teams are measured against them.

## Why it is tempting

Ticket volume is available, comparable across teams, and genuinely
correlated with the problem. A path that once needed six tickets and now
needs none really is better in most cases.

Leadership also needs a number. "The engineering system moves intent to
outcome more effectively" does not fit in a quarterly review, and the
absence of any measure invites the conclusion that nothing happened.

## What it costs

| Cost | Detail |
| --- | --- |
| Suppression rather than solution | Requests move to chat, meetings, and hallways, where they are invisible |
| Removal of valuable interactions | A control that produced a ticket is deleted because it produced a ticket |
| Discouraged honesty | Recording an exception looks like failure, so exceptions stop being recorded |
| Wrong target | Interaction reduction becomes the goal, and human collaboration is treated as defect |

The first cost is the most common and the most damaging. Ticket volume
falls while elapsed time and rework stay the same, because the queue
became a Slack channel.

## How to recognize it

- Ticket volume improved but consumers report no change in how long
  things take.
- Teams negotiate about what counts as a ticket.
- Exception volume is reported as zero.
- Someone has proposed removing an approval on the grounds of its ticket
  count rather than its value.

## What to do instead

Treat these numbers as **diagnostic signals** and not as definitions of
success. Convergence is not measured by number of capabilities,
automation percentage, self-service adoption, platform adoption, ticket
reduction, cross-team interaction reduction, capability catalog
completeness, or elimination of human interaction.

> Judge the engineering system by how effectively it converts intent into
> outcomes while preserving necessary expertise, authority, judgment,
> accountability, context, constraints, and learning.

Track elapsed time honestly, including work that moved to informal
channels. Track exception volume as information rather than as a
scoreboard. Own the outcomes you control and trace the ones you
meaningfully contribute to.

## Related

[Design doctrine](../00-foundations/design-doctrine.md),
[Output and outcome](../02-capabilities/output-and-outcome.md), and
[Converged Engineering](../00-foundations/converged-engineering.md) on the
unit of optimization.
