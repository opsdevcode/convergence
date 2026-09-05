# Method cycle

The work of designing the engineering system. This is **not** the
[conceptual model](core-conceptual-model.md). The conceptual model
describes how intent becomes outcome. This describes the deliberate work
of examining and changing that path. See the
[initial application method](../docs/12-method/README.md).

```mermaid
flowchart TB
  Scope["Scope<br/>class of intent, outcome, entry"]:::intent
  Trace["Trace<br/>what recent instances actually did"]:::exp
  Diag["Diagnose<br/>waits, accidental vs intentional"]:::exp
  Int["Intervene<br/>smallest change, including none"]:::real
  Obs["Observe<br/>wrong-success, evidence, learning"]:::learn

  Scope --> Trace
  Trace --> Diag
  Diag --> Int
  Int --> Obs
  Obs -.->|understanding changed| Scope
  Obs -.-> Trace
  Obs -.-> Diag
  Obs -.-> Int
  Diag -.->|not enough instances| Trace
  Int -.->|constraint still unclear| Diag

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
```

The order is a default, not a gate sequence. Observe may return to any
earlier move when evidence changes understanding. If there is nothing
useful to change or watch, **stop** — iteration is not mandatory.
Identify, encode, and design remain as **depth**, not required extra
stages.
