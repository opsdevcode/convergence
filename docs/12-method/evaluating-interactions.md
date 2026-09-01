# Evaluating interactions

**Serves:** the [design doctrine](../00-foundations/design-doctrine.md).

> Convergence removes accidental complexity while preserving intentional
> constraint.

Evaluation turns that sentence into a question you can ask about a line
in a [delivery trace](tracing-a-flow.md):

**What value does this interaction provide to the engineering system?**

## The answers are recognitions, not scores

Four answers recur. They are ways of describing what you found, not
categories to count.

| Recognition | What it looks like | Response |
| --- | --- | --- |
| Engineering or governance value | Independent authority, separation of duties, risk containment, regulatory obligation, genuine judgment | Preserve it, and design it deliberately |
| Duplicated interpretation | Several people re-deriving the same conclusion from the same rules | Encode the interpretation, keep the authority |
| Routing | Work spent discovering who owns the next step | Remove the discovery burden |
| Inherited process | A step no one can explain except historically | Ask the owner what breaks if it stops |

Do not turn this into a percentage of waste, a classification database,
or a scored inventory. The doctrine is a lens. A number derived from it
would be false precision, and it would immediately become a target.

## Slowness is not the test

A boundary or control is not accidental simply because it slows delivery.
Nor is a fast interaction automatically fine: a rubber-stamp approval
that takes four minutes and provides no independent judgment is still
inherited process wearing a control's clothes.

| Usually intentional | Usually accidental |
| --- | --- |
| Independent approval for a high-risk change to a regulated production system | Discovering which of five teams owns a routine provisioning request |
| A domain authority ruling on a data class that has not been ruled on before | A domain authority repeating a ruling they have already made forty times |
| Human judgment on a novel architecture | Re-entering the same context into a second team's intake form |
| A break-glass path with named authority and evidence | A path that only works if you know whom to message |

"Usually" is doing real work in that table. Context decides.

## The interaction whose value is real and whose shape is not

The most common finding is not a clean split. It is a control that
carries genuine value, implemented as organizational routing.

Data-class review is a real control. Requiring the consumer to discover
that it exists, find the reviewer, and re-explain the system is not part
of the control. The judgment is intentional. Its current delivery is
accidental.

Separating those two is most of the work. Preserve the judgment, the
authority, and the evidence. Remove the discovery, the translation, and
the queue.

## Who decides

Evaluation is contestable by design.

- A consumer's frustration is **evidence** about cost. It is not a ruling
  that a control is worthless.
- A domain authority's position is **authoritative** within their domain.
  It is not immune to the observation that the same answer has been given
  forty times.
- Neither party alone can declare an interaction accidental.

When the two disagree, that disagreement is a finding, not a deadlock to
resolve by escalation. Usually it means the control is intentional and
its realization is not, which is the case above.

## Re-evaluate

A judgment made once is not permanent. An interaction that was
intentional when the risk was uncharacterized may become duplicated
interpretation after the organization has answered the same question
enough times. That transition is exactly what
[deciding what to encode](deciding-what-to-encode.md) is about.

The reverse also happens. An encoded path can stop deserving trust when
the assumptions behind it change. See
[operating and evolving](operating-and-evolving.md).
