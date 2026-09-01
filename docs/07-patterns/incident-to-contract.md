# Incident to contract

## Problem

An incident produces a thorough review, a list of action items, and a
document. Six months later the same class of failure recurs, and the
review is cited as evidence that the organization already knew.

Learning that changes nothing in the system is not learning. It is
documentation of regret.

## The pattern

Route the durable conclusion of an incident into the artifact that
governs the path, rather than into a report. Depending on what failed:

| What the incident revealed | Where the conclusion belongs |
| --- | --- |
| An assumption in how the path is fulfilled | Realization, plus a test that would have caught it |
| A promise consumers relied on that was never true | The contract, corrected |
| A constraint that was real but unstated | Policy, at the edge and in the node |
| A case the encoding does not cover | The exception path, or the contract boundary |
| A decision nobody had authority to make | Ownership, made explicit |

The test matters more than the document. A conclusion expressed as a
check that fails when the condition returns will outlive the people who
attended the review.

## When it applies

- The failure mode is likely to recur.
- The conclusion is stable enough to state.
- The path has an owner who can change it.

## What it costs

| Cost | Detail |
| --- | --- |
| Time after the fire | The work happens when attention has already moved on |
| Accumulation | Constraints added one incident at a time can ossify a path |
| Overcorrection | One dramatic failure can produce a rule that penalizes every future case |

Accumulation deserves attention. Every incident adds a constraint and
almost nothing removes one, so paths get more restrictive over time
without anyone deciding that they should.

## When not to use it

- The incident was genuinely novel and unlikely to recur. Not every
  incident should become an abstraction.
- The conclusion is still contested. Encoding a disputed lesson gives one
  side the authority of the system.

## Related

[Major Principle 6](../01-principles/06-close-the-loop.md) and
[operating and evolving](../12-method/operating-and-evolving.md). Learning
informs change; it does not automatically mandate change.
