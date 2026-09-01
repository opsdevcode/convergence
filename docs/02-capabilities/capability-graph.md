# Capability graph

A **capability graph** is the conceptual web of capabilities and their
relationships.

A capability can:

- consume other capabilities (composition / dependency)
- expose a contract
- have policies bound to it or to particular edges
- produce telemetry
- be consumed by people
- be consumed by products
- be consumed by software systems
- be consumed by automation
- be consumed by AI agents
- be consumed by other capabilities

Nodes are capabilities (and, optionally, consumer classes). Edges are
"composes," "authorized to consume," or "emits feedback to." This is a
model for thinking and for discovery, not a mandate to render a giant
org-chart replacement in a GUI.

## Why a graph

Lists of "platform services" hide coupling. A graph makes it visible that
`DeployApplication` is only as strong as the identity and policy
capabilities it composes. It also makes blast radius discussable: a
breaking change in `Secrets` is not a local ticket storm; it is a graph
event.

## Consumers on the graph

Humans, products, software systems, automation, and agents are different
entry points into the same graph. They should not each get a private shadow org process. They
may get different *experiences* and different authorization.

Your organizational structure should not become your software delivery API.
The graph is the API-shaped view of delivery. The org chart is how you
staff providers.

See [Capability consumers](../../diagrams/capability-consumers.md).

Related architecture: [Converged architecture](../03-architecture/converged-architecture.md).

## Policy and telemetry

Policy can sit on a capability ("this capability is not available in
production without data-class X") or on a composition ("this product may
compose `DeployApplication` but not raw `Compute`"). Telemetry should be
attributable to capability and consumer so learning has somewhere to go.

## What the graph is not

It is not a CMDB by another name, though CMDBs may overlap. It is not a
requirement that every script be a node. Start with capabilities that
encode scarce expertise and sit on customer paths.

**TODO:** Later architecture work should discuss versioning of the graph, cyclic composition,
and how to represent paved paths as distinguished subgraphs without turning
the path into another silo.
