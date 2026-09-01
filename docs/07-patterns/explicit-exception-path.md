# Explicit exception path

## Problem

Every encoded path eventually meets a case it does not fit. If the
exception route is undefined, consumers invent one: a message to someone
they know, a manual change, or a quiet decision to do it differently.

The improvised route then becomes the real process, and it is invisible.

## The pattern

Treat the exception as a first-class part of the design, with a named
authority, a stated trigger, a record, and later review.

Frequently the exception path is itself a capability.
`AssessNovelSecurityArchitecture` is not a failure of an automated
security path. It is the capability that handles what the standard path
correctly refuses.

## When it applies

- A standard path exists and covers most cases.
- The remaining cases need judgment the encoding does not hold.
- Someone has authority to say yes, and can be identified in advance.

## What it costs

| Cost | Detail |
| --- | --- |
| Specialist attention | Exceptions consume the scarce judgment the encoding was meant to free |
| Definition work | The trigger has to be stated, or everything becomes an exception |
| Honest accounting | Exception volume becomes visible, which is uncomfortable and useful |

## When not to use it

If exceptions are the majority, this pattern is a way of formalizing a
broken contract. Fix the contract boundary instead. Exception volume is
evidence about where the encoding is wrong, and a well-run exception path
should be arguing itself out of most of its work over time.

Do not use an exception path to avoid characterizing risk. "We will
handle it case by case" applied to every case is not a design.

## Signals it is working

- Exception volume is low and the reasons cluster.
- The clusters produce contract changes.
- Consumers use the exception path rather than routing around it.

## Related

[Explicit exception handling](../12-method/designing-experience-and-realization.md)
and [operating and evolving](../12-method/operating-and-evolving.md).
Urgency is a different case: see
[break-glass with evidence](break-glass-with-evidence.md).
