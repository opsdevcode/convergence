# Convergence

One product. Many specialties. One engineering system.

**Status:** Early Draft / v0.1

This repository is a working body of knowledge about an emerging software
engineering model. It is not a product, a vendor specification, or an
industry standard. The problem it names is real. The model it sketches is
under development.

**Specialization remains. Silos don't.**

Convergence is not the convergence of expertise. It is the convergence of
delivery.

## Working definitions

**Convergence** is the evolution of software delivery from an organization
of engineering functions into an integrated engineering system.

**Converged Engineering** designs that system so specialized expertise can
participate in delivery through capabilities without requiring consumers to
navigate the organizational structures behind them.

These are working definitions, not established industry definitions.

Expertise remains specialized. Ownership remains explicit. Human judgment
remains essential. What converges is delivery.

**Converged Engineering does not eliminate specialization. It eliminates
specialization as a delivery boundary.**

It is not a new specialty, team, or job family. Creating a "Convergence
Engineering" silo would recreate the problem.

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

A conceptual loop, not a mandatory runtime:

```
                    INTENT
                      |
                      v
                 CAPABILITY
                /          \
               v            v
         EXPERIENCE    REALIZATION
         how consumed  how fulfilled
                \          /
                 v        v
                   OUTCOME
                      |
                      v
                   LEARNING
                      |
                      +-----> feedback into the system
```

A capability is what the engineering system can accomplish. Experience is
how a consumer interacts with it. Realization is how the organization
currently fulfills it. Those three must stay distinct.

A capability does not have to be an API, a platform feature, or a formal
contract. A human-realized security assessment and an automated database
path can both be capabilities.

See [Conceptual model](docs/00-foundations/conceptual-model.md).

**Your organizational structure should not become your software delivery
API.**

**Encode what is repeatable. Collaborate on what is novel.**

Converged Engineering optimizes the engineering system's ability to move
intent to outcome, not the local efficiency of one function.

## What this is not

- Not the elimination of SRE, infrastructure, security, platform, or product
  engineering.
- Not "everyone is full stack."
- Not a rename of DevOps or Platform Engineering.
- Not an IDP, service catalog, graph database, or agent framework.
- Not vendor-owned. No product defines the model.
- Not a requirement to buy or build "Convergence infrastructure."

This repository once used "Capability Engineering" as the name of the
discipline. That work remains as the capability *mechanism*. The phrase also
has prior uses in systems engineering. See
[Terminology](docs/00-foundations/terminology.md).

## Documentation

| Section | Contents |
| --- | --- |
| [00 Foundations](docs/00-foundations/README.md) | Definitions, conceptual model, problem, terminology |
| [01 Principles](docs/01-principles/README.md) | Major Principle 1; working notes |
| [02 Capabilities](docs/02-capabilities/README.md) | Mechanism: intent, capability, experience, realization, contracts, graph |
| [03 Architecture](docs/03-architecture/README.md) | Conceptual architecture |
| [04 Operating model](docs/04-operating-model/README.md) | How existing disciplines change and what remains |
| [05 AI-native engineering](docs/05-ai-native-engineering/README.md) | Agents as consumers; AI does not create the need |
| [06 Maturity model](docs/06-maturity-model/README.md) | Characteristics, not automation scores |
| [07 Patterns](docs/07-patterns/README.md) | Placeholder |
| [08 Anti-patterns](docs/08-anti-patterns/README.md) | Placeholder |
| [09 Reference architecture](docs/09-reference-architecture/README.md) | Placeholder |
| [10 Reference implementations](docs/10-reference-implementations/README.md) | Non-canonical examples |
| [11 Adoption](docs/11-adoption/README.md) | Illustrative contexts; not prescribed orgs |
| [Diagrams](diagrams/README.md) | Conceptual diagrams |
| [RFCs](rfcs/README.md) | Process for conceptual change |

## Contribution

Editorial fixes and examples are welcome. Changes to Convergence, Converged
Engineering, principles, the conceptual model, terminology, or architecture
go through an [RFC](rfcs/README.md).

See [CONTRIBUTING.md](CONTRIBUTING.md) and [GOVERNANCE.md](GOVERNANCE.md).

## License

Documentation is licensed under [Creative Commons Attribution 4.0
International](LICENSE) (CC BY 4.0). If executable examples or code are added
later, they should use Apache License 2.0 unless a later decision says
otherwise.
