# Converged architecture

Converged Engineering's conceptual architecture is a loop, not a stack of
org functions the product team must climb.

Specialties remain distinct. They **contribute** to capabilities. They do
not merge into one role.

```text
Product, Platform, SRE, Infrastructure,
Cloud, Security, Networking, Identity,
Data, AI, … (expertise remains specialized)
        ↓
   Capabilities
        ↓
   Experiences
        ↓
    Outcomes
        ↓
    Learning
        ↺ (into capabilities)
```

See [Converged Engineering conceptual model](../../diagrams/converged-engineering-model.md).

## Expertise feeds capabilities; it is not a queue beside them

In the traditional model, specialist groups sit in a chain. In this model,
they invest in capabilities on the path from intent to outcome.

The underlying engineering systems (clusters, identity providers, pipelines,
policy engines, observability backends) remain. They are implementation.
Consumers should meet them through capabilities except when debugging or
doing novel work.

## Experiences are not the model

Portals, CLIs, and agent tools are experiences. If the experience is a form
that opens a ticket, the architecture has not changed. If it invokes a
contracted capability, it is doing its job.

A platform may host discovery and composition. It is not the architecture
by itself.

## Separate conceptual from implementation

| Conceptual | Implementation (out of scope here) |
| --- | --- |
| Capability graph | Service catalog, graph DB, Git repo of specs |
| Contract | OpenAPI, proto, policy-as-code, SLO docs |
| Encoded governance | Admission controllers, IAM, GRC tools |
| Feedback | Observability products, incident tooling |

Adopters will mix these. This repository should not pick winners in v0.1.
