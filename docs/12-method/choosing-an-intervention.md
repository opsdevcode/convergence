# Choosing an intervention

**Serves:** [Major Principle 2](../01-principles/02-design-the-engineering-system.md)
and the [design doctrine](../00-foundations/design-doctrine.md).

After [diagnose](README.md), pick the **smallest** change that could
improve the **engineering system** for this class of intent. This page is
a menu, not a required sequence.

The intervention is not automatically automation, platform work,
self-service, reorganization, documentation, or capability creation.

## Change nothing

Legitimate when the path already carries the right judgment and
controls, or when encoding would freeze unsettled knowledge, or when
the analyst does not understand the domain well enough to intervene.

Record the reason on the [application record](application-record.md) so
the next pass does not re-litigate from zero.

## Match the intervention to the system problem

| If the system problem is mainly… | Consider |
| --- | --- |
| Consumers cannot tell what the organization can already do | Clarify the existing capability (name, owner, constraints). See [Identifying capabilities](identifying-capabilities.md) |
| Discovery, translation, or a portal that files tickets | Improve **experience**; check that realization actually changes. See [Designing experience and realization](designing-experience-and-realization.md) |
| Fulfillment is the queue or an undocumented tribal path | Change **realization** (human fulfillment remains valid) |
| The same settled expertise is re-applied ticket by ticket | [Decide what to encode](deciding-what-to-encode.md) — form follows what varies |
| The work is novel or residual risk | Retain explicit specialist **collaboration**; do not automate the verdict |
| People lack the same facts | Clearer **information** (still may be a conversation) |
| Org-chart hops that decide nothing | Remove organizational routing; keep ownership discoverable |
| A real control delivered as a scavenger hunt | Redesign the **intentional** control into the path; do not delete it |
| Execution crossed a domain and permission got confused | Clarify authority vs execution; composition must not expand authority |
| Parts succeed and the whole fails | Change the composition seam, composite promise, or attribution |
| Nobody can see whether the path worked | Improve observation / evidence on the path |
| Owner is the route, or owner is invisible | Change ownership *expectations* (discoverable, not the ticket queue) |

Do not prescribe a platform. Do not create a Convergence team. Do not
treat automation as the mature form of a capability.

## Guardrails

- Domain authority stays with the domain. Composite ownership does not
  buy the parts. See [Composition](../03-architecture/composition.md).
- Encoded expertise remains challengeable. Specialists stay in the
  loop as owners of the encoding, not as a hidden queue.
- If the proposed fix is a catalog, IDP, or graph first, you are
  solving a documentation fantasy. Trace again.

## Depth

Experience and realization design, exception paths, and composition
guardrails: [Designing experience and realization](designing-experience-and-realization.md).

Anti-patterns that look like adoption:
[Anti-patterns](../08-anti-patterns/README.md).
