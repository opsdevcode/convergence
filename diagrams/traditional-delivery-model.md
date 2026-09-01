# Traditional organizational delivery

Handoffs, not a reporting line. The customer experiences one product.

```mermaid
flowchart TB
  Need(["Customer need"]):::out
  Product["Product"]:::team
  Platform["Platform / DevOps"]:::team
  SRE["SRE"]:::team
  Infra["Cloud / Infrastructure"]:::team
  Net["Network / Identity / Security"]:::team

  Need --> Product
  Product --> Platform
  Platform --> SRE
  SRE --> Infra
  Infra --> Net

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
```

Contrast: [Converged Engineering](converged-engineering-model.md).
Narrative: [The problem](../docs/00-foundations/problem.md).
