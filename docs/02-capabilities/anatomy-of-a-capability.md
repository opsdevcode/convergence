# Anatomy of a capability

Optional facets. Not a mandatory schema. A capability can exist with
little more than a recognized intent and some realization (including a
person).

Do not confuse the capability with its contract, experience, or
realization.

```mermaid
flowchart TB
  Cap["Capability<br/>what the system can accomplish"]:::cap
  Cap --> Intent["Class of intent served"]:::intent
  Cap --> Comp["Composition<br/>other capabilities, if any"]:::learn
  Cap --> Ctr["Contract, if explicit<br/>expectations and constraints"]:::exp
  Cap --> Exp["Experience<br/>how consumers interact"]:::exp
  Cap --> Real["Realization<br/>how it is currently fulfilled"]:::real
  Cap --> Out["Outcomes it can produce or contribute to"]:::out
  Cap --> Learn["Learning / feedback"]:::learn

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
```

Contract-related facets, when used, may include inputs, expected
outcomes, constraints, policies, eligibility, reliability, cost,
ownership, exceptions, and lifecycle. See
[Capability contract](capability-contract.md).

Rigor should match complexity, risk, reuse, and scale.

## DeployApplication

`DeployApplication` is a [composite](composite-capabilities.md)
capability. See
[DeployApplication composition](../../diagrams/deploy-application-composition.md)
and [Worked examples](worked-examples.md).
