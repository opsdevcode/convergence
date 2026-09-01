# Convergence as a function

A Convergence team is created. Perhaps a VP of Convergence, a Convergence
Office, or a Converged Engineering group. It owns the model, reviews
designs against it, and approves capability definitions.

Within a year, teams open tickets with the Convergence team to get
capabilities approved.

## Why it is tempting

Organizations resource things by creating owners for them. Without a
named owner, cross-cutting work genuinely does starve, and this concern
is legitimate: there is real system-level work that no individual
capability owner is incentivized to do.

The move also solves an accountability question cleanly. Someone can be
asked how Convergence is going.

## What it costs

| Cost | Detail |
| --- | --- |
| A new routing layer | The function becomes another queue on the delivery path |
| Recreated problem | Delivery once again traverses an organizational boundary for routine work |
| Displaced ownership | Teams treat Convergence as someone else's program |
| Reduced authority | Domain authorities lose standing to a group with no domain expertise |

This is the specific failure the model warns about most consistently,
because it is the failure that looks most like success from the outside.

## How to recognize it

- Capability definitions require approval from a central group.
- Teams describe Convergence as a program they are subject to.
- The function reports adoption of itself as the measure of progress.
- A design review exists whose purpose is compliance with the model.

## What to do instead

**Convergence cannot be delegated to a Convergence function.**

Converged Engineering is a property of the engineering system, not
another delivery specialty. A platform engineer, SRE, infrastructure
engineer, product engineer, or security engineer can practice it.

A transformation effort may have **stewardship**, and stewardship should
exist at the level where the concern exists: local, domain, cross-domain,
enterprise, or federated, formal or informal. This repository does not
prescribe a council, office, board, or role, and the organizational
implementation of system-level stewardship remains an
[open question](../00-foundations/open-questions.md).

The distinction that matters: stewardship holds concerns that have no
other home. It does not sit on the delivery path.

## Related

[Convergence](../00-foundations/convergence.md),
[Converged Engineering](../00-foundations/converged-engineering.md), and
[operating and evolving](../12-method/operating-and-evolving.md).
