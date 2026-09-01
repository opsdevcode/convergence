# Invocation as authority

An actor that can call a capability is treated as entitled to its
effects. This surfaces most often with AI agents: an agent has a tool for
`DeployApplication`, therefore the agent is treated as authorized to
deploy.

It also appears without agents. A consumer authorized for a composite is
assumed to be authorized for everything the composite touches.

## Why it is tempting

Exposure and authorization are easy to conflate because in practice they
usually arrive together. If someone gave the agent the tool, surely
someone decided it should have it.

With agents there is added pressure to move quickly, and authorization
design is slower than tool registration.

## What it costs

| Cost | Detail |
| --- | --- |
| Silent authority expansion | Composition grants reach that nobody deliberately granted |
| Unattributable action | The principal behind an action becomes unclear after the fact |
| Bypassed domain authority | Specialists discover their controls were composed around |
| Untraceable incidents | The call sequence is recoverable, the intent behind it is not |

## How to recognize it

- Agent permissions are described by which tools are registered rather
  than which principal they act for.
- A composite capability's authorization is not derived from its
  components' constraints.
- No one can state which human or service principal a given action was
  taken on behalf of.
- Authorization for agents is described as a separate, lighter story
  "because AI".

## What to do instead

**Authority does not imply execution. Execution does not imply
authority.** Privilege is a distinct concern from either, and ownership is
not itself a security boundary. See
[Major Principle 5](../01-principles/05-distribute-execution.md).

Agents act with a principal and under policy that the organization
already decided. They do not get a parallel, weaker authorization story.
Composition is valid only when the contracts, constraints, and relevant
authorities of contributing capabilities can coexist, and it must not
silently expand authority.

Record the intent an agent was given, not only the calls it made.

## Related

[Agents as capability consumers](../05-ai-native-engineering/agents-as-capability-consumers.md)
and [composite capabilities](../02-capabilities/composite-capabilities.md).
This repository does not replace identity, access management, or security
governance.
