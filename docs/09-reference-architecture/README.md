# Reference architecture

A conceptual reference for what an engineering system has to be able to
do. It is **non-normative**. No product is required to comply with it, and
no product can claim to implement it.

Each concern below is paired with what satisfying it can look like at
small scale, because a reference that only makes sense with a platform
would contradict the model. **Convergence should not require Convergence
infrastructure.**

Implementation examples belong in
[Reference implementations](../10-reference-implementations/README.md), and
even there nothing is canonical.

## Concerns

### Discovery

A consumer needs to find out what the engineering system can accomplish,
whether they are eligible, and what they will get, without knowing which
team owns the next step.

| At small scale | At larger scale |
| --- | --- |
| A handbook page listing what exists and who owns it | Searchable capability descriptions with stated eligibility |
| Conversation in a shared channel | Machine-readable descriptions for programmatic consumers |

Discovery that requires searching a wiki and then asking a person is a
search problem, not an interface.

### Separation of experience and realization

The system must let how something is consumed change independently of how
it is fulfilled, and vice versa.

| At small scale | At larger scale |
| --- | --- |
| A documented interface and a module behind it | Stable contract, multiple experiences, multiple realizations |
| One managed service, one convention | Regional or per-domain realizations under one capability name |

This is the concern most often violated by design. A portal that is
inseparable from the queue behind it has collapsed the two.

### Intent expression

Consumers express what they are trying to cause at a level they can
responsibly own, and learn relevant constraints before committing.

| At small scale | At larger scale |
| --- | --- |
| A declared config with a few fields, documented defaults | Intent-shaped inputs bound to policy at authoring time |
| A short conversation that establishes data class and size | Eligibility evaluated and explained before work starts |

Higher abstraction is not automatically better. See
[intent](../02-capabilities/intent.md).

### Composition

Capabilities must be able to participate in larger capabilities, with the
constraints of the contributors preserved rather than averaged away.

| At small scale | At larger scale |
| --- | --- |
| One documented standard path assembled from known parts | Composite capabilities with reconciled contracts |

Three constraints hold regardless of scale:

- Safety of individual capabilities does not guarantee safety of their
  composition.
- Composition must not silently expand authority.
- Composition is valid only when contributing contracts, constraints, and
  authorities can coexist.

### Encoded governance

Policy, risk, and regulatory obligations participate in the path rather
than arriving as a phase after the engineering is done.

| At small scale | At larger scale |
| --- | --- |
| A required check and a documented rule | Policy as code, evaluated at the edge and in the node |
| A named person who decides the rare cases | Explicit exception path with authority and retained evidence |

Encoded governance does not mean automated policy replaces judgment.
Review and escalation remain appropriate for exceptional and high-risk
cases.

### Consumption by unequal consumers

Humans, products, software systems, automation, and authorized agents all
consume capabilities. They do not have equal judgment or equal rights.

| Consumer | Needs the reference to support |
| --- | --- |
| Human | Explanation, exceptions, a route to a person |
| Product | Stable expectations and versioning |
| Software system | Programmatic use with no hallway context |
| Automation | Determinism and idempotency |
| Authorized agent | Parseable contracts, tight authorization, blast-radius limits, recorded intent |

Same capabilities, different experiences, different policy. Not a second
organization and not a required single graph. Invocation is not authority.

### Learning intake

Evidence produced by use has to reach whoever can change the capability.

| At small scale | At larger scale |
| --- | --- |
| The owner is in the channel where complaints land | Usage, exception, incident, and cost evidence routed to owners |
| Exceptions remembered because the team is small | Exceptions recorded, with reasons, and reviewed |

Learning informs change; it does not automatically mandate change, and it
does not guarantee the organization will act.

## What this reference does not include

- A required contract schema.
- A required graph schema, registry, or global capability taxonomy.
- A control plane, catalog, portal, or workflow engine as a requirement.
- An org structure, a funding model, or a team topology.
- Maturity levels or a compliance checklist.

A reference architecture that mandated any of those would make
Convergence dependent on an implementation, which
[the model refuses](../11-adoption/README.md).

## Related

[Converged architecture](../03-architecture/converged-architecture.md) for
the conceptual model and federation.
[Method](../12-method/README.md) for how to get from a current flow to any
of this.
