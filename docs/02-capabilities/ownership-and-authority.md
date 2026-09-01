# Ownership and authority

Three distinct accountabilities. Shared contribution does not require
shared accountability.

| | Accountable for |
| --- | --- |
| **Domain authority** | What is correct within a specialized domain or decision scope |
| **Capability ownership** | Stewardship and continued fitness of a capability |
| **Outcome ownership** | The result closest to the intent being pursued |

Authority does not imply execution. Execution does not imply authority.
Ownership is not itself a security boundary. Privilege (what an actor is
technically permitted to do) is a separate concern and is not defined
here.

Accountability includes learning and evolution, not merely conformance.
See [Major Principle 5](../01-principles/05-distribute-execution.md).

```mermaid
flowchart TB
  Deploy["DeployApplication<br/>capability ownership"]:::cap
  Deploy --> Sec["Security domain authority"]:::real
  Deploy --> Id["Identity domain authority"]:::real
  Deploy --> Rel["Reliability domain authority"]:::real
  Deploy --> Net["Networking domain authority"]:::real
  Out["Product outcome ownership"]:::out
  Deploy -.-> Out

  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
```

This repository does not prescribe which team must own each layer.

> Ownership should be discoverable without being required for routing.

See [Organizational independence](organizational-independence.md).
