# Capability consumers

Different consumers. Same capability layer. Authorization may differ.
The graph should not.

```mermaid
flowchart TB
  subgraph consumers["Consumers"]
    direction LR
    Human["Human"]:::actor
    Product["Product"]:::actor
    Soft["Software"]:::actor
    Auto["Automation"]:::actor
    Agent["AI agent"]:::actor
  end

  Graph["Capability layer"]:::cap
  Systems["Underlying engineering systems<br/>realization"]:::real

  Human --> Graph
  Product --> Graph
  Soft --> Graph
  Auto --> Graph
  Agent --> Graph
  Graph --> Systems

  classDef actor fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
```

See [Agents as capability consumers](../docs/05-ai-native-engineering/agents-as-capability-consumers.md).
