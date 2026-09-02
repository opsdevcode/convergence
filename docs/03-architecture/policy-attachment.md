# Policy attachment

Policy has to bind somewhere in the structure. Which attachment point is
chosen determines what the policy can express, when a consumer learns
about it, and whether it can be bypassed.

[Policy at the edge or in the node](../07-patterns/policy-at-the-edge-or-in-the-node.md)
covers the most common placement decision as a pattern. This document
covers the full set of attachment points and what each one is structurally
capable of.

## Attachment points

| Attachment point | Can express | Cannot express |
| --- | --- | --- |
| Capability | Which classes of intent are in scope at all | Anything about a specific case |
| [Contract](../02-capabilities/capability-contract.md) | What the consumer may rely on and must supply | Enforcement; a contract states, it does not compel |
| [Experience](../02-capabilities/experience.md) (edge) | Constraints legibly, before the consumer commits | A guarantee, because the edge can be bypassed |
| [Realization](../02-capabilities/realization.md) (node) | Enforcement that does not depend on the caller | Early feedback; refusal arrives late by construction |
| Composition edge | Whether these capabilities may combine, and under what conditions | Anything about a single capability in isolation |
| Consumer class | Different policy for an agent than for a person, over one capability | A substitute for authorization the organization already decided |

## No single point is sufficient

Each attachment point has a characteristic failure when used alone.

| Attached only at | Fails as |
| --- | --- |
| Edge | Advisory guidance that the determined consumer routes around |
| Node | A late refusal after the consumer has already committed effort |
| Contract | A documented expectation nothing holds anyone to |
| Capability | Coarse eligibility with no view of the specific case |

Edge and node together are the usual minimum: the edge exists so
consumers learn constraints early, the node exists because enforcement
cannot depend on the consumer's goodwill. They must agree. An edge that
promises what the node refuses is worse than no edge policy, because it
teaches consumers to distrust the feedback.

## The composition edge is the point most often missing

Most organizations attach policy to capabilities and realizations and
leave the composition edge unguarded. That is precisely where authority
expands silently.

A consumer authorized for a composite is not thereby authorized for
everything the composite touches. Something in the structure has to say
so, and the natural place is the composition relation itself rather than
either of the capabilities it joins. See
[composition](composition.md).

## Consumer class is an attachment point

The same capability can carry different policy for different classes of
consumer without becoming two capabilities. A human may be permitted to
proceed with a warning where an agent is not, because the human can be
asked to exercise judgment and accept consequence.

This is a structural allowance, not a licence to invent a lighter
authorization story for agents. Agents act with a principal and under
policy the organization already decided. **Invocation is not authority.**
See
[Authorization and principals](../05-ai-native-engineering/authorization-and-principals.md).

## Policy must not manufacture certainty

Encoded policy represents organizational knowledge. It is not a perfect
representation of reality, and a policy evaluation returning "permitted"
is not a statement that an action is wise.

**Abstract complexity. Expose consequence and uncertainty where they
matter to responsible action.** Where a policy decision rests on
assumptions that may not hold, the architecture should surface that to
whoever carries the consequence rather than resolving it into a clean
boolean.

## Proportional formalism

**Formalism should scale with organizational distance, risk, consequence,
reuse, and complexity.**

A rule that two people apply within one team can be a sentence in a
handbook and a required check. A rule that crosses a regulatory boundary
and is consumed by twelve domains probably needs to be machine-readable,
versioned, and evidenced. Both are policy attachment.

## Not in scope here

- No required policy language, engine, or schema.
- No control plane. Implementation belongs in
  [Reference architecture](../09-reference-architecture/README.md) and
  [Reference implementations](../10-reference-implementations/README.md).
- No claim that encoded policy replaces judgment. Review and escalation
  remain appropriate for exceptional and high-risk cases.
- This repository does not replace identity, access management,
  governance, risk, or regulatory frameworks.
