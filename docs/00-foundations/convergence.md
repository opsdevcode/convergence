# Convergence

**Working definition:** Convergence is a working name for an **emerging
methodology** for designing software delivery as a coherent engineering
system rather than as a sequence of organizational handoffs.

This is a proposed name and a proposed body of work, not an established
industry term, not a historical movement, not a mature methodology, and
not a new engineering discipline or specialty.

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

The customer still experiences one product. This work asks whether the
*engineering system* can look more like that product: many kinds of
expertise, fewer *accidental* delivery seams. Intentional boundaries remain
where they carry engineering or governance value.

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

Convergence is the hypothesis that these forces can collapse **accidental
delivery boundaries** while leaving **expertise** intact. It is not a claim
that existing disciplines failed, or that this framing is the only
response.

AI-assisted and agentic engineering can **expose the cost of implicit
engineering systems** (tribal routing, org-chart APIs). They do not create
the need for Convergence and do not prove it.

## Prior art

Convergence does not claim that its component ideas are new. It builds on
decades of work across DevOps, Site Reliability Engineering, Platform
Engineering, Team Topologies, continuous delivery, cloud computing,
infrastructure as code, sociotechnical systems, and related disciplines. It
also accepts Conway's Law rather than rediscovering the relationship between
organizational structure and system design.

The work **draws on** those traditions as lineage. It is **developing** an
integrated way to design the engineering system (capabilities, experience
and realization kept distinct, specialization preserved). That is not a
claim of originality of the parts, uniqueness of the whole, or that nobody
had connected similar ideas before.

For what each neighboring body of work established, how Convergence relates to
it, the comparison table, and sources, see
[Prior art and intellectual lineage](prior-art.md).

## Not to be confused with

"Convergence" and "converged" already carry unrelated meanings. Convergence
and Converged Engineering as used here are none of the following, and are not
affiliated with or derived from them:

- **Convergence Engineering** ([Sunnyday Technologies, 2026](https://doi.org/10.5281/zenodo.19863081)):
  a methodology for commissioning autonomous software, measured by a "time to
  silence" metric.
- **Convergent engineering** / convergent systems engineering: a
  transdisciplinary team-based research approach defined by the U.S. National
  Academies (2017).
- **Converged and hyperconverged infrastructure**: data-center product
  categories combining compute, storage, and network.
- **IT/OT convergence** and **network convergence**: the merging of
  information, operational, or communication technologies.

See [Terminology](terminology.md) and
[Prior art and intellectual lineage](prior-art.md#not-to-be-confused-with).

## What Convergence is not

- Not a merger of job families into one generic engineer.
- Not a mandate to dissolve SRE, security, or infrastructure groups.
- Not DevOps renamed. DevOps addressed the development/operations split.
  Convergence is complementary on other specialist boundaries; it does not
  supersede DevOps.
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
