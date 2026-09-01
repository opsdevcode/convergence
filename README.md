# Convergence

One product. Many specialties. One engineering system.

**Status:** Early Draft / v0.1

This repository is a working body of knowledge about a proposed engineering
model. It is not a product, a vendor specification, or an industry standard.
The problem it names is real. The solution it sketches is a hypothesis under
development.

**Specialization remains. Silos don't.**

## Hierarchy

| Term | Role in this body of work |
| --- | --- |
| **Convergence** | The broader shift: delivery through organizational boundaries gives way to shared capabilities and outcomes. |
| **Converged Engineering** | A proposed engineering model for operating in that shift. Specialties contribute expertise without using the specialty as the delivery API. |
| **Capabilities** | A primary technical mechanism of that model: reusable, contracted expressions of expertise. Not claimed to be the only possible mechanism. |

Working definition of **Convergence:**

> Convergence is the shift from software delivery through organizational
> boundaries toward an engineering system in which specialized disciplines
> contribute to shared capabilities and outcomes.

Working definition of **Converged Engineering:**

> Converged Engineering is an engineering model in which specialized
> disciplines contribute expertise through shared, reusable, governed
> capabilities and share responsibility for the outcomes those capabilities
> enable.

These are working definitions, not established industry definitions.

**Converged Engineering does not eliminate specialization. It eliminates
specialization as a delivery boundary.**

It is not a new specialty, team, or job family. A platform engineer, SRE,
infrastructure engineer, product engineer, or security engineer can practice
it. Creating a "Convergence Engineering" silo would recreate the problem.

## The problem

Software engineering specialized for good reasons. Product, platform, SRE,
infrastructure, cloud, networking, identity, security, data, AI, and related
functions each hold real expertise.

Those specializations often became the delivery architecture itself. A
customer need is decomposed into an organizational supply chain:

customer need → product → platform → SRE → infrastructure → networking →
identity → security → …

The customer experiences none of those boundaries. The customer experiences
one product.

The problem is not specialization. The problem is that specialization became
the architecture of software delivery.

See [The problem](docs/00-foundations/problem.md).

## Capabilities

Expertise should be encoded into capabilities, not institutionalized as
handoffs. A capability is a reusable expression of engineering expertise
that exposes a defined contract and can be consumed or composed without
requiring the consumer to navigate the organizational structure that
produced it.

Lifecycle (a loop, not a linear pipeline):

```
Intent → Capability → Experience → Outcome → Learning
```

Learning feeds back into capabilities.

Consumers include humans, products, software systems, automation, AI agents,
and other capabilities.

Your organizational structure should not become your software delivery API.
The developer is not the platform team's customer. The developer is part of
the product value chain.

See [Capabilities](docs/02-capabilities/README.md).

## What this is not

- Not the elimination of SRE, infrastructure, security, platform, or product
  engineering.
- Not "everyone is full stack."
- Not a rename of DevOps or Platform Engineering. Those remain neighboring
  practices. Converged Engineering is about how *all* of them expose and
  consume expertise.
- Not vendor-owned. No product defines the model. See
  [Reference implementations](docs/10-reference-implementations/README.md).
- Not a claim that capabilities solve every organizational problem.

This repository once framed "Capability Engineering" as the name of the
discipline. That work is preserved as the capability mechanism. The phrase
also has prior uses in systems engineering; this project did not invent the
words. See [Terminology](docs/00-foundations/terminology.md).

## Documentation

| Section | Contents |
| --- | --- |
| [00 Foundations](docs/00-foundations/README.md) | Convergence, Converged Engineering, problem, terminology |
| [01 Principles](docs/01-principles/README.md) | Principles grouped by Convergence, Converged Engineering, and capabilities |
| [02 Capabilities](docs/02-capabilities/README.md) | Model, anatomy, contract, graph |
| [03 Architecture](docs/03-architecture/README.md) | Conceptual converged architecture |
| [04 Operating model](docs/04-operating-model/README.md) | How existing disciplines change and what remains |
| [05 AI-native engineering](docs/05-ai-native-engineering/README.md) | Agents as capability consumers |
| [06 Maturity model](docs/06-maturity-model/README.md) | Draft placeholder |
| [07 Patterns](docs/07-patterns/README.md) | Draft placeholder |
| [08 Anti-patterns](docs/08-anti-patterns/README.md) | Draft placeholder |
| [09 Reference architecture](docs/09-reference-architecture/README.md) | Draft placeholder |
| [10 Reference implementations](docs/10-reference-implementations/README.md) | Non-canonical examples |
| [Diagrams](diagrams/README.md) | Conceptual diagrams |
| [RFCs](rfcs/README.md) | Process for conceptual change |

## Contribution

Editorial fixes and examples are welcome. Changes to Convergence, Converged
Engineering, principles, the capability model, terminology, or architecture
go through an [RFC](rfcs/README.md).

See [CONTRIBUTING.md](CONTRIBUTING.md) and [GOVERNANCE.md](GOVERNANCE.md).

## License

Documentation is licensed under [Creative Commons Attribution 4.0
International](LICENSE) (CC BY 4.0). If executable examples or code are added
later, they should use Apache License 2.0 unless a later decision says
otherwise.
