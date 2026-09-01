# Roadmap

Versions are snapshots of the body of work, not product releases. Dates
are intentionally omitted. A version is ready when the documents in that
stage are coherent enough to criticize, not when they are finished forever.

## v0.1 - Foundations

Working definitions of Convergence and Converged Engineering, conceptual
model (intent, capability, experience, realization, outcome, learning),
problem statement, terminology, design doctrine, six Major Principles,
capability mechanism, and repository structure.

**Conceptual freeze:** treat this core as frozen unless a contradiction
is discovered. Do not add lifecycle stages, maturity levels, required
schemas, or prescribed implementations to "complete" v0.1. Park further
theory in [Open questions](docs/00-foundations/open-questions.md).

## v0.2 - Capabilities

Tighten the anatomy of a capability and the capability contract. Decide
which properties are required vs. optional at different scales. Improve the
`DeployApplication` example and add a second, dissimilar example (for
example, identity issuance or data access). Keep capabilities as a
mechanism, not as a second overarching discipline.

## v0.3 - Converged Operating Model

Complete the relationship to product, platform, SRE, infrastructure/cloud,
and security. Add networking, identity, data, and AI engineering if the
core framing holds. State what changes in planning, staffing, and funding
without prescribing an org chart or a Convergence team.

## v0.4 - Architecture

Develop conceptual converged architecture and the capability graph:
composition, policy attachment, telemetry, and consumption. Keep
implementation architecture (control planes, catalogs, runtimes) in a later
reference architecture, not here.

## v0.5 - AI-Native Consumption

Specify what an agent-facing contract needs that a human portal does not:
discovery, authorization, idempotency, blast-radius limits, and observation.
Stay within what current agents can actually do.

## v0.6 - Maturity Model

Describe stages of adoption that organizations can recognize. Avoid
certification language. Measure encoding of expertise and reduction of
handoff-as-API, not adoption of a branded platform or a new job family.

## v0.7 - Patterns and Anti-Patterns

Document recurring designs and failure modes. Promote only patterns that
have been argued in the open, not invented to fill a chapter.

## v0.8 - Reference Architecture

A vendor-neutral conceptual reference: discovery, composition, governance,
consumption, and learning. Explicitly non-normative for any product.

## v0.9 - Community Review

Invite structured critique from practitioners in SRE, platform, security,
infrastructure, and product engineering. Incorporate RFCs. Mark remaining
disputed claims.

## v1.0 - Initial Stable Body of Work

A version that organizations can cite without expecting the core
definitions to churn weekly. Stability means Convergence, Converged
Engineering, principles, and the capability model are settled enough to
version; it does not mean the ideas are complete or standard.

## Out of scope for this roadmap

- A website or docs generator
- A certification program
- A required implementation
- Dates and OKRs for this repository as a product
