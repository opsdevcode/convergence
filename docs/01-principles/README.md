# Principles

These documents are working doctrine for v0.1. Changing a Major Principle
requires an [RFC](../../rfcs/README.md).

This section is organized so Major Principles of Convergence are not mixed
with capability implementation guidance or architecture notes.

## How this section is organized

| Kind | Status |
| --- | --- |
| **Major Principles of Convergence** | Written through before listing. Expect roughly five to eight. No empty stubs. |
| **Capability-specific principles** | Stay with the capability mechanism. Not Major Principles. |
| **Architecture-specific principles** | None promoted yet. |

## Major Principles of Convergence

| # | Principle |
| --- | --- |
| 1 | [Specialization remains. Silos don't.](01-specialization-remains-silos-dont.md) |

---

## Working notes (not Major Principles)

The fragments below are leftover from the v0.1 outline. They have not been
developed as Major Principles. Do not treat them as equal to Principle 1.
They will be rewritten, merged, demoted, or dropped as later principles are
specified.

### Outcomes over outputs

**Statement:** Judge the engineering system by customer and business
outcomes, not by tickets closed or resources created.

**Explanation:** A provisioned cluster is an output. A customer completing a
workflow with agreed reliability and cost is an outcome. The customer
experiences one product, not the supply chain that produced it.

**Implications:** Local throughput metrics stay diagnostic, not defining.
Layer-oriented OKRs (portal tickets, account provisioning time) should not
be the scoreboard.

**Does not mean:** Ignore operational metrics, or stop counting deployments.

### Notes toward Converged Engineering practice

These concern how specialized disciplines work together. They are not
Major Principles yet.

#### Self-service is the default interface

This fragment predates Major Principle 1. It is **not** a Major Principle.
Principle 1 states that not every interaction must become self-service.

**Statement:** The normal way to use expertise is to invoke a governed
capability, not to open a request with the providing team.

**Explanation:** Self-service means API, CLI, workflow, or agent tool. It
does not mean an unguarded console.

**Implications:** If a common intent still requires a human in another team,
that is a backlog item for the provider unless the risk cannot be encoded
yet.

**Does not mean:** No human contact, no support, and no exceptions.

#### Governance is encoded, not appended

**Statement:** Policy, security, and compliance should be part of what is
invoked and enforced, not a separate phase that starts when the work is
otherwise done.

**Explanation:** Appended governance produces waiting and exception
culture. Encoded governance produces a smaller, explicit set of allowed
compositions.

**Implications:** Security and risk owners help specify contracts and
verification. They do not disappear in favor of "move fast."

**Does not mean:** Automated policy replaces all judgment.

#### Intent becomes the interface

**Statement:** Consumers should express what they are trying to achieve, at
the highest level they are qualified to specify, not the implementation
recipe of every underlying system and team.

**Explanation:** "Run this service in production for this team under the
standard path" is an intent. "Open these three tickets" is an
organizational API. Agents cannot navigate tribal process.

**Implications:** Interfaces should accept intent-shaped inputs and bind
them to policy.

**Does not mean:** Consumers never specify constraints. Region, data class,
and SLO class are often part of intent.

#### Ownership extends to outcomes

**Statement:** Owning a contribution to the engineering system includes
how it behaves on the path to customer outcomes, not only owning a backlog
of requests.

**Explanation:** If a capability or platform path is green in isolation and
red in the customer path, the provider is not done. Shared ownership with
product teams is expected.

**Implications:** Providers need telemetry from consumption. Product teams
need a clear contract so "shared ownership" is not infinite blame.

**Does not mean:** Specialists absorb product management, or product teams
absorb SRE.

### Notes toward capability-specific principles

These concern the capability mechanism. They are not Major Principles of
Convergence.

#### Capabilities over layers

**Statement:** Organize consumption around capabilities that fulfill
intents, not around technical layers that each require a handoff.

**Explanation:** Layers describe a stack. They are a poor API for getting
work done. Implementations may still be layered.

**Implications:** Discovery should list capabilities and intents, not only
team names that match OSI-ish layers.

**Does not mean:** Delete networking teams, or pretend layers are not real.

#### Expertise becomes capability

**Statement:** Specialized knowledge should be encoded into capabilities so
it can be reused, not only dispensed as one-off help.

**Explanation:** Tickets spend expertise once. Capabilities spend it
continuously. Encoding includes contracts, automation, policy, tests, and
usable documentation.

**Implications:** Remaining tickets for standard intents are signals of
missing or awkward capabilities.

**Does not mean:** Specialists stop doing incident response, design review,
or novel work. Novel work is how new capabilities are born. Not every
organizational problem is solved by adding a capability.

#### Capabilities are composable

**Statement:** Higher-level capabilities should be built from lower-level
ones through contracts, so consumers are not forced to reassemble the
organization on every change.

**Explanation:** `DeployApplication` may compose compute, networking,
identity, secrets, security, observability, deployment, and reliability.

**Implications:** Contracts need versioning. Breaking a lower capability
ripples.

**Does not mean:** Infinite abstraction, or hiding all failure modes.

#### Learning closes the loop

**Statement:** Outcomes, incidents, cost, and usage should change
capabilities, not only produce reports.

**Explanation:** Intent → Capability → Experience / Realization → Outcome
→ Learning. If production learning never changes the system, the loop is
fictional.

**Implications:** Time must be reserved to encode learning.

**Does not mean:** Every incident becomes a new abstraction.
