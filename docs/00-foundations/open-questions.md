# Open questions

These topics emerged from hostile testing of the v0.1 conceptual core.
They are **parked**, not solved. This list is not a backlog of frameworks
waiting to be built, and nothing here should be treated as a gap that
must be closed before the model is usable.

The v0.1 core (definitions, six Major Principles, design doctrine,
conceptual loop, capability mechanism) stays frozen unless a contradiction
is found.

Each topic now sits in one of three states.

| State | Meaning |
| --- | --- |
| Practice guidance exists | Applied guidance was written; the theory is still open |
| RFC candidate | Resolving it would change the conceptual core, so it needs an [RFC](../../rfcs/README.md) |
| Stays parked | Not enough practice yet to theorize without inventing |

## Practice guidance exists

The [method](../12-method/README.md) says something useful about these.
That is not the same as having resolved them.

| Topic | What practice says now | What is still open |
| --- | --- | --- |
| Reversibility | Ask two separate questions, consumer reversibility and organizational reversibility, before they are urgent. See [operating and evolving](../12-method/operating-and-evolving.md) | Whether reversibility can be characterized comparably across capabilities without becoming a rating |
| Deprecation and lifecycle semantics | Distinguish deprecating a contract version, splitting, merging, and retiring a capability. Retire when the class of intent is gone, not when its realization is inconvenient | Whether any of this belongs in a contract as required structure rather than as guidance |
| Long-term capability decay | Named decay signals, and name an owner at the time of encoding rather than after | How decay is detected before consumers feel it, and who is accountable when the owner has gone |
| Capability semantic drift | State the current meaning, correct the contract, split when two meanings have genuinely separated | How drift is detected at all, given that the name keeps working |
| Emergent composition risk | Three constraints: safety of parts does not imply safety of composition, composition must not silently expand authority, composition is valid only when contributing contracts and authorities can coexist. See [designing experience and realization](../12-method/designing-experience-and-realization.md) | How to evaluate composition safety without building dependency scoring or a systemic-risk algorithm |
| System-level stewardship | Stewardship should exist at the level where the concern exists. [Convergence as a function](../08-anti-patterns/convergence-as-a-function.md) describes the failure mode to avoid | The organizational implementation. No council, office, board, or role is prescribed, and this remains genuinely unsolved |

## RFC candidates

These would extend or change the conceptual core. An
[RFC](../../rfcs/README.md) is the right route, and none is required for
v0.1.

| Topic | What an RFC would have to establish |
| --- | --- |
| Evidence and evidence independence | What makes evidence independent, and whether the definition of [learning](../02-capabilities/learning.md) needs to distinguish classes of evidence. Must not become an evidence schema by default |
| Uncertainty representation | Whether uncertainty can be represented without a confidence schema or risk score. The current position is that abstraction must not manufacture false certainty, and that consequence and uncertainty are exposed in prose rather than rated |
| Knowledge provenance | Whether an encoding should carry where its knowledge came from, who last validated it, and against what. Closely tied to decay, and the cost of maintaining provenance may exceed its value |
| Trust across federation boundaries | What one engineering system can rely on from another, and what has to be verified rather than assumed. Federation is currently a boundary condition, not a trust protocol |

An RFC on any of these should say what breaks without it. Several of these
topics are more interesting than they are urgent.

## Stays parked

Theorizing on these now would produce vocabulary rather than
understanding. They need field evidence first.

| Topic | Why it waits |
| --- | --- |
| Consequence and blast radius | Named as concerns. Any general measurement system would be invented rather than observed |
| Concentration risk | Reuse creates leverage and concentration together. Knowing which paths carry the most traffic is currently the whole of the advice |
| Incentive compatibility | Acknowledged in the [operating model](../04-operating-model/README.md). Convergence requires incentive compatibility, not merely technical compatibility, but this repository does not prescribe budgeting, chargeback, compensation, or procurement models |
| Evolution over long organizational time | Learning creates evidence for evolution; it does not guarantee an organization acts on it. Nothing in a method fixes that |
| Recognizable maturity stages | Whether stages can be described at all without producing a scoring system. Current answer: the [dimensions](../06-maturity-model/README.md) must not be aggregated |

## What this list is not

- Not a roadmap. See the [roadmap](../../ROADMAP.md) for staged work.
- Not a set of required schemas, ratings, or scoring systems. Several
  entries exist specifically to record that a scoring system was
  considered and refused.
- Not a reason to delay practice. Every topic here can be left open while
  a real flow is traced and improved.
