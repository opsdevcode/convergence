# Conceptual model

This is a **conceptual** model of Converged Engineering. It is not a
mandatory runtime, control plane, catalog, portal, or graph database.

```
                            INTENT
                              |
                              v
                         CAPABILITY
                        /          \
                       /            \
                      v              v
                EXPERIENCE       REALIZATION
               how consumed      how fulfilled
                      \              /
                       \            /
                        v          v
                           OUTCOME
                              |
                              v
                           LEARNING
                              |
                              +-----------> feedback into the system
```

See [Core conceptual model](../../diagrams/core-conceptual-model.md).

| Concept | Question it answers |
| --- | --- |
| [Intent](../02-capabilities/intent.md) | What result is the consumer trying to cause, at a level they can own? |
| [Capability](../02-capabilities/capability.md) | What can the engineering system accomplish? |
| [Experience](../02-capabilities/experience.md) | How does a consumer discover, request, use, and observe it? |
| [Realization](../02-capabilities/realization.md) | How is it currently fulfilled? |
| [Outcome](../02-capabilities/output-and-outcome.md) | What resulting state satisfies or advances intent? |
| [Learning](../02-capabilities/learning.md) | What evidence should change the system? |

Related: [composite capabilities](../02-capabilities/composite-capabilities.md),
[contracts](../02-capabilities/capability-contract.md),
[capability graph](../02-capabilities/capability-graph.md),
[ownership](../02-capabilities/ownership-and-authority.md),
[organizational independence](../02-capabilities/organizational-independence.md),
[coordination and collaboration](../02-capabilities/coordination-and-collaboration.md).

Worked examples: [ProvideRelationalStorage and AssessNovelSecurityArchitecture](../02-capabilities/worked-examples.md).

## Distinctions that must not collapse

If something describes **what** the engineering system can accomplish, it
may be a capability.

If it describes **how a consumer interacts** with that ability, it belongs
to experience.

If it describes **how the organization fulfills** that ability, it belongs
to realization.

An output is something produced. An outcome is a resulting state that
satisfies or advances intent.

A capability can exist without a formal contract, without automation, and
without a dedicated platform. Encoding repeatable expertise changes
realization and leverage. It does not create the capability from nothing.

## What this model is not

It does not require Kubernetes, an IDP, a workflow engine, a service
catalog, or a graph database. A startup may realize capabilities with Git,
conventions, CI, IaC, docs, and conversation. A regulated enterprise may
add machine-readable contracts and audit. Both can practice Converged
Engineering.
