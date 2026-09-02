# Consumption

How consumers traverse the structure to get from intent to outcome.

The five consumer classes are named in
[agents as capability consumers](../05-ai-native-engineering/agents-as-capability-consumers.md).
This document covers the structural consequences of serving all of them
through one set of capabilities.

## One capability, many experiences

The plurality is architectural, not incidental. A single capability can
be consumed through a conversation, a declared file in a repository, a
command line, a portal, and an agent's tool description, without becoming
five capabilities.

The corollary is a counting error worth naming: **the number of
experiences is not the number of capabilities.** An organization with one
capability and four experiences has not built four things, and an
organization that ships a second portal has not added a capability.

## The consumption path

Every consumer traverses the same five steps, and each step has a
characteristic failure.

| Step | The consumer needs to | Fails when |
| --- | --- | --- |
| Discovery | Learn the ability exists | Finding it requires knowing who owns it |
| Eligibility | Learn whether this case qualifies, and what they will get | The answer arrives after they have committed effort |
| Expression | State intent at a level they can responsibly own | The interface demands realization decisions they do not own |
| Realization | Have the work happen | The path silently becomes a queue |
| Observation | Know the outcome, and act if it is wrong | Success is assumed and failure surfaces elsewhere |

Eligibility is the step most often missing. It is why
[policy at the edge](policy-attachment.md) exists as an attachment point:
without it, consumers discover constraints by failing.

## Consumers are not equal

They differ in judgment, in rights, and in what they can be told.

| Consumer | Needs from the structure | Must not receive |
| --- | --- | --- |
| Human | Explanation, an exception route, a way to reach a person | A path that only works with tribal knowledge |
| Product | Stable expectations, versioning, notice of change | Silent capability changes labelled as realization changes |
| Software system | Programmatic use with no hallway context | An interface that assumes a human will interpret it |
| Automation | Determinism and idempotency | Ambiguity it will resolve by guessing |
| Authorized agent | Parseable contracts, tight authorization, blast-radius limits, recorded intent | Authority derived from tool availability |

Serving all five does not require a second organization, a single
enterprise graph, or a separate agent platform. It requires that
[policy attach per consumer class](policy-attachment.md) over the same
capability.

## The exception path is part of consumption

An architecture that describes only the standard path has described the
part that works. Consumers meet cases the encoding does not fit, and
where they go next is a structural question.

If the structure has no answer, consumers supply one: a message to
someone they know, a manual change, an undocumented shortcut. That
improvised route then carries real traffic and is invisible. See
[explicit exception path](../07-patterns/explicit-exception-path.md).

## Abstraction is offered, not imposed

**Intent should be expressed at the highest level of abstraction the
consumer can responsibly own.**

**Abstraction should be available where it removes irrelevant
responsibility, not imposed where the consumer legitimately owns that
responsibility.**

Structurally this means a capability may expose more than one level of
expression, and that the higher one is not automatically preferred. A
team that genuinely owns its data placement decisions should not be forced
through an interface that decides placement for them.

Convergence seeks appropriate leverage, not maximum abstraction.

## At small scale

Discovery can be a handbook page. Eligibility can be a documented rule a
consumer reads before starting. Expression can be a short conversation
with a domain authority. Observation can be a channel the owner is in.

All five steps exist in a ten-person company. Only their realization
changes.
