# Core conceptual model

Conceptual only. Not a runtime or control plane.

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
```

| Node | Meaning |
| --- | --- |
| Intent | Result the consumer is trying to cause |
| Capability | What the engineering system can accomplish |
| Experience | How the capability is consumed |
| Realization | How the capability is currently fulfilled |
| Outcome | Resulting state that advances intent |
| Learning | Evidence that changes the system |

See [Conceptual model](../docs/00-foundations/conceptual-model.md).
