# Convergence

One product. Many specialties. One engineering system.

| | |
| --- | --- |
| Status | v0.1 conceptual core frozen. First versions of applied guidance are in the tree. |
| Stage | [v0.9 community review](ROADMAP.md). Invite structured critique; do not expand the frozen core. |
| Kind | **Emerging methodology** (not mature) for designing software delivery as a coherent engineering system rather than a sequence of organizational handoffs. Draws on established practices; not a product, standard, or new engineering discipline. |
| Company process | [OpsDevCode CONTRIBUTING](https://github.com/opsdevcode/.github/blob/main/CONTRIBUTING.md) (GitHub only; this repo is independently licensed CC BY 4.0) |

> Specialization remains. Silos don't.
>
> Convergence is not the convergence of expertise. It is the convergence of delivery.

## What this is

This repository is the working home of **Convergence**: an **emerging
methodology** for designing software delivery as a coherent
[engineering system](docs/00-foundations/converged-engineering.md) so that
specialized expertise participates through capabilities instead of through
tickets, queues, approvals, meetings, and other organizational routing.

The problem is not specialization. Specialists remain specialists. Human
judgment, domain authority, ownership, and accountability remain. What
should decrease is **unnecessary** coordination: treating the org chart as
the delivery API for **routine** intent.

> Converged Engineering does not eliminate specialization. It eliminates specialization as a delivery boundary.

It is **not** a finished or independently validated methodology. Application
guidance is early. Whether it proves practically valuable still requires use
and critique.

**Lineage (not the whole identity).** Individual ideas have substantial
[prior art](docs/00-foundations/prior-art.md). The work synthesizes
established practice from product, platform, reliability, operations,
systems, and organizational engineering. It does not claim those components
are inventions, and it does not replace Product Operating Model thinking,
Team Topologies, Platform Engineering, DORA, DevOps, SRE, Lean, or systems
engineering. No single named methodology has been identified that combines
these concerns in substantially the same way; a combination of those
practices can still reproduce many of the same designs.

It is a **lens and a developing method**, not a new specialty. Established
disciplines already reason well inside their own concerns. This work is for
designing **across** their boundaries—for example where product intent meets
specialist expertise, where a platform experience meets how work is actually
fulfilled, or where distributed execution meets domain authority.

## Who it is for

The **full** model is most useful to people who already reason across
specialties: architects, staff and principal engineers, platform and
infrastructure leaders, security and reliability leaders, and engineering
leadership.

Individual practitioners may use **one principle, one distinction, or one
diagnostic question** without adopting the whole vocabulary. Abstraction has
a cost; treating this as mandatory organizational doctrine for every
engineer is not the intent.

## Working definitions

| Term | Working definition |
| --- | --- |
| **Convergence** | A working name for an emerging methodology (not mature) for designing software delivery as a coherent engineering system rather than a sequence of organizational handoffs. Not an established industry movement. |
| **Converged Engineering** | A proposed design of that system: specialized expertise participates through capabilities so consumers of routine intent need not navigate the organizational structures behind them. |

These are working definitions, not established industry definitions.

Expertise remains specialized. Ownership remains explicit. Human judgment
remains essential. What converges is delivery.

> Converged Engineering does not eliminate specialization. It eliminates specialization as a delivery boundary.

It is not a new discipline, specialty, team, or job family.
**Convergence cannot be delegated to a Convergence function.**

## The problem

Specializations exist because complex systems require depth. They often
became the delivery architecture itself: a customer need is routed through
product, platform, SRE, infrastructure, networking, identity, security, and
related queues.

The customer experiences none of those boundaries. The customer experiences
one product.

The problem is not specialization. The problem is that specialization became
the architecture of software delivery.

See [The problem](docs/00-foundations/problem.md).

## Conceptual model

The reasoning **foundation** of the emerging methodology. Not a claim of
novel mechanics and not a mandatory runtime.

```mermaid
flowchart TB
  Intent(["Intent"]):::intent
  Cap["Capability"]:::cap
  Exp["Experience<br/>how consumed"]:::exp
  Real["Realization<br/>how fulfilled"]:::real
  Out(["Outcome"]):::out
  Learn["Learning"]:::learn

  Intent --> Cap
  Cap --> Exp
  Cap --> Real
  Exp --> Out
  Real --> Out
  Out --> Learn
  Learn -.->|feedback into the system| Cap

  classDef intent fill:#E8EEF6,stroke:#3D5A80,color:#1B2838
  classDef cap fill:#E4EFE7,stroke:#2F6F4E,color:#1B2838
  classDef exp fill:#F4EFE4,stroke:#8A6A2F,color:#1B2838
  classDef real fill:#EEE8F6,stroke:#5B4B8A,color:#1B2838
  classDef out fill:#F6E8EE,stroke:#8A4B63,color:#1B2838
  classDef learn fill:#EEF4E8,stroke:#5A7A3A,color:#1B2838
```

| | |
| --- | --- |
| Capability | What the engineering system can accomplish |
| Experience | How a consumer interacts with it |
| Realization | How the organization currently fulfills it |

Those three must stay distinct. A capability does not have to be an API, a
platform feature, or a formal contract. A human-realized security assessment
and an automated database path can both be capabilities.

See [Conceptual model](docs/00-foundations/conceptual-model.md).

> Your organizational structure should not become your software delivery API.
>
> Encode what is repeatable. Collaborate on what is novel.
>
> Convergence removes accidental complexity while preserving intentional constraint.
>
> Convergence seeks appropriate leverage, not maximum abstraction, automation, standardization, reuse, or self-service.

See [Design doctrine](docs/00-foundations/design-doctrine.md) and
[Major Principles](docs/01-principles/README.md).

Converged Engineering optimizes the engineering system's ability to move
intent to outcome, not the local efficiency of one function. That system
may be local or federated. Convergence does not require one homogeneous
enterprise implementation.

## What this is not

- Not a new engineering discipline or specialty
- Not a replacement for Product, Platform, SRE, security, infrastructure, or related practice
- Not "everyone is full stack"
- Not a rename of DevOps, Platform Engineering, or Team Topologies
- Not a finished, certified, or mandatory methodology
- Not a firm-wide operating model or mandated platform
- Not an IDP, service catalog, graph database, or agent framework
- Not vendor-owned; no product defines the model
- Not a requirement to buy or build "Convergence infrastructure"
- Not organizational consolidation
- Not measured by catalogs, automation percentage, or ticket volume
- Not an AI-specific model; AI does not require it

## Prior art (lineage, not the whole identity)

Component ideas come from established traditions. That is intellectual
honesty, not a claim that Convergence has no thesis of its own. Read
[Prior art and intellectual lineage](docs/00-foundations/prior-art.md)
for Conway, sociotechnical systems, DevOps, DORA, SRE, continuous delivery,
Lean, systems engineering, Team Topologies, Platform Engineering, product
operating-model thinking, and related work—what each established, how
Convergence relates, and how the name differs from other uses of
"convergence."

This repository once used "Capability Engineering" as a project name. That
work remains as the capability *mechanism*. The phrase also has prior uses in
systems engineering. See [Terminology](docs/00-foundations/terminology.md).

## Documentation

**Start here.** Frozen material is the thesis, principles, and conceptual
foundation. [Method](docs/12-method/README.md) is the **emerging
application**—early, not a second frozen core, not a transformation
program.

1. [The problem](docs/00-foundations/problem.md) — specialization is
   necessary; organizational routing as the delivery API is the target.
2. [Prior art](docs/00-foundations/prior-art.md) — what is already
   established; what this work does not claim to invent or replace.
3. [Design doctrine](docs/00-foundations/design-doctrine.md) — accidental
   vs intentional friction.
4. [Foundations](docs/00-foundations/README.md) and
   [Terminology](docs/00-foundations/terminology.md) — working definitions.
5. [The six Major Principles](docs/01-principles/README.md).
6. [Conceptual model](docs/00-foundations/conceptual-model.md) — intent,
   capability, experience, realization, outcome, learning.

Then [Capabilities](docs/02-capabilities/README.md) for mechanism detail,
and [Method](docs/12-method/README.md) to apply Convergence to one bounded
class of intent. You can use one
principle without the whole vocabulary.

If you came to disagree, read
[How to critique this](docs/00-foundations/how-to-critique.md) after that
path. It separates frozen claims from applied guidance and from questions
left parked on purpose.

Versions of this body of work are described in [ROADMAP.md](ROADMAP.md).
v0.1 through v0.8 now have documents coherent enough to criticize. v0.9
is review, not another chapter.

| Group | Section | Contents |
| --- | --- | --- |
| Frozen | [00 Foundations](docs/00-foundations/README.md) | Definitions, conceptual model, design doctrine, problem, terminology, prior art and lineage, open questions, how to critique |
| Frozen | [01 Principles](docs/01-principles/README.md) | Six Major Principles |
| Frozen | [02 Capabilities](docs/02-capabilities/README.md) | Intent, capability, experience, realization, contracts, graph |
| Applied | [03 Architecture](docs/03-architecture/README.md) | Composition, policy attachment, observation, consumption, graph, federation |
| Applied | [04 Operating model](docs/04-operating-model/README.md) | Per-discipline vignettes (not a new firm operating model) |
| Applied | [05 AI-native engineering](docs/05-ai-native-engineering/README.md) | Agents as consumers, agent-facing contracts, authorization |
| Applied | [06 Maturity](docs/06-maturity-model/README.md) | Optional spectra, not a program or score |
| Applied | [07 Patterns](docs/07-patterns/README.md) | Recurring designs, with their costs |
| Applied | [08 Anti-patterns](docs/08-anti-patterns/README.md) | Recurring failure modes |
| Applied | [09 Reference architecture](docs/09-reference-architecture/README.md) | Non-normative conceptual reference |
| Applied | [11 Adoption](docs/11-adoption/README.md) | Startup through brownfield sketches |
| Applied | [12 Method](docs/12-method/README.md) | Initial application method: five moves on one class of intent |
| Applied | [Diagrams](diagrams/README.md) | Conceptual diagrams |
| Later | [10 Implementations](docs/10-reference-implementations/README.md) | Placeholder. No implementation defines the model. |
| Process | [Roadmap](ROADMAP.md) | Snapshots v0.1–v1.0; current stage is v0.9 review |
| Process | [RFCs](rfcs/README.md) | Required for changes to the frozen core |

## Contribution

Editorial fixes and examples are welcome. Changes to Convergence, Converged
Engineering, principles, the conceptual model, terminology, or architecture
go through an [RFC](rfcs/README.md).

See [CONTRIBUTING.md](CONTRIBUTING.md), [GOVERNANCE.md](GOVERNANCE.md),
and [How to critique this](docs/00-foundations/how-to-critique.md).

## License

Documentation is licensed under [Creative Commons Attribution 4.0
International](LICENSE) (CC BY 4.0). If executable examples or code are added
later, they should use Apache License 2.0 unless a later decision says
otherwise.
