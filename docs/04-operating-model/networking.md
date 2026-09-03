# Networking

Networking expertise remains. Connectivity, segmentation, and trust
boundaries are not undifferentiated heavy lifting, and they do not become
simple because a product engineer wants a database reachable.

## What does not disappear

- Segmentation, routing, and failure-domain design
- DNS, certificates, and service discovery
- Ingress, egress, and edge policy
- Firewall, security-group, and zero-trust reasoning
- The judgment behind which boundaries are intentional

## What changes

Networking should increasingly appear as **realization of higher-level
capabilities** rather than a team a consumer files tickets against for
every routine connection.

| Was requested as | Becomes |
| --- | --- |
| A ticket for a subnet, a rule, a DNS entry | A constraint inside `ProvideConnectivity` |
| Per-service firewall negotiation | Standard connectivity for the common case, stated in a contract |
| "Which team owns the load balancer?" | An [experience](../02-capabilities/experience.md) that does not require knowing |

The recurring, understood cases become part of a capability the consumer
never has to route for. Novel topologies, unusual egress, and genuinely
new trust boundaries remain networking judgment, reached through an
[explicit exception path](../07-patterns/explicit-exception-path.md).

Segmentation is often **intentional constraint**, not accidental friction.
A boundary that contains blast radius or separates trust zones should be
designed into the path, not removed because it slowed a deploy. See the
[design doctrine](../00-foundations/design-doctrine.md).

## Networking as a contributor

Networking is frequently a domain authority behind a
[composite](../03-architecture/composition.md) such as `DeployApplication`.
Contributing connectivity to that composite does not transfer networking's
authority over segmentation to the composite's owner. Composition moves
obligation, not authority.

## What this is not

Not "the network team is obsolete because the cloud handles it." The cloud
moved where the work happens; it did not remove the expertise. The request
catalog should shrink as the primary interface. The skill should not.
