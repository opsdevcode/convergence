# Converged architecture

A loop, not a stack of org functions to climb. Specialties remain
distinct. They contribute expertise into capabilities. They do not merge
into one role.

```mermaid
flowchart TB
  Intent(["Intent"]):::intent
  Cap["Capability"]:::cap
  Exp["Experience"]:::exp
  Real["Realization"]:::real
  Out(["Outcome"]):::out
  Learn["Learning"]:::learn

  Intent --> Cap
  Cap --> Exp
  Cap --> Real
  Exp --> Out
  Real --> Out
  Out --> Learn
  Learn -.->|back into the system| Cap

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
```

Product, Platform, SRE, Infrastructure, Cloud, Security, Networking,
Identity, Data, AI, and related expertise **feed** capabilities. In the
traditional model those groups sit in a chain. Here they are sources of
realization and domain authority, not a request ladder.

Clusters, identity providers, pipelines, and similar systems remain
implementation (realization). Portals and CLIs are experience. Neither
is the capability.

A platform may host discovery or compose realizations. It is not the
architecture by itself.

See [Conceptual model](../00-foundations/conceptual-model.md) and
[Capability graph](../02-capabilities/capability-graph.md).

Conceptual vs implementation (examples only, not requirements):

| Conceptual | Might be implemented as (optional) |
| --- | --- |
| Capability graph | Docs, spreadsheet, catalog, graph DB |
| Contract | Markdown, OpenAPI, policy-as-code |
| Experience | Conversation, CLI, portal, agent tools |
| Realization | People, IaC, managed services, hybrids |
