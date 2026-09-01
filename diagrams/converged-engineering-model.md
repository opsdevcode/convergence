# Converged Engineering conceptual model

Specialized disciplines remain separate. They contribute expertise into
shared capabilities. Capabilities have experiences and realizations.
Outcomes produce learning that feeds the system.

This is not a merger into one generic engineering role.

```mermaid
flowchart TB
  subgraph specialties["Specialized expertise (roles remain)"]
    direction LR
    Product["Product"]
    Platform["Platform"]
    SRE["SRE"]
    Infra["Infrastructure / Cloud"]
    Sec["Security"]
    Net["Network / Identity"]
    DataAI["Data / AI"]
  end

  Caps["Capabilities"]
  Exp["Experience"]
  Real["Realization"]
  Out["Outcomes"]
  Learn["Learning"]

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
  Learn -->|"feeds back"| Caps
```

Contrast: [Traditional organizational delivery model](traditional-delivery-model.md).
