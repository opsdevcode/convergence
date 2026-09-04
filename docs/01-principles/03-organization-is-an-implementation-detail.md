# Organization is an implementation detail, not a delivery interface.

**Major Principle 3 of Convergence** (working doctrine, v0.1)

Organizational structure should not become the software delivery API.
Consumers of routine intent should not have to assemble the org chart to
get work done.

Organizational structure is **not** irrelevant.

**Organizational structure should participate in delivery where
organizational separation itself carries engineering or governance
value.**

**Convergence abstracts routing, not accountability.**

**Abstraction should remove information from the execution path without
necessarily removing it from the engineering system.**

## What remains visible

Ownership, authority, provenance, operational responsibility, and
auditability may remain visible and discoverable even when consumers do
not navigate them to accomplish routine intent.

[Organizational independence](../02-capabilities/organizational-independence.md)
must not imply organizational opacity.

| Abstracted out of the execution path | Designed into the path |
| --- | --- |
| Which team owns the next step for routine intent | Separation of duties and independent authority |
| The intake form, the queue, the re-explanation | Regulatory obligation and risk containment |
| Discovering whom to ask | Legal entity separation, geographic or residency constraints |
| Organizational sequence as the delivery interface | Human judgment and domain responsibility |

Anything in the right column can make a boundary intentional, and belongs
in [experience](../02-capabilities/experience.md) and
[realization](../02-capabilities/realization.md) by design rather than
rediscovered as tribal routing.

## What this principle does not mean

- All organizational boundaries are bad.
- Teams, legal entities, or regions should disappear.
- Accountability is hidden because routing is hidden.
- Convergence requires reorganization.
- One enterprise org chart or one platform is required.

## Lineage

That organizational structure becomes embedded in system design is Conway's
Law (1968), not an observation original to Convergence. This principle accepts
that relationship and asks a delivery question on top of it: how much
organizational knowledge should a consumer need to accomplish routine intent?
See [Prior art](../00-foundations/prior-art.md#conways-law-and-the-inverse-conway-maneuver).

See [Major Principle 1](01-specialization-remains-silos-dont.md) and
[Design doctrine](../00-foundations/design-doctrine.md).
