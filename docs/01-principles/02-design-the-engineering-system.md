# Design the engineering system, not the handoffs.

**Major Principle 2 of Convergence** (working doctrine, v0.1)

Optimize the path from [intent](../02-capabilities/intent.md) to
[outcome](../02-capabilities/output-and-outcome.md). Do not optimize the
local efficiency of a queue, a team, or a handoff as if that were the
system.

Handoffs, tickets, and stage gates can be legitimate. They can also be
the accidental architecture of delivery. Design the engineering system
first. Then decide which interactions still earn their keep.

See [Design doctrine](../00-foundations/design-doctrine.md).

## What "optimize" means here

The engineering system is the **unit of reasoning**. Tradeoffs should be
judged against that system rather than assuming that locally optimal
capabilities produce an effective whole.

This principle does not compute, guarantee, or enforce a system-level
result. There is no single computable optimum. Competing outcomes,
independent obligations, regulatory constraints, risk, local autonomy,
and uncertainty can all make more than one choice defensible.

Sustained improvement at system scope requires
[incentive compatibility](../04-operating-model/README.md#incentives).
Convergence names that as a precondition. It does not supply budgeting,
metrics, funding, or organizational alignment.

[Observation](../03-architecture/observation.md) can make system-level
tradeoffs, dependencies, evidence, and misalignment explicit and
attributable, so that not acting is visible as a decision. It cannot make
the decision.

System-level reasoning does not grant authority to override a
contributing domain. A locally worse, systemically attractive trade is
not automatically legitimate. An independent security or regulatory
authority may correctly refuse a change that would improve delivery
latency. **Better** remains contextual and multi-objective: what better
satisfies the relevant intent and outcomes while preserving the
constraints, authorities, and obligations that legitimately apply — not
simply what is faster. See
[How not to measure Convergence](../00-foundations/design-doctrine.md#how-not-to-measure-convergence).

How organizations actually align incentives, and how system-level
stewardship is implemented, remain
[open questions](../00-foundations/open-questions.md).

## What to design

The relevant system is the one through which a class of intent moves
toward outcome. That system may be a team, a domain, a business unit, a
region, an enterprise, or a federation. Convergence does not require one
homogeneous enterprise system.

**Converge where outcomes require coherence. Preserve autonomy where they
don't.**

**Convergence seeks coherence where coherence provides value, not
uniformity everywhere.**

## Handoffs are not the unit of work

A handoff is a fact of realization. It is not the product. Designing
around handoffs produces more routing, more translation, and more
inherited process. Designing around capabilities produces a place for
expertise to participate without making the org chart the interface.

This principle does not say every handoff is waste. Independent review,
separation of duties, and novel collaboration can be intentional.

## What this principle does not mean

- Eliminate Platform, SRE, Security, or any other specialty.
- Mandate one platform or one implementation.
- Treat ticket reduction as success.
- Treat every approval as a defect.
- Create a Convergence function that becomes the new routing layer.

See [Major Principle 3](03-organization-is-an-implementation-detail.md).
