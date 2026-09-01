# Break-glass with evidence

## Problem

Sometimes action must outrun normal governance: a production incident, a
security response, a failure that is getting worse while an approval
waits.

If no legitimate fast path exists, one of two things happens. Either
people take the action anyway through borrowed credentials and undocumented
access, or they wait and the damage grows. Both outcomes are worse than a
designed path.

## The pattern

A documented path that grants elevated action under stated conditions,
with:

| Element | Purpose |
| --- | --- |
| Named authority | Someone is entitled to invoke it, known in advance |
| Stated trigger | It is clear when this is legitimate, and when it is not |
| Automatic record | The action, the actor, the reason, and the time are captured without relying on memory |
| Bounded scope | It grants what the situation needs, not standing access |
| Mandatory later review | Every use is examined afterward, including the ones that were correct |

Break-glass is [intentional friction](../00-foundations/design-doctrine.md)
inverted in time. Normal paths put judgment before action. This one puts
action first and judgment immediately after, deliberately, and only where
that trade is justified.

## When it applies

- Delay itself carries significant risk.
- The set of people who should be able to act is identifiable.
- Retrospective review is genuinely performed.

## What it costs

| Cost | Detail |
| --- | --- |
| Standing risk | The path exists, so it can be misused |
| Review discipline | Without real review it degrades into ordinary access |
| Drift toward routine | If it is convenient enough, it becomes the normal way to work |

The third cost is the one that materializes most often. A break-glass
path used weekly is not a break-glass path. It is the actual process,
with worse governance.

## When not to use it

- Delay does not actually cause harm, and the path is really about
  avoiding an approval someone finds annoying.
- The organization will not review usage, in which case this is
  unmonitored privilege with better branding.
- It would be the only path. Break-glass complements a standard path; it
  does not replace one.

## Related

[Major Principle 5](../01-principles/05-distribute-execution.md) on
privilege as distinct from authority, and
[explicit exception path](explicit-exception-path.md) for cases that need
judgment rather than speed.
