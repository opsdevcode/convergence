# Deciding what to encode

**Serves:** [Major Principle 4](../01-principles/04-encode-what-is-repeatable.md).

**Method move:** 4. Intervene, **conditional** — only when repetition
suggests settled expertise. Domain experts decide whether knowledge is
understood enough to encode. See the
[initial application method](README.md).

> Encode what is repeatable. Collaborate on what is novel.

Repetition is a signal to **examine**, not a verdict that something
should be encoded. This document is the examination.

## Questions before encoding

| Question | If the answer is bad |
| --- | --- |
| Is the knowledge stable? | Encoding a moving target produces something wrong by the time it ships |
| Is the risk characterized? | You would be encoding a guess and giving it the authority of a system |
| Who keeps it current? | Without a named owner it becomes legacy on day one |
| What happens when it is wrong, and who notices? | Silent wrongness at scale is worse than a slow correct answer |
| Can it be challenged? | Encoded expertise that cannot be argued with stops improving |
| What will the specialist do with the reclaimed time? | If the answer is "more of the same queue", nothing was gained |

That last question is the point of the principle. Encoding exists to move
scarce judgment toward novel work, not to reduce headcount or to make a
dashboard improve.

## Encoding is broader than automation

These are forms, not levels. There is no ladder here and no direction of
travel implied by the order.

| Form | Fits when |
| --- | --- |
| Documentation | The knowledge is stable but judgment stays human |
| Standards | Many teams need the same answer, with room for context |
| Patterns | The shape recurs but the details vary |
| Policy | The rule must be stated and consistently applied |
| Decision guidance | The judgment is the variable part, not the action |
| Contracts | Expectations between consumer and provider need to be explicit |
| Workflows | Sequence and evidence matter |
| Libraries and modules | The action is mechanical and version-managed |
| Software and automation | The action is mechanical, frequent, and safe to repeat |
| AI context | An agent or assistant needs the same rules a person would read |

Automation is one entry in that table. Choosing it when the variable part
is judgment produces a tool that is confidently wrong.

## Match the form to what actually varies

Look at the interaction you are encoding and ask what changed between
instances.

| What varies | Encode |
| --- | --- |
| Nothing; the same action every time | The action |
| The inputs, within known bounds | The action, with the bounds as constraints |
| The judgment, from the same rules | The rules and the decision guidance, not the verdict |
| The judgment, from genuinely new facts | Nothing yet; this is still novel work |

## When not to encode

- The interaction is rare enough that a conversation is cheaper.
- The knowledge is still moving.
- Nobody will own the result.
- The risk has not been characterized, so there is no rule to state.
- The repetition is a symptom of something upstream, and encoding it
  would make the upstream problem permanent.

Deciding not to encode is a legitimate outcome and should be recorded
with its reason, so the next pass does not re-litigate it from scratch.

## Two encodings that look alike

| Increases leverage | Creates a new bottleneck |
| --- | --- |
| Consumers get an answer without the specialist in the loop | Consumers get a form that still ends in the specialist's queue |
| The specialist owns and improves the encoding | The specialist owns a tool nobody told them about |
| Exceptions are visible and rare | Exceptions are the majority and go around the encoding |
| The rule can be challenged and changed | The rule is frozen in a system nobody wants to touch |

If the right column describes what you built, the queue moved. It did not
shrink. See [Anti-patterns](../08-anti-patterns/README.md).

## Encoded expertise still needs living expertise

**Encoded expertise must remain challengeable.**
**Encoded expertise without living expertise eventually becomes legacy.**

Encoding is not a handover that ends the specialist's involvement. It
changes what the specialist spends attention on. Decay is covered in
[operating and evolving](operating-and-evolving.md).
