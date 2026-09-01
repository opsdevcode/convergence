# Traditional organizational delivery model

Arrows are **potential organizational handoffs**, not a reporting line.
The customer does not experience those groups. The customer experiences
one product.

```mermaid
flowchart BT
  subgraph supply["Organizational supply chain"]
    direction BT
    Net["Network / Identity / Security"]:::team
    Cloud["Cloud / Infrastructure"]:::team
    SRE["SRE"]:::team
    Plat["Platform / DevOps"]:::team
    Product["Product Engineering"]:::team
    Net -->|"handoff"| Cloud
    Cloud -->|"handoff"| SRE
    SRE -->|"handoff"| Plat
    Plat -->|"handoff"| Product
  end
  Outcome(["Customer outcome<br/>one product"]):::out
  Product --> Outcome

  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
```

Contrast: [Converged Engineering](converged-engineering-model.md).
Narrative: [The problem](../docs/00-foundations/problem.md).
