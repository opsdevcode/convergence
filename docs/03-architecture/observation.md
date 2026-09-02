# Observation

The loop from [intent](../02-capabilities/intent.md) to
[outcome](../02-capabilities/output-and-outcome.md) only closes if
evidence produced by use reaches whoever can change the capability. That
requirement has structural consequences, which is what this document
covers.

What learning *is* belongs to [learning](../02-capabilities/learning.md).
What to do with evidence once it arrives belongs to
[operating and evolving](../12-method/operating-and-evolving.md).

## Learning attaches to the capability

Evidence is produced by instances. It has to accumulate somewhere that
outlives them, and the capability is the only element in the model with
that property. An incident review attaches to an incident. A capability
persists across incidents, consumers, and owners.

This is why naming an owner is an architectural requirement rather than a
courtesy. A capability with no owner has nowhere for evidence to land,
which means the loop is drawn in the diagram and broken in practice.

## What the structure has to make visible

| Evidence | Originates at | Needs to reach |
| --- | --- | --- |
| Usage and success | Realization | Capability owner |
| Failure and incidents | Realization | Capability owner and domain authority |
| Exceptions granted | Exception path | Capability owner, as contract evidence |
| Abandonment partway through | Experience | Capability owner |
| Constraints discovered too late | Experience | Whoever owns the edge policy |
| Composition failures | Composition edge | Composite owner, with attribution |
| Cost and reliability behavior | Realization | Capability owner |
| Security findings, audit, regulatory change | Outside the loop entirely | Domain authority, then capability owner |

The last row matters more than its position suggests. Some of the most
consequential evidence is not produced by the system at all. The
architecture has to have somewhere to put it.

## Attribution across composition edges

A consumer of a composite experiences the composite. When something
fails, the cause frequently sits in a contributor the consumer never
chose and should not have to reason about.

The structure therefore needs attribution that does not become exposure.

| Attribution the structure needs | Exposure the consumer does not need |
| --- | --- |
| Which contributor produced the failure | The contributor's internal implementation |
| Which owner can act on it | A routing path to that owner |
| Whether the composite or a part is at fault | Realization detail they cannot act on |

**Convergence abstracts routing, not accountability.** During an incident
that distinction is the whole point: the consumer should not have to
navigate the org chart, and the responder must be able to.

## Silence is not evidence of correctness

A capability that emits nothing is not observably healthy. It is
unobserved. This is worth stating because the absence of complaints is
routinely read as a signal, particularly for capabilities whose consumers
have quietly stopped using them.

Abandonment and workarounds are evidence, and both are invisible unless
the structure looks for them.

## Some evidence has no emitter

The most useful decay signal is a specialist quietly doing manual work
beside the encoded path. Nothing emits that. Neither does "consumers
disagree about what this capability guarantees", which is the leading
indicator of semantic drift.

An architecture that only accepts evidence with an emitter will miss the
failure modes that matter most. The honest conclusion is that observation
includes conversation, and that a channel where the owner is present is a
legitimate part of the structure at any scale.

## Evidence does not guarantee action

**Learning informs change; it does not automatically mandate change.**
**Learning creates evidence for evolution; it does not guarantee that an
organization will act on that evidence.**

What the architecture can do is make evidence explicit and attributable,
so that not acting is visible as a decision. It cannot make the decision.

## Not in scope here

- No required telemetry schema, metric set, or instrumentation standard.
- No evidence schema or confidence rating. Evidence independence and
  uncertainty representation are
  [open questions](../00-foundations/open-questions.md).
- No claim that quantitative signals are the measure of Convergence. See
  [Ticket count as the score](../08-anti-patterns/ticket-count-as-the-score.md).
