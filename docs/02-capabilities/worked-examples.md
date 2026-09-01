# Worked examples

Two contrasting capabilities. Same conceptual model. One is often
technology-realized. One is often human-realized. Both are capabilities.

Recurring names: `ProvideRelationalStorage` · `DeployApplication` ·
`AssessNovelSecurityArchitecture` · `LaunchRegulatedAPI`

## ProvideRelationalStorage

```mermaid
flowchart LR
  I(["Intent"]):::intent --> C["Capability"]:::cap
  C --> E["Experience"]:::exp
  C --> R["Realization"]:::real
  E --> O(["Outcome"]):::out
  R --> O
  O --> L["Learning"]:::learn

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
```

| Facet | This example |
| --- | --- |
| Intent | Persistent relational storage the product engineer is eligible to use (not "open the DBA queue") |
| Capability | `ProvideRelationalStorage` |
| Experience | Handbook plus PR, API, portal, or conversation: size class, data class, environment |
| Realization | DBA by hand; Terraform plus cloud SQL; platform plus managed PostgreSQL; approval plus automation |
| Output | A database instance exists |
| Outcome | The application has usable, policy-fitting relational persistence |
| Learning | Repeated exceptions become policy; missing observability is added to realization |

The capability can outlast a change of realization. Contribution upward to
claim submission and cost is [traced, not owned](output-and-outcome.md).

## AssessNovelSecurityArchitecture

```mermaid
flowchart TB
  Intent(["Intent<br/>assess a design not shipped before"]):::intent
  Cap["AssessNovelSecurityArchitecture"]:::cap
  Exp["Request, collaborate, findings, exceptions"]:::exp
  Real["Sarah + standards + threat-modeling practice"]:::real
  Out(["Residual risk explicit enough to decide"]):::out

  Intent --> Cap
  Cap --> Exp
  Cap --> Real
  Exp --> Out
  Real --> Out

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
```

| Facet | This example |
| --- | --- |
| Intent | Security architecture assessment of a new design |
| Capability | The organization can satisfy that class of intent |
| Experience | Request, context, collaboration, findings, exceptions |
| Realization | Sarah (expertise), standards, practice. Fragile if only Sarah. Still a capability. |
| Output | Written assessment, meeting, findings list |
| Outcome | Design assessed; residual risk explicit for outcome owners |
| Learning | Repeated "novel" requests get encoded; Sarah returns to remaining novel work |

If Sarah is replaced by Alex, consumers still use the capability, not
Sarah's calendar. See
[Organizational independence](organizational-independence.md) and
[diagram](../../diagrams/assess-novel-security-architecture.md).

## DeployApplication and LaunchRegulatedAPI

`DeployApplication` composes workload, identity, connectivity, secrets,
observability, and reliability. `LaunchRegulatedAPI` additionally depends
on protecting sensitive data and exception-time human governance.

See [Composite capabilities](composite-capabilities.md) and
[Regulated enterprise](../11-adoption/regulated-enterprise.md).
