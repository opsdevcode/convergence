# Patterns

Recurring designs that have shown up more than once in practice, written
so they can be argued with.

A pattern here is not a recommendation to adopt. Each one states the
problem it addresses, what it costs, and when not to use it. A pattern
with no stated cost is marketing.

| Pattern | Addresses |
| --- | --- |
| [Standard path as a composed capability](standard-path-as-a-composed-capability.md) | Routine intent that currently walks the org chart |
| [Explicit exception path](explicit-exception-path.md) | Cases the standard path does not fit |
| [Break-glass with evidence](break-glass-with-evidence.md) | Urgent action that must outrun normal governance |
| [Policy at the edge or in the node](policy-at-the-edge-or-in-the-node.md) | Where a constraint should be enforced |
| [Incident to contract](incident-to-contract.md) | Learning that never changes anything |
| [Discoverable ownership](discoverable-ownership.md) | Hidden owners, or owners as the route |

## Relationship to the rest of the repository

Patterns apply the [Major Principles](../01-principles/README.md) through
the [method](../12-method/README.md). They do not extend the conceptual
core, and none of them is required to practice Converged Engineering.

Several of these patterns can be realized with documentation and
conventions. None of them requires a platform.

Failure modes are in [Anti-patterns](../08-anti-patterns/README.md).
