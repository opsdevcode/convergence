# Method cycle

The work of designing the engineering system. This is **not** the
[conceptual model](core-conceptual-model.md). The conceptual model
describes how intent becomes outcome. This describes the deliberate work
of examining and changing that path.

```mermaid
flowchart TB
  Trace["Trace<br/>how the intent reaches outcome today"]:::exp
  Eval["Evaluate<br/>what value each interaction provides"]:::exp
  Ident["Identify<br/>what the system can already accomplish"]:::cap
  Decide["Decide<br/>whether and how to encode"]:::cap
  Design["Design<br/>experience, realization, constraints"]:::real
  Operate["Operate<br/>learning, decay, evolution"]:::learn

  Trace --> Eval
  Eval --> Ident
  Ident --> Decide
  Decide --> Design
  Design --> Operate
  Operate -.->|better evidence, next pass| Trace

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
  classDef team fill:#F3F4F6,stroke:#6B7280,color:#111827
```

The order is a reading order, not a gate sequence. Real work moves
backward as often as forward.

See [Method](../docs/12-method/README.md).
