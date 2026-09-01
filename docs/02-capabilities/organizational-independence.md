# Organizational independence

**A capability is organizationally independent to the degree that
consumers can successfully discover and use it without understanding the
organizational structure responsible for its realization.**

This is a spectrum, not a binary.

It does **not** mean ownership disappears, teams disappear, humans
disappear, consumers can never contact owners, or organizational
boundaries are inherently bad.

Organizational independence must not imply organizational opacity.
Ownership, authority, provenance, operational responsibility, and
auditability may remain discoverable when they are not required for
routing.

> Ownership should be discoverable without being required for routing.

See [Major Principle 3](../01-principles/03-organization-is-an-implementation-detail.md).

## Example

```mermaid
flowchart LR
  subgraph before["Named architect is the realization"]
    C1["Consumer"]:::actor --> Cap1["AssessNovelSecurityArchitecture"]:::cap
    Cap1 --> S["Security architect"]:::real
  end

  subgraph after["Successor is the realization"]
    C2["Consumer"]:::actor --> Cap2["AssessNovelSecurityArchitecture"]:::cap
    Cap2 --> A["Successor architect"]:::real
  end

  classDef actor fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
```

The consumer still depends on the capability, not on knowing a particular
person. Fulfillment is conceptual. It is not a required product.

See [Consumer to capability to realization](../../diagrams/consumer-capability-realization.md).
