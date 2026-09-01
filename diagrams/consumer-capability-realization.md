# Consumer, capability, realization

Same consumer, two interfaces. Ownership stays discoverable. It should
not be required for routine routing.

```mermaid
flowchart TB
  subgraph good["Depend on the capability"]
    direction LR
    C1["Consumer"]:::actor --> Cap["Capability"]:::cap
    Cap --> R["Realization<br/>people, process, technology"]:::real
  end

  subgraph bad["Org chart as delivery API"]
    direction LR
    C2["Consumer"]:::actor --> T1["Team"]:::team
    T1 -->|"ticket / queue"| T2["Team"]:::team
    T2 -->|"ticket / queue"| T3["Team"]:::team
  end

  classDef actor fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
```

See [Organizational independence](../docs/02-capabilities/organizational-independence.md).
