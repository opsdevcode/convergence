# Policy at the edge or in the node

## Problem

A constraint has to be enforced somewhere. Put it in the wrong place and
you get one of two failures: consumers learn about it far too late, or
every consumer reimplements it slightly differently.

## The pattern

Decide deliberately whether a given constraint belongs at the edge, where
consumption happens, or in the node, where fulfillment happens. Usually
both, doing different jobs.

| | Policy at the edge | Policy in the node |
| --- | --- | --- |
| Where | Experience: authoring, request, composition | Realization: the system that acts |
| Answers | May this consumer ask for this, and what will they get? | Will this actually be permitted to happen? |
| Fails as | Advisory that can be bypassed | A late refusal after commitment |
| Value | Fast, legible feedback before work is wasted | Enforcement that does not depend on the caller behaving |

Edge policy exists so consumers learn constraints before they commit.
Node policy exists because enforcement cannot depend on the consumer's
goodwill or correctness.

A data-class rule stated at authoring time is edge policy. The same rule
enforced where the resource is created is node policy. Both should exist
and they should agree.

## When it applies

Any constraint that a consumer can encounter, which is most of them.

## What it costs

| Cost | Detail |
| --- | --- |
| Duplication | The same rule expressed twice, in two forms |
| Divergence | The two copies can disagree, and the edge copy usually rots first |
| Maintenance | One owner has to keep both true |

Divergence is the real risk. An edge that promises what the node refuses
is worse than no edge policy, because consumers stop trusting the
feedback.

## When not to use it

- Trivially low-risk constraints where edge guidance is enough.
- Cases where the rule cannot be stated clearly enough to enforce, which
  means it is still judgment and belongs in an
  [exception path](explicit-exception-path.md).

## Related

[Capability contract](../02-capabilities/capability-contract.md) on
proportional rigor. Governance moves into delivery rather than delivery
moving through governance: see
[Regulated enterprise](../11-adoption/regulated-enterprise.md).
