# Consumer, capability, realization

Preferred conceptual path (left) versus organizational routing (right).

```mermaid
flowchart LR
  subgraph preferred["Depend on the capability"]
    C1["Consumer"] --> Cap["Capability"]
    Cap --> R["Realization\n(people, process, tech)"]
  end
```

```mermaid
flowchart LR
  subgraph routing["Org chart as delivery API"]
    C2["Consumer"] --> T1["Team"]
    T1 --> T2["Team"]
    T2 --> T3["Team"]
  end
```

Ownership stays discoverable. It should not be required for routine
routing. See
[Organizational independence](../docs/02-capabilities/organizational-independence.md).
