# Operating and evolving

**Serves:** [Major Principle 6](../01-principles/06-close-the-loop.md).

> Learning is evidence capable of changing what the engineering system
> believes.

An encoded path is not finished. This document covers what happens after
it is in use, and it is where several topics from
[open questions](../00-foundations/open-questions.md) become practical
rather than theoretical.

## What evidence should reach the owner

[Learning](../02-capabilities/learning.md) is not limited to telemetry.
The evidence that most often changes a capability is qualitative and
arrives by accident unless someone routes it deliberately.

| Evidence | What it usually means |
| --- | --- |
| Exceptions granted | The contract's boundary is in the wrong place |
| Consumers routing around the path | The experience costs more than the workaround |
| Abandonment partway through | The consumer learned a constraint too late |
| The same question asked repeatedly | Discovery or documentation is failing, not the capability |
| Incidents involving the path | A realization assumption was wrong |
| Security findings and threat intelligence | The risk model behind the encoding moved |
| Audit and regulatory change | An obligation changed, not the engineering |
| A specialist quietly doing manual work again | The encoding no longer covers reality |

That last row is the most useful and the least instrumented. It rarely
shows up in a dashboard.

## Decay

Encoded expertise ages. The knowledge was true when it was written and
the world moved.

Signals that an encoding is decaying:

- Exceptions rise steadily without a change in demand.
- The owner has left and no successor was named.
- Nobody can explain why a constraint exists.
- The specialist is doing manual work beside the encoded path rather than
  improving it.
- Nothing has changed in it for a long time, in a domain that has.

**Encoded expertise without living expertise eventually becomes legacy.**
Decay is not failure of the model. It is the expected cost of encoding,
and it is a reason to name an owner at the time of encoding rather than
after.

## Semantic drift

A subtler failure: the name stays stable while the meaning moves.
`DeployApplication` still exists, but what it now includes, assumes, or
quietly excludes has changed, and consumers hold different beliefs about
it.

Signals: consumers disagree about what the capability guarantees; the
contract and the behavior diverge; the same name means different things
in two domains.

The response is not renaming for its own sake. State the current meaning,
correct the contract, and where two meanings have genuinely separated,
split them into two capabilities rather than defending one word.

## Reversibility

Two distinct questions, both worth asking before they are urgent.

| Consumer reversibility | Organizational reversibility |
| --- | --- |
| Can a consumer undo what they just caused? | Can the organization unwind this encoding? |
| Is the undo path as discoverable as the do path? | Is the prior realization still viable? |
| What is destroyed rather than detached? | Who has the authority to decide to unwind? |

Delegated execution raises the stakes of both. The more execution is
delegated, the more uncertainty, consequence, authority, and recovery
must be explicit. v0.1 does not define a reversibility rating, and this
section is not one.

## Change what, exactly

Not all change is the same change, and conflating them is how consumers
lose trust.

| Realization change | Capability change |
| --- | --- |
| How it is fulfilled | What the system can accomplish |
| Consumers should not need to care | Consumers need to be told |
| Owned by domain authority and capability owner | Renegotiates expectations |
| Example: managed service replaces self-hosted | Example: a data class is no longer eligible |

A realization change that consumers must react to was a capability change
that was not labelled as one.

## Deprecation, splitting, retiring

- **Deprecate a contract version** when expectations change but the
  ability remains.
- **Split a capability** when one name has come to serve two classes of
  intent with different constraints.
- **Merge** when two names have converged on the same intent and the
  difference is now only historical.
- **Retire a capability** when the class of intent itself is gone, not
  when its current realization is inconvenient.

Retiring a capability because its realization is awkward usually means
the intent moves into shadow processes and stops being visible.

## Stewardship at the scope of the concern

Some dysfunction sits between capabilities, where no individual owner is
incentivized or authorized to fix it. Concentration risk across several
composites is the common example.

**Stewardship should exist at the level where the concern exists.** That
may be a team, a domain, a cross-domain group, an enterprise function, or
a federation agreement, and it may be formal or informal.

This repository does not prescribe a council, office, board, or role. The
organizational implementation remains an
[open question](../00-foundations/open-questions.md). Creating a function
that becomes the routing layer for Convergence would recreate the
original problem.

## Evidence does not guarantee action

**Learning informs change; it does not automatically mandate change.**
**Learning creates evidence for evolution; it does not guarantee that an
organization will act on that evidence.**

A method cannot fix that, and claiming otherwise would be dishonest.
Incentives and politics can block a well-evidenced change. What the
method can do is make the evidence explicit and attributable, so the
decision not to act is visible as a decision rather than as an accident.
