# Terminology

These terms are the working vocabulary for this repository. Prefer them over
near-synonyms unless an RFC replaces them.

Use the hierarchy consistently:

| If you mean | Say |
| --- | --- |
| The broader shift away from delivery-by-org-boundary | **Convergence** |
| The proposed engineering model for operating in that shift | **Converged Engineering** |
| Encoded expertise under a contract | **capability** (and Capability Model, contract, graph) |
| Historical or systems-engineering uses of a similar phrase | **Capability Engineering** (see below); do not use this as the name of *this* body of work |

## Convergence

The shift from software delivery through organizational boundaries toward
an engineering system in which specialized disciplines contribute to
shared capabilities and outcomes. A working name for a phenomenon, not a
team and not an established industry definition. See
[Convergence](convergence.md).

## Converged Engineering

A proposed engineering model in which specialized disciplines contribute
expertise through shared, reusable, governed capabilities and share
responsibility for the outcomes those capabilities enable. A way existing
roles can work; not a new specialty. See
[Converged Engineering](converged-engineering.md).

## Capability

A reusable expression of engineering expertise that exposes a defined
contract and can be consumed or composed without requiring the consumer to
navigate the organizational structure that produced it. A capability may
compose other capabilities. It is not a team, a ticket category, or a cloud
product name, though those may implement or provide it.

Capabilities are a primary mechanism of Converged Engineering, not the
only conceivable mechanism of Convergence.

## Capability consumer

Any actor that invokes a capability: a human, a product, a software
system, automation, an AI agent, or another capability. Consumers differ
in how they discover, authorize, and observe. They should not need to know
the providing team's org chart.

## Capability contract

The stated interface of a capability: how to invoke it, what it accepts and
returns, and the commitments and limits that come with use (policy,
security, reliability, cost, and similar). Not every field must be equally
rigorous for every capability. See
[Capability contract](../02-capabilities/capability-contract.md).

## Capability provider

The owner responsible for offering, operating, and evolving a capability.
Often a specialist team (SRE, security, infrastructure, platform, data).
Provider is an ownership role, not a job title that replaces those
disciplines.

## Capability graph

The web of capabilities, their composition relationships, consumers, and
attached policy and telemetry. A conceptual model, not a requirement to
deploy a particular graph database. See
[Capability graph](../02-capabilities/capability-graph.md).

## Intent

A consumer's goal expressed at the level the consumer should have to care
about (for example, "deploy this application in the production environment
for team X under the standard service policies"). Intent is the preferred
interface. Implementation details belong below the contract.

## Outcome

A measurable result for a customer or for the business (and, internally, for
the health of the capability itself). Outputs (a cluster exists, a ticket
closed) are not outcomes.

## Experience

How a consumer encounters a capability: CLI, API, IDE, product UI, workflow
engine, or agent tool-calling. Experience should not be the place where
governance is reinvented as a side process.

## Policy

Rules that constrain how a capability may be used or how it may behave:
who, what, where, when, at what risk, at what cost. Policy should be part
of the capability's encoded governance, not only a meeting after the fact.

## Composition

Building a higher-level capability or experience from other capabilities,
through their contracts, without exposing every underlying implementation
to the consumer.

## Capability lifecycle

The stages of a capability as an engineered artifact: proposed, available,
deprecated, retired, and the versioning of its contract. Distinct from an
application's release lifecycle, though they interact.

## Feedback

Telemetry, traces, incidents, cost, usage, and qualitative learning that
should change the capability. Feedback is how the lifecycle loop closes.

## Specialization

Concentrated engineering expertise in a domain (infrastructure, security,
reliability, networking, identity, data, product, platform, and others).
Specialization is not a silo. See
[Specialization remains. Silos don't.](../01-principles/01-specialization-remains-silos-dont.md).

## Silo

A restriction of access to expertise such that routine delivery must go
through that group's people and process. A team with healthy ownership is
not automatically a silo.

## Organizational boundary

A line of ownership, accountability, domain authority, or separation of
concerns. Boundaries can be healthy. Routine execution that depends on
traversing a boundary (tickets, queues, meetings, tribal knowledge) is
what Convergence challenges.

## Repeatable work

Understood, predictable engineering interactions. Repeatability is a
signal that expertise may be ready to encode. It is not a rule that every
repeated interaction must be automated or self-service.

## Novel work

Exceptions, unusual risk, architectural decisions, and judgment not yet
covered by an encoding. Novel work remains collaborative.

The specialized knowledge held in disciplines such as product, platform,
SRE, infrastructure, cloud, networking, identity, security, data, and AI
engineering. Converged Engineering treats this expertise as the source
material to encode, not as a problem to eliminate.

## Related phrases

| Phrase | Meaning here |
| --- | --- |
| Encoded expertise | Knowledge made reusable through a capability and its contract, not only stored in people and tickets |
| Self-service | The default *interface* is invocation of a capability, not a request to a queue. Self-service does not mean ungoverned. |
| Paved path | A recommended composition of capabilities for a common intent. A path is not a substitute for a contract. |
| Delivery boundary | A point where work must wait on another specialty's queue, approval, or tribal process in order to proceed |

Avoid using "platform," "service," "capability," "Convergence," and
"Converged Engineering" interchangeably. If you mean the internal developer
platform, say platform. If you mean encoded expertise under contract, say
capability. If you mean the industry shift, say Convergence. If you mean
the operating model, say Converged Engineering.

## Note on "Capability Engineering"

This repository originally used **Capability Engineering** as the name of
the overarching discipline. That framing was revised: capabilities are the
mechanism; Converged Engineering is the model; Convergence is the broader
shift.

The phrase "Capability Engineering" also appears in other fields, including
systems engineering and defense-related capability development, where it
often means eliciting, specifying, and delivering operational capabilities
for a system-of-systems. This repository does not claim to have coined the
phrase and does not replace those bodies of work.

**TODO:** Add researched citations and a short comparison to established
systems-engineering uses of "capability" after a proper literature pass.

Do not revive "Capability Engineering" as the title of *this* model unless
an RFC explicitly does so.
