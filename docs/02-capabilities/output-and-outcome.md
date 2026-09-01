# Output and outcome

**An output is something produced. An outcome is a resulting state that
satisfies or advances intent.**

| | Output | Outcome |
| --- | --- | --- |
| Relational storage | Database instance exists | Application has usable, compliant, resilient persistence for the intent |
| Security assessment | A written report | Residual risk is explicit enough to decide |

Do not force every engineering capability to claim direct business
outcomes.

## Contribution upward (not a mandatory taxonomy)

> Own the outcome you can control. Trace the outcomes you contribute to.

```mermaid
flowchart TB
  C["Capability outcome<br/>ProvideRelationalStorage"]:::cap
  E["Engineering outcome<br/>Application persists claim state reliably"]:::real
  P["Product outcome"]:::exp
  Cu["Customer outcome<br/>Completes claim submission"]:::out
  B["Business outcome<br/>Fewer abandoned claims; lower processing cost"]:::intent
  C --> E --> P --> Cu --> B

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
```

The relational-storage capability contributes to broader outcomes. It
does not own the business result. That is
[outcome ownership](ownership-and-authority.md) at the right level.
