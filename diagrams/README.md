# Diagram conventions

Canonical diagrams live in this directory. Do not invent a second layout
for the same idea in `docs/`. Link here, or paste the block unchanged.

## Rules

1. `flowchart TB` unless the page is a two-column comparison (`flowchart LR` with two subgraphs).
2. Stadium `([ ])` for Intent, Outcome, and Consumer.
3. Rectangle `[" "]` for Capability, Experience, Realization, Learning, and teams.
4. Class names: `intent`, `cap`, `exp`, `real`, `out`, `learn`, `team`.
5. Consumers use `intent`. Composed capabilities use `cap`. Org hops use `team`.
6. Always append the full classDef block below, including unused classes.
7. No personal names. Use roles (security architect, product engineer).

## classDef block

```
  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
```

| Class | Meaning |
| --- | --- |
| intent | Intent, consumer |
| cap | Capability |
| exp | Experience |
| real | Realization |
| out | Outcome |
| learn | Learning |
| team | Organizational hop |

## Files

| File | Idea |
| --- | --- |
| [core-conceptual-model.md](core-conceptual-model.md) | Canonical loop |
| [traditional-delivery-model.md](traditional-delivery-model.md) | Handoff supply chain |
| [converged-engineering-model.md](converged-engineering-model.md) | Specialties feeding capabilities |
| [consumer-capability-realization.md](consumer-capability-realization.md) | Capability vs team routing |
| [capability-consumers.md](capability-consumers.md) | Who consumes |
| [deploy-application-composition.md](deploy-application-composition.md) | Composite capability |
| [assess-novel-security-architecture.md](assess-novel-security-architecture.md) | Human-realized example |
| [method-cycle.md](method-cycle.md) | The work of design, not the system loop |
