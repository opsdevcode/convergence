# Organizational independence

**A capability is organizationally independent to the degree that
consumers can successfully discover and use it without understanding the
organizational structure responsible for its realization.**

This is a spectrum, not a binary.

It does **not** mean ownership disappears, teams disappear, humans
disappear, consumers can never contact owners, or organizational
boundaries are inherently bad.

> Ownership should be discoverable without being required for routing.

## Example

```mermaid
flowchart LR
  subgraph before["Sarah is the realization"]
    C1["Consumer"]:::actor --> Cap1["AssessNovelSecurityArchitecture"]:::cap
    Cap1 --> S["Sarah"]:::real
  end

  subgraph after["Alex is the realization"]
    C2["Consumer"]:::actor --> Cap2["AssessNovelSecurityArchitecture"]:::cap
    Cap2 --> A["Alex"]:::real
  end

  classDef actor fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
```

The consumer still depends on the capability, not on knowing Sarah. Fulfillment
is conceptual. It is not a required product.

See [Consumer to capability to realization](../../diagrams/consumer-capability-realization.md).
