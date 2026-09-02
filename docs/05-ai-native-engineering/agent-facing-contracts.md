# Agent-facing contracts

An agent is a [capability consumer](agents-as-capability-consumers.md). It
consumes the same capabilities as everyone else. What differs is the
[experience](../02-capabilities/experience.md), and the difference is not
cosmetic: an agent cannot recover the context a human supplies without
noticing.

This document specifies what an agent-facing experience needs that a human
portal can leave unstated. It defines no schema, protocol, or format. The
requirement is that certain things be explicit, not that they take a
particular shape.

## What a human portal is allowed to leave implicit

A human portal works partly because a human is standing in front of it,
supplying judgment the interface never states.

| A human supplies for free | An agent cannot |
| --- | --- |
| Reads a label and infers the rest | Infer reliably; it acts on what is stated |
| Asks in a channel when unsure | Route around a gap; it guesses or fails |
| Notices "that looks wrong" and stops | Feel that something is off |
| Remembers why they did it | Reconstruct intent from a call log later |
| Knows who to escalate to | Find a person unless one is named |

Every row is a piece of the delivery path a human carries silently. An
agent-facing contract is largely the work of writing those rows down.

## The five things an agent contract must make explicit

The roadmap names five. Each is something a human portal can imply and an
agent contract cannot.

### Discovery

The agent must be able to answer, for its principal: which capabilities
exist, and which am I permitted to use? Discovery is scoped to the
principal, not to the catalog. An agent that can enumerate capabilities it
may not use has been handed a map with no boundaries.

Discovery that resolves to "search the wiki" is not discovery. It is the
[search problem](agents-as-capability-consumers.md) a human tolerates and
an agent cannot.

### A parseable contract

The [contract](../02-capabilities/capability-contract.md) must state, in a
form the agent can read: what inputs are required, what the capability
will do, what it will **not** do, and what it guarantees. The negative
space matters more for agents than for humans, because a human infers the
boundary and an agent tests it.

A natural-language handbook can sit beside the contract. It does not
replace it.

### Idempotency

The agent must be able to retry without compounding effects. Whether by
idempotency key, declared desired state, or a safe re-run semantics, the
contract has to say what happens on repeat. A human retries carefully; an
agent retries on a timer.

### Blast-radius limits

The contract must make the scope of an action explicit and bounded: what
it can touch, at what rate, in which environment. A human estimates blast
radius from experience. An agent has none, so the bound has to be stated
and enforced in [realization](../02-capabilities/realization.md), not
assumed.

### Observation

The outcome must be observable to the agent and to a human reviewing
later, including the **intent the agent was given**. A call sequence
recovered from logs does not explain why. Recorded intent does. See
[Observation](../03-architecture/observation.md).

## The thing the roadmap does not list: escalation

A sixth need falls out of the other five. Every agent will meet a case its
contract does not cover. Without a defined path, it does what an
undirected human does, except worse: it improvises against a boundary it
cannot see.

The contract needs a stated answer for "outside my contract," and for an
agent that answer is usually to stop and hand back to a principal, not to
push through. This is the
[explicit exception path](../07-patterns/explicit-exception-path.md)
applied to a consumer that cannot judge when to invoke it.

## What this is not

- Not a required schema, contract language, or protocol. Proportional
  formalism still applies: a low-risk internal capability may need very
  little.
- Not a claim that agents need a separate capability graph. They consume
  the [same conceptual set](agents-as-capability-consumers.md) through a
  different experience.
- Not a lighter authorization story. What the agent may do is covered in
  [Authorization and principals](authorization-and-principals.md), and
  invocation is not authority.
- Not a promise that a good contract makes an agent safe. It makes the
  agent's exposure explicit, which is what turns the debate into one about
  contracts rather than about who pasted a token into a chat tool.
