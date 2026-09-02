# Authorization and principals

The most common design error with agents is to treat the ability to call a
capability as permission to cause its effects. It is not. This document
develops what an agent is allowed to do, using the distinctions already in
[Major Principle 5](../01-principles/05-distribute-execution.md) rather
than inventing new ones.

This is not an identity or access-management design. It defines no token
format, protocol, or directory. It states what has to be true
conceptually, and leaves the mechanism to existing security practice,
which Convergence does not replace.

## An agent acts for a principal

An agent is never the source of authority. It acts with and for a
**principal**: a user, a service account, or a workflow identity that the
organization has already reasoned about.

| The principal is | The agent is |
| --- | --- |
| The party the organization authorized | A consumer acting on that party's behalf |
| Accountable for what is done under it | The mechanism, not the accountable party |
| Scoped by decisions made before the agent ran | Bound to that scope, never wider |

"The agent did it" is never a complete account of an action. "The agent
did it for this principal, under this scope" is.

## Four distinctions, unchanged from Principle 5

Agents do not need new vocabulary. They need the existing distinctions
applied honestly.

| Term | For an agent |
| --- | --- |
| Authority | Who determines what correct means. Never the agent; it holds none |
| Privilege | What the agent is technically permitted to do, for this principal |
| Execution | The agent performing the action |
| Ownership | Who is accountable for the capability and the outcome. Not the agent |

An agent has privilege and performs execution. It never holds authority or
ownership. Collapsing these is how an invocation becomes an unaudited
decision.

## Delegation does not widen

When a human directs an agent, they delegate a scoped task, not their
standing. The agent receives privilege bounded by the intent and by the
principal, and no more.

| Delegated | Not delegated |
| --- | --- |
| A specific task, within a stated scope | The principal's full standing |
| Privilege sufficient for that task | Authority over the domain |
| Accountability that remains with the principal | A new, lighter accountability for "the AI" |

A human who may approve one exception has not authorized an agent to
approve exceptions. The agent may prepare, propose, and execute what was
permitted; it does not inherit the judgment.

## Invocation is not authority

**Invoking a capability does not grant authority.** An agent with a
`DeployApplication` tool is not thereby permitted to deploy anything, to
any environment, at any time. It is permitted exactly what its principal's
privilege and the capability's contract allow.

This is the same rule the anti-pattern
[Invocation as authority](../08-anti-patterns/invocation-as-authority.md)
warns about, stated from the architecture side: authorization derives from
the principal and the contract, never from the presence of a tool.

## Composition must not widen authority

When an agent invokes a
[composite capability](../02-capabilities/composite-capabilities.md), the
composite's contributing capabilities carry their own constraints and
authorities. The composite must not become a way to reach an effect the
principal could not reach directly.

**Composition must not silently expand authority.** An agent authorized
for the composite is not authorized for everything underneath it. See
[Composition](../03-architecture/composition.md) and
[Policy attachment](../03-architecture/policy-attachment.md), where the
composition edge is a policy attachment point precisely so that this does
not happen.

## Recording is part of authorization

Because an agent's call sequence may not reveal why it acted, the intent
it was given is part of the authorization record, not just the execution
log. "This principal directed this agent toward this intent, and it was
permitted to do these things in service of it" is the account an audit
needs. See [Observation](../03-architecture/observation.md).

## What this is not

- Not an IAM, RBAC, or policy-engine design. No formats, no protocols.
- Not a claim that agents need weaker controls because they are
  convenient. They need the controls the organization already defined,
  applied without exception.
- Not a replacement for security, identity, or governance functions.
  Convergence makes the exposure explicit; those functions still own the
  controls.
