# Capability model

This is an early formal model of the capability mechanism. It is
intentionally incomplete. v0.2 should tighten required vs. optional fields
and add a second example besides `DeployApplication`.

## Position in the hierarchy

Convergence is the shift. Converged Engineering is the model. This section
specifies **capabilities** as a way to encode expertise so delivery does
not require walking the org chart.

Other mechanisms (how teams are funded, how product process works, how
incidents are staffed) matter. A complete capability catalog will not, by
itself, fix a missing product strategy or an understaffed security function.

## Lifecycle

```
Intent → Capability → Experience → Outcome → Learning
```

Learning feeds back into capabilities. A pipeline that ends at "handoff to
ops" is the default shape this mechanism is trying to replace, not a
practice it refuses to ever use.

- **Intent** is the outcome a consumer is trying to achieve.
- **Capability** is encoded expertise that can fulfill that intent under a
  contract.
- **Experience** is how a human, product, software system, automation, or
  agent consumes the capability.
- **Outcome** is the measurable result for a customer or the business.
- **Learning** is telemetry, incident knowledge, cost, and usage that
  improve the capability.

## Who consumes

A capability can be consumed by humans, products, software systems,
automation, AI agents, and other capabilities. Authorization and experience
may differ. The [capability graph](capability-graph.md) should not.

Your organizational structure should not become your software delivery API.

## What to specify next

See [Anatomy](anatomy-of-a-capability.md) for facets and
[Capability contract](capability-contract.md) for the consumer-facing
surface.
