# Converged Engineering conceptual model

Specialized disciplines remain separate. They contribute expertise into
shared capabilities. Capabilities are consumed through experiences.
Experiences produce outcomes. Learning returns to capabilities.

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

  Caps["Shared capabilities"]
  Exp["Experiences"]
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
  Exp --> Out
  Out --> Learn
  Learn -->|"feeds back"| Caps
```

Contrast: [Traditional organizational delivery model](traditional-delivery-model.md).
