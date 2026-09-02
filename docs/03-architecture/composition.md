# Composition

Composition is the structural relation that lets one capability satisfy
an intent by drawing on others. It is the reason the engineering system
can present `DeployApplication` to a consumer who does not want to think
about identity, connectivity, secrets, or observability separately.

This document covers composition as **structure**. What a composite
capability is belongs to
[composite capabilities](../02-capabilities/composite-capabilities.md).
How to decide whether to build one belongs to the
[method](../12-method/designing-experience-and-realization.md).

## What composition moves and what it does not

The most consequential property of composition is that it transfers some
things and deliberately does not transfer others.

| Composition transfers | Composition does not transfer |
| --- | --- |
| The obligation to satisfy the consumer's intent | Authority over the contributing domains |
| Accountability for the composite's own coherence | Ownership of the contributing capabilities |
| The relevant constraints of every contributor | The privilege to bypass those constraints |
| Responsibility for the seams between contributors | Domain expertise, which stays where it lives |

The platform group that owns `ProvideRelationalStorage` as a composite
does not thereby acquire authority over network placement or data
classification. It owns the composite and the seams. Domain authority
stays with networking and security.

## Validity

Three constraints hold at every scale, and none of them is optional.

- The safety or correctness of individual capabilities does not guarantee
  the safety or correctness of their composition.
- Composition must not silently expand authority.
- Composition is valid only when the contracts, constraints, and relevant
  authorities of contributing capabilities can coexist.

The third constraint has a structural consequence worth stating plainly.
A composite cannot promise more than its contributors permit. If one
contributor restricts a data class and another does not, the composite
inherits the restriction; it does not average the two or pick the more
convenient one.

When contributors genuinely conflict, the architecture has three honest
responses and one dishonest one.

| Response | When it fits |
| --- | --- |
| Refuse to compose | The conflict is real and cannot be reconciled |
| Narrow the composite's contract | The overlap is still useful on its own |
| Route to an [exception path](../07-patterns/explicit-exception-path.md) | The conflict needs judgment, case by case |
| Promise the union anyway | Never. This is how composites start lying |

## Depth is relative

`DeployApplication` composes workload, identity, connectivity, secrets,
observability, and reliability. Each of those composes further. There is
no atomic layer, so the architecture does not have one either.

Model the level at which consumers actually express intent. Add depth
downward only where it changes a decision, an authority, or a constraint.
Modelling every cloud primitive as a capability produces an inventory
rather than an architecture.

## Concentration

**Reuse creates leverage and concentration risk simultaneously.**
**Leverage amplifies correctness, error, and compromise.**

This is a structural property of composition, not an argument against it.
A composite that carries most routine delivery is the most valuable thing
in the system and the most consequential place for a defect. The
architectural implication is modest and specific: know which composites
carry the most traffic.

Beyond that, concentration risk stays an
[open question](../00-foundations/open-questions.md). This repository does
not define dependency scoring or a systemic-risk algorithm.

## What composition is not

- Not a call graph. Contributors may be human, and the relation holds
  whether or not anything is invoked programmatically.
- Not a dependency inventory for rating fragility.
- Not a requirement for an orchestration engine. A documented standard
  path assembled from known parts is composition.
- Not a claim that deeper composition is better.

## At small scale

One page describing a standard path, naming the parts it draws on and the
constraints each part imposes, is a composed capability. The three
validity constraints still apply, and they are the part that matters.

## Related

[Standard path as a composed capability](../07-patterns/standard-path-as-a-composed-capability.md),
[Major Principle 5](../01-principles/05-distribute-execution.md), and
[Invocation as authority](../08-anti-patterns/invocation-as-authority.md).
