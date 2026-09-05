# Terminology

Working vocabulary. Prefer these terms unless an RFC replaces them.

| If you mean | Say |
| --- | --- |
| Treating delivery as an engineering system rather than a function walk; emerging methodology (working name) | **Convergence** |
| The proposed design of that system | **Converged Engineering** |
| What the engineering system can accomplish | **capability** |
| How it is currently fulfilled | **realization** |
| How a consumer interacts with it | **experience** |
| Historical / systems-engineering phrase | **Capability Engineering** (not the name of this model) |

## Convergence

A working name for an **emerging methodology** for designing software
delivery as a coherent engineering system rather than a sequence of
organizational handoffs. Working name, not an established industry
movement, not a mature methodology, and not a new discipline. Not the same
as the separately published
"Convergence Engineering" methodology (Sunnyday Technologies), the National
Academies' "convergent engineering," converged or hyperconverged
infrastructure, or IT/OT and network convergence. See
[Prior art](prior-art.md#not-to-be-confused-with) for the disambiguation and
sources.

## Converged Engineering

Designs that engineering system so specialized expertise can participate
in delivery through capabilities without requiring consumers to navigate
the organizational structures behind them. A way existing roles can work;
not a new discipline or specialty. See
[Converged Engineering](converged-engineering.md).

## Intent

The result a consumer is trying to cause, expressed at the level of
responsibility that consumer owns. Higher abstraction is not always
better. See [Intent](../02-capabilities/intent.md).

## Capability

An organization's ability to satisfy a class of intent through the
application of expertise, resources, and systems. Describes **what** the
engineering system can accomplish. Not inherently an API, service,
workflow, platform feature, product, team, or person. Need not have a
formal contract to exist. See [Capability](../02-capabilities/capability.md).

## Expertise

What someone (or a specialist group) knows. Distinct from capability:
expertise is knowledge; capability is what the engineering system can
accomplish with that knowledge.

## Experience

The means by which a consumer discovers, understands, requests, uses,
observes, and interacts with a capability. Broader than UI. See
[Experience](../02-capabilities/experience.md).

## Realization

The people, processes, technologies, policies, services, and mechanisms
through which a capability is fulfilled. Describes **how** it is currently
accomplished. The capability may stay stable while realization changes.
See [Realization](../02-capabilities/realization.md).

## Output

Something produced (a database exists, a ticket closed, a report written).
Not the same as an outcome.

## Outcome

A resulting state that satisfies or advances intent. Outcomes can
contribute upward (capability → engineering → product → customer →
business) without the lower capability owning the business result. See
[Output and outcome](../02-capabilities/output-and-outcome.md).

## Learning

Evidence capable of changing what the engineering system believes. Not
limited to telemetry. Informs change; does not mandate it. See
[Learning](../02-capabilities/learning.md).

## Capability contract

The explicit description of expectations and constraints governing
consumption and fulfillment of a capability. Not the capability itself.
Rigor is proportional. See
[Capability contract](../02-capabilities/capability-contract.md).

## Composite capability

A capability that satisfies intent by composing other capabilities.
Composition is recursive and relative to the abstraction being modeled.
Lower-level capabilities are not objectively "atomic." See
[Composite capabilities](../02-capabilities/composite-capabilities.md).

## Capability graph

A conceptual representation of what the engineering system can accomplish,
how those capabilities relate and compose, what constrains them, and which
outcomes they contribute to. Not inherently a graph database, CMDB,
catalog, org chart, platform, or control plane. May be partial or
federated. Not a required enterprise graph. See
[Capability graph](../02-capabilities/capability-graph.md).

## Organizational independence

The degree to which consumers can discover and use a capability without
understanding the organizational structure responsible for its
realization. A spectrum, not a binary. Ownership remains. Must not imply
opacity. See
[Organizational independence](../02-capabilities/organizational-independence.md).

## Domain authority

Accountable for what is correct within a specialized domain.

## Capability ownership

Accountable for stewardship and continued fitness of a capability.

## Outcome ownership

Accountable for the result closest to the intent being pursued.

Shared contribution does not require shared accountability. See
[Ownership and authority](../02-capabilities/ownership-and-authority.md).

## Privilege

What an actor is technically permitted to do. A separate concern from
authority, ownership, and execution. Ownership is not itself a security
boundary. See
[Ownership and authority](../02-capabilities/ownership-and-authority.md).

## Coordination

Work required primarily to route execution through organizational
structure (which form, which queue, which channel).

## Collaboration

Work required to solve a problem whose answer is not yet sufficiently
encoded or understood.

See [Coordination and collaboration](../02-capabilities/coordination-and-collaboration.md).

## Capability consumer

Any actor that uses a capability: a human, product, software system,
automation, authorized AI agent, or another capability.

## Principal

A user, service account, or workflow identity that the organization has
already reasoned about. An AI agent acts *for* a principal; invoking a
capability does not by itself grant authority. See
[Authorization and principals](../05-ai-native-engineering/authorization-and-principals.md).

## Federation

A boundary condition of Convergence, not a separate framework or a stage
of maturity. Convergence can exist as a federation of engineering systems
that become coherent at the boundaries where they must interact.
Recursively applicable. See [Federation](../03-architecture/federation.md).

## Stewardship

Responsibility for a concern that no single capability owner is
incentivized or authorized to correct. It should exist at the level where
the concern exists (local, domain, cross-domain, enterprise, or
federated). Not a prescribed council, office, board, or role, and its
organizational implementation is an
[open question](open-questions.md). Distinct from capability ownership.

## Specialization, silo, organizational boundary

A **specialization** concentrates expertise. A **silo** restricts access
so routine delivery must go through that group's people and process. An
**organizational boundary** can be healthy (ownership, authority, risk).
See [Specialization remains. Silos don't.](../01-principles/01-specialization-remains-silos-dont.md).

## Repeatable work and novel work

**Repeatable** interactions are understood and predictable enough that
encoding may be warranted. **Novel** work remains collaborative.
Repeatability is a signal, not a rule to automate everything.

## Related phrases

| Phrase | Meaning here |
| --- | --- |
| Encoded expertise | Repeatable knowledge represented in reusable mechanisms (not only in people and tickets) |
| Self-service | One possible experience; not required for a capability to exist |
| Delivery boundary | A point where work waits on another specialty's queue, approval, or tribal process |
| Paved path | A recommended composition; not a substitute for distinguishing capability, experience, and realization |
| Accidental complexity | Friction or process that mainly reflects organizational shape, not engineering or governance value. See [Design doctrine](design-doctrine.md). |
| Intentional constraint | A designed boundary or source of friction that provides authority, judgment, safety, risk, or similar value. Same document. |
| Blast radius | The extent of what an action can affect. A limit designed into a contract, not a general measurement system. |
| Concentration risk | Reuse creates leverage and concentration together; leverage amplifies correctness, error, and compromise. An [open question](open-questions.md). |
| Semantic drift | The name stays stable while the meaning moves; consumers hold different beliefs about the same capability. See [Operating and evolving](../12-method/operating-and-evolving.md). |
| Break-glass | Intentional friction inverted in time: action first, judgment recorded after. A path used routinely is not break-glass. See [Break-glass with evidence](../07-patterns/break-glass-with-evidence.md). |

Do not use "platform," "service," "capability," "experience,"
"realization," "Convergence," and "Converged Engineering"
interchangeably.

## Note on "Capability Engineering"

This repository originally used that phrase as the name of the
overarching discipline. Capabilities are now a mechanism. The phrase also
appears in systems engineering and related fields.

**TODO:** Add researched citations after a literature pass.

Do not revive "Capability Engineering" as the title of this model unless
an RFC does so.

"Capability provider" appeared in earlier drafts as the offering owner.
Prefer **capability ownership** unless discussing a specific provider
role in an example.
