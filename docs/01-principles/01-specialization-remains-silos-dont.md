# Specialization remains. Silos don't.

**Major Principle 1 of Convergence** (working doctrine, v0.1)

Convergence preserves specialized engineering expertise while removing
specialization as a routine delivery boundary.

**Converged Engineering does not eliminate specialization. It eliminates
specialization as a delivery boundary.**

**Your organizational structure should not become your software delivery
API.**

## Specialization is not a silo

A **specialization** concentrates expertise. Complex systems require depth.
Infrastructure, security, reliability, networking, identity, data, product,
platform, and related domains retain their expertise, authority, and
ownership.

A **silo** restricts access to that expertise through organizational
boundaries so that the only practical way to use it is to go through the
people and process of that group, every time.

Convergence is not the convergence of expertise. It is the convergence of
**delivery**. Specialties stay. The routine path to an outcome should not
require assembling the org chart.

## Consume the expertise, not the expert

When expert knowledge becomes understood, repeatable, and predictable,
organizations should encode that knowledge into reusable mechanisms rather
than requiring the specialist to participate manually in every transaction.

Those mechanisms may include capabilities and contracts. They may also
include policies, automation, standards, tooling, and other engineering
interfaces. This principle does not require that every encoding be a
capability.

This does **not** mean experts are less valuable or should be removed from
engineering work. The opposite is intended: expert time is too valuable to
spend repeatedly solving problems the organization already knows how to
solve.

**Encode what is repeatable. Collaborate on what is novel.**

## Repeatable vs novel

**Repeatable** engineering interactions are those the organization already
understands: the intent is familiar, the risk is characterized, the
outcome is predictable enough to describe in a contract or standard.
Repeatability is a **signal** that expertise may be ready to become a
capability or another reusable mechanism. It is not an absolute rule. Not
every repeated interaction must become automated or self-service. Some
repetition is still cheaper or safer as a conversation.

**Novel** work remains collaborative: exceptions, unusual risk,
architectural decisions, and judgment that the encoding does not yet
cover. Specialists stay in that work. Encoding should make that work more
visible, not pretend it does not exist.

**Make exceptional work exceptional again.** Routine, understood work
should flow through reusable engineering mechanisms. Novel work should
flow through human collaboration.

## Organizational boundaries are not automatically silos

Convergence does not claim that every organizational boundary is bad.

Healthy boundaries may establish ownership, accountability, domain
authority, risk management, separation of concerns, and specialized
expertise. Teams can exist. Approvals can exist. Centralized expertise can
be the right design.

The problem occurs when **routine delivery** repeatedly requires engineers
to traverse those boundaries through tickets, queues, meetings, approvals,
Slack messages, email, or tribal knowledge.

**Boundaries can be healthy. Dependency on a boundary for routine
execution is what Convergence challenges.**

A silo, in this usage, is not "a team exists." It is "the team is the
interface for work the organization already knows how to do."

## Diagnostic

Does routine delivery require engineers to know which team owns the next
step?

A frequent yes is evidence that organizational structure may have become
part of the software delivery interface.

## Example: persistent relational storage

Intent: "My application needs persistent relational storage."

In a traditional supply chain, a product engineer may have to interact
separately with infrastructure or cloud, networking, identity, security,
database or data specialists, and observability or SRE. Each of those
groups may be highly competent. Competence is not the issue. The consumer
should not have to understand and traverse that structure to satisfy a
standard intent.

A database capability can encode appropriate expertise from those domains
behind a stable contract: allowed engines and sizes, network placement,
identity and encryption defaults, backup and observability expectations,
data-class policy. The product engineer consumes the contract. They do not
become a database administrator, a network engineer, or a security
engineer.

The capability does **not** replace those specialists. They retain domain
authority and responsibility for what the capability encodes. When a
request falls outside the supported contract (unusual topology, novel
risk, a data class the path does not cover), specialists become directly
involved. That is the novel path working as designed.

## Desired state

Specialists advance and govern their domains. Routine consumers benefit
from that expertise through stable engineering interfaces without needing
to understand the organizational structure behind them.

## What this principle does not mean

- Everyone becomes full-stack.
- Specialists disappear.
- Teams disappear.
- Product engineers must become infrastructure experts.
- Developers must become security experts.
- Every interaction must become self-service.
- Every engineering decision can be automated.
- Centralized expertise is inherently bad.
- Humans should never approve engineering decisions.
- Every organizational boundary is a silo.

## Relationship to capabilities

Capabilities are one primary way to encode repeatable expertise. This
Major Principle is about specialization and delivery, not about mandating
a catalog. Capability-specific guidance belongs under
[capabilities](../02-capabilities/README.md), not as a substitute for this
principle.
