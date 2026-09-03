# Convergence

**Working definition:** Convergence is the evolution of software delivery
from an organization of engineering functions into an integrated
engineering system.

This is a proposed name for an observed pressure and a proposed framing,
not an established industry term and not a new engineering specialty.

Convergence is not the convergence of expertise. It is the convergence of
**delivery**.

The engineering system may use [capabilities](../02-capabilities/capability.md)
as a primary mechanism. Convergence is not identical to a capability
catalog. Staffing, funding, and process also shape whether delivery is an
org walk or a system.

## What is shifting

Modern software organizations divided engineering into Product, Platform,
SRE, Infrastructure, Cloud, Security, Networking, Identity, Data, AI, and
related functions. Those specialties continue to exist. Their expertise
remains valuable.

What is under pressure is **specialization as a delivery boundary**: the
habit of requiring an outcome to traverse tickets, queues, approvals, and
meetings that mirror the org chart.

The customer still experiences one product. Convergence is the claim that
the *engineering system* should look more like that product: many kinds of
expertise, fewer delivery seams.

A threat model is not a capacity plan. An SLO is not a product hypothesis.
Those kinds of work should contribute to shared capabilities and outcomes
instead of forming a supply chain the product must climb.

## Forces (none of these *is* Convergence)

Several developments make delivery-by-handoff less tenable:

Cloud abstraction, infrastructure as code, platform engineering and
developer platforms, self-service interfaces, policy as code,
observability, APIs and automation, AI-assisted and agentic engineering.

The same developments support two very different responses.

| Automating the supply chain | Convergence |
| --- | --- |
| The handoffs remain and get faster | The delivery boundary itself collapses |
| Each queue gets a better interface | Routine intent stops traversing queues |
| Expertise stays behind its counter | Expertise participates through capabilities |

Convergence is the hypothesis that these forces should collapse **delivery
boundaries** while leaving **expertise** intact.

**AI does not create the need for Convergence. It exposes the cost of not
having it.**

## Prior art

Convergence builds on ideas that already exist. It does not claim they are
new, and it does not treat any of them as equivalent to Convergence. The
differentiation is how they are integrated: delivery as a system,
capabilities as what the system can do, experience and realization kept
distinct, specialization preserved.

| Related work | What it contributes | Where Convergence differs |
| --- | --- | --- |
| [Conway's Law](https://martinfowler.com/bliki/ConwaysLaw.html) and the Inverse Conway Maneuver | Names the force: system structure mirrors communication structure | Convergence targets the delivery boundary directly, not only re-drawn team lines meant to shape architecture |
| [Team Topologies](https://teamtopologies.com/) (stream-aligned, platform, enabling, complicated-subsystem) | Reduces handoffs and cognitive load by organizing teams for flow | Restructures teams; Convergence leaves specialties intact and changes how their expertise is exposed and consumed |
| DevOps and SRE | Lowered the development/operations wall; reliability as engineering | Address one split; Convergence addresses the many specialist splits that remain after it |
| Platform Engineering, internal developer platforms, "platform as a product" | Self-service consumption of paved paths; a platform defined by how it is consumed | A platform may serve experience or realization; it is not the definition of Convergence, and a portal that routes the same tickets has not converged delivery |
| Intent-based and intent-driven engineering | Intent as a contract the system compiles into approved primitives | Overlaps with the intent-to-outcome loop; Convergence keeps experience and realization distinct and requires no registry product |
| "Engineering system" programs (for example Microsoft's One Engineering System) | Treats the engineering system itself as a product | Convergence is vendor-neutral and non-normative; no implementation defines it |
| AI platform engineering: agents as platform consumers on governed golden paths | Agents consume the same governed paths as humans | Convergence treats agents as consumers that expose the cost of tribal routing; they do not create the need |
| Sociotechnical systems, domain-driven design, continuous delivery, infrastructure as code, policy as code, developer experience | Foundational practices Convergence assumes | Convergence composes them into a delivery-as-system frame rather than restating any one |

This list is not complete and is not an endorsement of any framework as
equivalent to Convergence.

## Not to be confused with

"Convergence" and "converged" already carry unrelated meanings. Convergence
and Converged Engineering as used here are none of the following:

- **Convergence Engineering** ([Sunnyday Technologies, 2026](https://doi.org/10.5281/zenodo.19863081))
  is a published methodology for commissioning autonomous software, measured
  by a "time to silence" metric. Unrelated to this work despite the similar
  name.
- **Converged and hyperconverged infrastructure** are data-center product
  categories that combine compute, storage, and network in one system.
- **IT/OT convergence** and **network convergence** describe the merging of
  information, operational, or communication technologies.

See [Terminology](terminology.md).

## What Convergence is not

- Not a merger of job families into one generic engineer.
- Not a mandate to dissolve SRE, security, or infrastructure groups.
- Not DevOps renamed. DevOps addressed the development/operations split.
  Convergence is about the many specialist splits that remain after that
  wall is lowered.
- Not Platform Engineering 2.0, an IDP architecture, a service catalog, a
  graph database, an agent framework, or a reorg methodology.
- Not something you staff by hiring a Convergence team.
- Not organizational consolidation: eliminating Platform, SRE, or
  Security; collapsing specialists into Product; universal full-stack
  teams; one mandated platform or implementation.
- Not a VP, office, or "Convergence Engineering" function that becomes
  the routing layer.

**Convergence cannot be delegated to a Convergence function.** A
transformation effort may have stewardship. Converged Engineering is a
property of the engineering system, not another delivery specialty.

See [Converged Engineering](converged-engineering.md) and
[The problem](problem.md).
