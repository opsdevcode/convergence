# AssessNovelSecurityArchitecture

Human-realized. Same loop as the [core model](core-conceptual-model.md).
Expertise sits in the security-architect role. The organization still
holds the capability.

```mermaid
flowchart TB
  Intent(["Intent"]):::intent
  Cap["Capability"]:::cap
  Exp["Experience<br/>how consumed"]:::exp
  Real["Realization<br/>how fulfilled"]:::real
  Out(["Outcome"]):::out
  Learn["Learning"]:::learn

  Intent --> Cap
  Cap --> Exp
  Cap --> Real
  Exp --> Out
  Real --> Out
  Out --> Learn
  Learn -.->|feedback into the system| Cap

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
```

| Node | This example |
| --- | --- |
| Intent | Assess a security architecture that has not shipped before |
| Capability | `AssessNovelSecurityArchitecture` |
| Experience | Request, collaborate, findings, exceptions |
| Realization | Security architect, standards, threat-modeling practice |
| Outcome | Residual risk explicit enough to decide |
| Learning | Repeated requests may be encoded; novel work stays with the architect |

See [Worked examples](../docs/02-capabilities/worked-examples.md).
