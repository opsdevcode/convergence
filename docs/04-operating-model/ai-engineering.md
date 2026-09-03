# AI engineering

AI and ML expertise remains. Building, training, serving, and evaluating
models is a discipline, and treating a model as if it were a deterministic
library is how it fails quietly.

## Scope note

This page is about the **AI engineering discipline**: the specialists who
build AI and ML systems, and how their expertise is consumed as
capabilities. It is not the same as
[AI-native engineering](../05-ai-native-engineering/README.md), which is
about AI agents **consuming** capabilities. Here, AI is the realization.
There, AI is the consumer.

## What does not disappear

- Model development, training, and fine-tuning
- Serving, inference, and evaluation
- Feature engineering and its data dependencies
- Model risk, drift, and monitoring
- The judgment about when a model is fit, and when it is not

## What changes

Model work should appear as **capabilities with contracts** rather than
notebooks handed over a wall to whoever operates them next.

| Was requested as | Becomes |
| --- | --- |
| A model handed off to another team to serve | A serving capability with a stated contract |
| Bespoke inference wiring per consumer | A capability consumers invoke without owning the model |
| "Ask the ML team to retrain" | Retraining and evaluation encoded, with owned exceptions |

## The thing AI engineering adds: honest uncertainty

A model is a **non-deterministic realization**. Its contract must not
present it as more certain than it is.

**Abstraction must not manufacture false certainty. Abstract complexity.
Expose consequence and uncertainty where they matter to responsible
action.** See the
[conceptual model](../00-foundations/conceptual-model.md).

A capability backed by a model should expose confidence, failure modes,
and the consequence of being wrong, rather than returning a clean answer
that hides its own uncertainty. Evaluation is not a launch gate that runs
once; it is part of how the capability is
[observed](../03-architecture/observation.md) and evolved. Model drift is
a decay signal like any other.

## What this is not

Not a claim that models replace specialists, and not "the model will catch
it" as a substitute for engineering. AI engineers own the failure modes of
what they build. Encoding multiplies their work; it does not remove the
judgment about fitness.
