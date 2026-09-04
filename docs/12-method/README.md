# Method

This section is **optional applied guidance** for examining a delivery
flow. It is not the identity of the project, not a required methodology,
and not a second conceptual core.

Nothing here adds to the frozen reasoning model. Every activity serves an
existing [Major Principle](../01-principles/README.md) or the
[design doctrine](../00-foundations/design-doctrine.md), and each
document says which.

## Two loops that must not merge

The common misreading of this section is to treat it as a second
lifecycle competing with the conceptual model. It is not.

| | [Conceptual model](../00-foundations/conceptual-model.md) | This section |
| --- | --- | --- |
| Describes | The engineering system | The work of designing that system |
| Runs | Continuously, whenever intent moves toward outcome | When someone deliberately examines a flow |
| Status in v0.1 | Frozen | Applied guidance, expected to improve |
| Vocabulary | Intent, capability, experience, realization, outcome, learning | Trace, evaluate, identify, decide, design, operate |

The design cycle acts on the system. The system produces the evidence the
design cycle reads. See [Method cycle](../../diagrams/method-cycle.md).

## The activities

| Step | Question it answers | Document |
| --- | --- | --- |
| Trace | How does this intent reach an outcome today? | [Tracing a flow](tracing-a-flow.md) |
| Evaluate | What value does each interaction provide? | [Evaluating interactions](evaluating-interactions.md) |
| Identify | What can the system already accomplish? | [Identifying capabilities](identifying-capabilities.md) |
| Decide | Is this knowledge worth encoding, and in what form? | [Deciding what to encode](deciding-what-to-encode.md) |
| Design | How is it consumed, fulfilled, and constrained? | [Designing experience and realization](designing-experience-and-realization.md) |
| Operate | What changed, what decayed, what should evolve? | [Operating and evolving](operating-and-evolving.md) |

One flow is [worked end to end](worked-method-example.md).

The order is a reading order, not a gate sequence. Real work moves
backward as often as forward, and most flows are re-entered later with
better evidence.

## What this method is not

- Not a maturity model. There are no levels and no score.
- Not a transformation program with a target end state.
- Not a checklist that produces a certificate when complete.
- Not dependent on a platform, catalog, graph database, or tool purchase.
- Not a reason to reorganize. See
  [Major Principle 3](../01-principles/03-organization-is-an-implementation-detail.md).
- Not a mandate to encode or automate whatever it finds.

The method can conclude that a flow is already well designed and that the
right action is to leave it alone. That is a successful pass.

## It has to work small

A trace can be a page of notes. An evaluation can be a conversation
between a product engineer and a domain authority. An encoding can be a
paragraph in a handbook and one required check.

If the method only works with tooling, it has become the thing it is
supposed to remove. See [Startup](../11-adoption/startup.md).

## Where to start

Pick one recurring intent that people complain about and that someone is
willing to own the outcome of. Trace that. Do not start with a survey of
every flow in the organization.

[Brownfield adoption](../11-adoption/brownfield.md) sketches the same
starting point in eleven steps. This section is the long form.
