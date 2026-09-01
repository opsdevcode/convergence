# Capability contract

A **capability contract** is the consumer-facing truth of a capability: how
to use it, what it promises, and what it refuses.

It is closer to an API plus operational and policy commitments than to a
legal contract. It should be specific enough that a human, a product, and an
agent can decide whether they are allowed to call it and what "success"
means.

## Why contracts exist

Without a contract, a "capability" is a team with a reputation. Consumers
learn by being burned. Agents cannot learn that way at organizational scale.

With a contract, composition is possible. `DeployApplication` can depend on
`Identity` without embedding the identity team's process.

## What a contract may include

Mapped from the [anatomy](anatomy-of-a-capability.md):

- Intent and applicability (when *not* to use this capability)
- Interface (API, CLI, events, agent tool definition)
- Inputs and outputs, including errors
- Authentication of the consumer and authorization model
- Policy bindings (always-on and input-dependent)
- Reliability and idempotency expectations
- Observability hooks the consumer is entitled to
- Cost and quota behavior
- Version and deprecation rules
- Ownership and escalation for out-of-contract situations

## Rigor is proportional

Not every capability needs a full reliability story on day one. A contract
that lies is worse than a short contract that is honest ("no SLO; beta;
expect breakage").

A useful test: could a new engineer or a constrained agent use this
capability without a hallway conversation? If not, the contract is not the
interface yet. The org chart still is.

## Governance in the contract

Encoded governance means the contract states the rules and the
implementation enforces them (admission, policy engines, continuous
verification). Review boards can still exist for exceptions and novel
systems. They should not be the only way a standard intent gets a yes.

## Change

Contract changes are capability lifecycle events. Breaking changes need
versioning. Silent changes teach consumers to bypass the capability.

**TODO:** In v0.2, decide whether this repository should recommend a minimum
contract profile (for example, identity of consumer, idempotency, and
declared policies) versus leaving minima entirely to adopting
organizations.
