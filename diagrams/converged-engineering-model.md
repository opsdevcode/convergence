# Converged Engineering conceptual model

Specialties remain separate. They contribute into capabilities. They do
not merge into one role.

```mermaid
flowchart TB
  subgraph specialties["Specialized expertise remains"]
    direction LR
    Product["Product"]:::team
    Platform["Platform"]:::team
    SRE["SRE"]:::team
    Infra["Infra / Cloud"]:::team
    Sec["Security"]:::team
    Net["Network / Identity"]:::team
    DataAI["Data / AI"]:::team
  end

  Caps["Capabilities"]:::cap
  Exp["Experience"]:::exp
  Real["Realization"]:::real
  Out(["Outcomes"]):::out
  Learn["Learning"]:::learn

  Product --> Caps
  Platform --> Caps
  SRE --> Caps
  Infra --> Caps
  Sec --> Caps
  Net --> Caps
  DataAI --> Caps
  Caps --> Exp
  Caps --> Real
  Exp --> Out
  Real --> Out
  Out --> Learn
  Learn -.->|feeds back| Caps

  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
```

Contrast: [Traditional delivery](traditional-delivery-model.md).
