# Convergence

**Working definition:** Convergence is the shift from software delivery
through organizational boundaries toward an engineering system in which
specialized disciplines contribute to shared capabilities and outcomes.

This is a proposed name for an observed pressure on software organizations,
not an established industry term and not a new engineering specialty.

The definition mentions capabilities because this repository develops that
mechanism in detail. Convergence as a *shift* could, in principle, include
other ways of collapsing delivery boundaries (staffing, funding, process).
Do not read the definition as "Convergence equals a capability catalog."

## What is shifting

Modern software organizations divided engineering into Product, Platform,
SRE, Infrastructure, Cloud, Security, Networking, Identity, Data, AI, and
related functions. Those specialties continue to exist. Their expertise
remains valuable.

What is under pressure is **specialization as a delivery boundary**: the
habit of requiring a customer outcome to traverse tickets, queues,
approvals, and meetings that mirror the org chart.

The customer still experiences one product. Convergence is the claim that
the *engineering system* should look more like that product: many kinds of
expertise, fewer delivery seams.

Convergence does **not** mean the disciplines are becoming identical. A
threat model is not a capacity plan. An SLO is not a product hypothesis.
The claim is that those kinds of work should contribute to shared
capabilities and shared outcomes instead of forming a supply chain the
product must climb.

## Forces

Several technical and organizational developments make delivery-by-handoff
less tenable. None of them "is" Convergence by itself.

**Cloud abstraction** moved a large amount of substrate behind APIs. Teams
can still wrap those APIs in a request process. The existence of the API
makes an organizational queue a choice, not a physics.

**Infrastructure as code** made change reviewable and repeatable. It also
made it easy to copy the same ticket-shaped workflow into Git.

**Platform engineering and developer platforms** productized internal
paths. They reduce undifferentiated work. They also fail when the platform
is a nicer front door to the same specialist queues.

**Self-service** (when it is a real interface, not a form that opens a
ticket) is how encoded expertise is consumed.

**Policy as code** makes governance executable. That is a prerequisite for
removing appended approval as the main control, not a guarantee that anyone
did so.

**Observability** makes production a shared fact rather than a tribal
story. Feedback can close a loop only if someone encodes it.

**APIs and automation** are how software systems consume other systems. If
the only API is a team, automation stops at the org chart.

**AI-assisted engineering and agentic systems** make the same failure
obvious: an agent should not need to know which team owns networking, who
approves identity, which Slack channel owns Kubernetes, or which queue
provisions databases. Agents need authorized capabilities. Humans already
needed that; agents do not forgive the absence.

These forces can be used to *automate a supply chain*. Convergence is the
hypothesis that they should instead collapse **delivery boundaries** while
leaving **expertise** intact.

## What Convergence is not

- Not a merger of job families into one generic engineer.
- Not a mandate to dissolve SRE, security, or infrastructure groups.
- Not DevOps renamed. DevOps addressed the development/operations split.
  Convergence is about the many specialist splits that remain after that
  wall is lowered, including platform, security, identity, and
  infrastructure as request APIs.
- Not something you staff by hiring a Convergence team.

## Relationship to the rest of this repository

**Converged Engineering** is the proposed model for *how* to operate during
this shift. **Capabilities** are a primary mechanism that model uses.
Other mechanisms (culture, staffing, funding, product process) matter and
are not fully specified here.

See [Converged Engineering](converged-engineering.md) and
[The problem](problem.md).
