# Maturity characteristics

This section deliberately does not deliver a maturity model.

There are no levels, no scores, no percentages, and no certification. The
dimensions below are described so that two people can have a specific
conversation about a specific capability, and then decide whether
anything needs to change.

**Capability maturity is not automation maturity.** A human-realized
security assessment capability can be highly mature. A brittle scripted
path can be immature.

## Why there is no score

The moment these dimensions are summed, averaged, or turned into a level,
three things happen. Teams optimize the number. Capabilities that should
sit low on a dimension are recorded as deficient. And the score becomes
the thing reported upward instead of whether intent reaches outcome.

Convergence is not measured by capability counts, automation percentage,
self-service adoption, or ticket reduction. See
[design doctrine](../00-foundations/design-doctrine.md).

Use the dimensions independently. Do not aggregate them.

## The dimensions

Seven characteristics, each a spectrum. The columns describe what you
would observe, not what is good.

### Explicitness

| Less explicit | More explicit |
| --- | --- |
| The ability exists but is not named | The capability is named and its intent is stated |
| Consumers learn it exists by asking someone | Consumers can find it without knowing who owns it |
| Expectations live in individual memory | Expectations are written somewhere consumers read |

Generally worth increasing. Naming a capability is cheap and makes
fragility visible rather than ambient.

### Repeatability

| Less repeatable | More repeatable |
| --- | --- |
| Each fulfillment is assembled from scratch | Common cases follow a known path |
| Outcomes vary between instances | Outcomes are predictable within stated bounds |
| The person matters more than the process | The path survives a change of person |

High repeatability for genuinely novel work is not achievable and not the
goal. Repeatability is a **signal** to examine for reusable knowledge,
not a target. See
[Major Principle 4](../01-principles/04-encode-what-is-repeatable.md).

### Degree of human judgment

| Less human judgment | More human judgment |
| --- | --- |
| The decision follows stated rules | A person weighs the specific case |
| Novel cases are rejected or escalated | Novel cases are the normal work |

**This dimension has no better end.** It describes the capability's
nature, not its quality. `AssessNovelSecurityArchitecture` should sit
high here permanently. A capability that has drifted from high to low
without anyone deciding that the judgment became mechanical has a
problem, and so does the reverse.

### Organizational independence

| Less independent | More independent |
| --- | --- |
| Consumers must know which team owns the next step | Consumers use the capability without navigating structure |
| Routine intent traverses queues | Routine intent completes without organizational discovery |
| Owner identity is required for routing | Owner identity is discoverable but not required |

A spectrum, not a binary, and independence must never mean opacity. See
[organizational independence](../02-capabilities/organizational-independence.md).

### Composability

| Less composable | More composable |
| --- | --- |
| Usable only through its own front door | Can participate in a larger capability |
| Constraints are implicit, so composition is guesswork | Constraints are stated well enough to combine safely |

Higher is not automatically better. Composability that lets contradictory
constraints combine, or that lets composition expand authority, is worse
than a capability that refuses to compose. See
[composite capabilities](../02-capabilities/composite-capabilities.md).

### Governance

| Less encoded governance | More encoded governance |
| --- | --- |
| Policy is applied by review after the work is done | Policy is part of what is invoked |
| Compliance evidence is assembled retrospectively | Evidence is a property of the path |
| Exceptions are indistinguishable from normal cases | Exceptions are explicit, authorized, and recorded |

Governance moves into delivery rather than delivery moving through
governance. This does not mean policy replaces judgment.

### Observability

| Less observable | More observable |
| --- | --- |
| The owner learns about problems from complaints | Usage, failure, and exception evidence reaches the owner |
| Nobody knows whether consumers abandon the path | Abandonment and workarounds are visible |
| Cost and reliability behavior are unknown | Both are known well enough to act on |

The most valuable evidence is often qualitative, including a specialist
quietly doing manual work beside the encoded path. See
[operating and evolving](../12-method/operating-and-evolving.md).

## How to use this

Pick one capability. Describe where it sits on each dimension, in a
sentence each. Then ask a different question: **does it need to be
somewhere else?**

Appropriate position depends on risk, reuse, consequence, complexity, and
scale. A startup's `ProvideRelationalStorage` realized through a handbook
page and a Terraform module may be exactly where it should be. Convergence
seeks appropriate leverage, not maximum anything.

If the answer for every dimension of every capability is "higher", the
conversation has become a scoring exercise again.

## Related

[Capability characteristics](../02-capabilities/capability-characteristics.md)
lists the same dimensions in the capability mechanism.
[Automation as maturity](../08-anti-patterns/automation-as-maturity.md)
covers the failure mode this section exists to prevent.
