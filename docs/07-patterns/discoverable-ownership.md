# Discoverable ownership

## Problem

Two opposite failures, often in the same organization.

In the first, ownership is the route: to get anything done you must know
which team owns the next step, so the org chart is the delivery
interface.

In the second, an abstraction hides ownership so thoroughly that when
something breaks, nobody can find out who is accountable. The consumer
was spared the org chart and then abandoned during an incident.

## The pattern

> Ownership should be discoverable without being required for routing.

Routine intent goes through the capability. Ownership, domain authority,
operational responsibility, and provenance stay published and findable
for anyone who needs them: during incidents, during design review, during
audit, and when a consumer has a case the path does not fit.

**Convergence abstracts routing, not accountability.** Abstraction should
remove information from the execution path without removing it from the
engineering system.

## When it applies

Essentially always. This is closer to a property that designs should hold
than a technique to apply selectively.

## What it costs

| Cost | Detail |
| --- | --- |
| Currency | Published ownership that is out of date is worse than none, because people act on it |
| Discipline | Ownership changes at reorganizations, and the record has to change with them |
| Temptation | Once owners are listed, consumers may go back to routing through them directly |

The third cost is worth watching. Publishing owners can quietly restore
the behavior the capability was meant to replace, particularly if the
capability path is slower than messaging a person.

## When not to use it

There is no case for hiding accountability. There is a real case for not
exposing realization detail that consumers cannot act on, which is a
different thing: that is realization opacity, not ownership opacity.

## Related

[Organizational independence](../02-capabilities/organizational-independence.md),
[Ownership and authority](../02-capabilities/ownership-and-authority.md),
and [Major Principle 3](../01-principles/03-organization-is-an-implementation-detail.md).
Organizational independence must not imply organizational opacity.
