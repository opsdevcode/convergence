# Designing experience and realization

**Serves:** [Major Principle 3](../01-principles/03-organization-is-an-implementation-detail.md),
[Major Principle 5](../01-principles/05-distribute-execution.md), and the
[design doctrine](../00-foundations/design-doctrine.md).

**Method move:** 4. Intervene. Experience vs realization is an
**always-used** cut (portal vs queue). Composition and authority detail
are **conditional**. See the [initial application method](README.md) and
[Choosing an intervention](choosing-an-intervention.md).

> Remove accidental friction. Design intentional friction.

Once you know the capability and what is worth encoding, two design
decisions remain and they are frequently confused.

| Experience decisions | Realization decisions |
| --- | --- |
| How the consumer discovers this exists | Which systems and people fulfill it |
| What intent they express, and at what level | Where the work actually runs |
| What they learn about constraints before committing | Which controls execute automatically |
| How they observe the outcome | Where a human decides |
| How they reach a person when the path does not fit | Who holds authority over each part |

The capability can hold still while either column changes. Keeping them
separate is what lets a realization be replaced without renegotiating
with every consumer.

## Design the friction you decided to keep

Evaluation identified interactions with real governance or judgment
value. Those do not survive by accident; they survive by being designed
into the path.

For each one, state four things:

| State | So that |
| --- | --- |
| What it is for | It can be defended, and later challenged |
| Who holds authority | Nobody has to discover the answer |
| When it applies | Routine cases are not dragged through exceptional handling |
| What evidence it leaves | Audit is a property of the path, not a scavenger hunt |

Independent approval for a high-risk change to a regulated production
system is a designed property of the path from
[intent](../02-capabilities/intent.md) to
[outcome](../02-capabilities/output-and-outcome.md). It is not an
obstacle the design failed to remove.

## Exception and break-glass paths

Every encoded path will meet a case it does not fit. The question is
whether the exception path is designed or improvised.

| Designed exception path | Improvised workaround |
| --- | --- |
| Named authority who can say yes | Whoever answers the message first |
| Logged, with the reason recorded | Invisible after the fact |
| Reviewed later | Never revisited |
| Rare, and known to be rare | Common, and quietly the real process |

A break-glass path with explicit authority, logging, and later review is
[intentional constraint](../00-foundations/design-doctrine.md). An
undocumented shortcut that everyone uses is the accidental system
reasserting itself.

Exceptions are also the best available evidence about where the encoding
is wrong. See [operating and evolving](operating-and-evolving.md).

## Keep ownership visible without making it the route

> Ownership should be discoverable without being required for routing.

[Organizational independence](../02-capabilities/organizational-independence.md)
means the consumer does not have to navigate the org chart for routine
intent. It does not mean the org chart is hidden. Owner, domain
authority, and operational responsibility should be findable by anyone
who needs them, including during an incident.

Independence is not opacity.

## Proportional rigor

Contract rigor should match complexity, risk, reuse, and scale. A
handbook page and a required check can be a real
[contract](../02-capabilities/capability-contract.md). A regulated path
may need machine-readable policy and retained evidence.

A short honest contract beats a thorough one that lies.

## Composition guardrails

When a capability composes others, the composition is a design decision
with its own risks.

- The safety of individual capabilities does not guarantee the safety of
  their composition.
- Composition must not silently expand authority. A consumer authorized
  for the composite is not thereby authorized for everything underneath.
- Composition is valid only when the contracts, constraints, and
  authorities of the contributing capabilities can coexist.
- Reuse creates leverage and concentration risk at the same time.

See [composite capabilities](../02-capabilities/composite-capabilities.md)
and [Major Principle 5](../01-principles/05-distribute-execution.md).
