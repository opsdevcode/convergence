# Design doctrine

This is foundational reasoning for Convergence. It sits **beneath** the
[Major Principles](../01-principles/README.md). It is not a principle, not
Principle 0, and not a scoring system.

**Convergence removes accidental complexity while preserving intentional
constraint.**

**Remove accidental friction. Design intentional friction.**

Necessary boundaries should be designed into the engineering system.
Accidental boundaries should not define it.

**Convergence seeks appropriate leverage, not maximum abstraction,
automation, standardization, reuse, or self-service.**

Convergence is not optimized by maximizing any mechanism.

## A reasoning lens

The distinction between accidental and intentional is **contextual, not
absolute**. A boundary, control, or source of friction must be evaluated
by the value it provides to the engineering system, not merely by whether
it introduces friction.

Ask:

What value does this boundary, interaction, control, or source of friction
provide to the engineering system?

If the answer is legitimate engineering, governance, authority, judgment,
safety, or risk value, Convergence should preserve it or deliberately
design it into
[experience](../02-capabilities/experience.md) and
[realization](../02-capabilities/realization.md).

If the answer is primarily historical organizational routing, duplicated
effort, unnecessary translation, or process inheritance, it is a candidate
for redesign.

A boundary or control is not accidental simply because it slows delivery.

## Preserve

| Keep | Because |
| --- | --- |
| Expertise | Complex systems still need depth |
| Authority | Domain authority and capability ownership remain explicit |
| Judgment | Novel work and residual risk stay human |
| Accountability | Shared contribution does not require shared accountability |
| Context | Intent is expressed at a level the consumer can own |

Also preserve useful organizational boundaries, separation of duties, risk
containment, regulatory obligations, meaningful human interaction,
deliberate review, and deliberate friction when they provide that kind of
value.

See [Specialization remains. Silos don't.](../01-principles/01-specialization-remains-silos-dont.md),
[Ownership and authority](../02-capabilities/ownership-and-authority.md),
and [Expertise encoding](../02-capabilities/expertise-encoding.md).

## Reduce

| Reduce | Typical shape |
| --- | --- |
| Routing | The org chart as the delivery API |
| Coordination | Work spent finding which team owns the next step |
| Repetition | Applying already-understood expertise, ticket by ticket |
| Unnecessary cognitive load | Consumers reconstructing tribal process |
| Inherited process | Ritual that adds no engineering or governance value |
| Accidental friction | Friction caused only by organizational shape |

Convergence is trying to reduce organizational routing, unnecessary
coordination, repeated application of already-understood expertise,
duplicated interpretation, irrelevant cognitive load, inherited process,
and accidental friction.

See [Coordination and collaboration](../02-capabilities/coordination-and-collaboration.md)
and [Organizational independence](../02-capabilities/organizational-independence.md).

## Accidental friction

A product engineer needs routine relational storage. The intent is
understood. Eligibility, size class, and data class are known. Delivery
still requires separate tickets to infrastructure, networking, identity,
security, and a database group.

The specialties may be competent. The friction is usually accidental: the
consumer is assembling the organization rather than using a
[capability](../02-capabilities/capability.md). Encoding that repeatable
path does not remove database or security expertise. It stops routing
from defining the system.

A security architect applying the same known rule to every similar request
is the same pattern. The capability already exists. The realization is
spending scarce judgment on work the organization already understands.

## Intentional constraint

Independent approval for a high-risk change to a regulated production
system can be **intentional friction**. It can provide independent
authority, separation of duties, risk containment, human judgment, and
evidence for compliance. Convergence should not "remove" that approval
because it slows a deploy. It should be a designed property of the path
from [intent](../02-capabilities/intent.md) to
[outcome](../02-capabilities/output-and-outcome.md), including a clear
exception and break-glass path with explicit authority and evidence.

A break-glass production path with named authority, logging, and later
review is intentional constraint. Making every engineer discover which of
five teams owns a routine request is not.

## What this doctrine does not mean

- All friction is bad.
- All organizational boundaries are bad.
- All human approval is waste.
- Automation is more mature than human realization.
- Self-service is always preferable.
- Convergence requires a platform.
- Convergence requires organizational restructuring.
- Maximum reuse, standardization, or abstraction is the goal.

Boundaries may be intentional because they provide independent authority,
separation of duties, risk containment, human judgment, regulatory
compliance, blast-radius limitation, meaningful domain ownership, or
necessary expertise boundaries.

## How not to measure Convergence

Convergence is not measured by number of capabilities, automation
percentage, self-service adoption, platform adoption, ticket reduction,
cross-team interaction reduction, capability catalog completeness, or
elimination of human interaction. Those can be **signals**. They are not
the score.

Judge the engineering system by how effectively it converts intent into
outcomes while preserving necessary expertise, authority, judgment,
accountability, context, constraints, and learning.

See [Converged Engineering](converged-engineering.md) and
[Learning](../02-capabilities/learning.md).
