# Converged Engineering

**Working definition:** Converged Engineering designs the engineering
system so specialized expertise can participate in delivery through
capabilities without requiring consumers to navigate the organizational
structures behind them.

This is a proposed model, not an established methodology.

**Converged Engineering does not eliminate specialization. It eliminates
specialization as a delivery boundary.**

Expertise remains specialized. Ownership remains explicit. Human judgment
remains essential. What converges is delivery.

## Why it is needed

If Convergence is the shift (functions as delivery architecture becoming
less useful), Converged Engineering is a response: keep the specialties;
change how expertise participates.

Without an explicit model, organizations tend to add a platform hop,
declare "you build it, you run it" without encoding specialist knowledge,
or hope agents will navigate the org chart. All three leave the product
assembled through organizational APIs.

## Unit of optimization

**Converged Engineering optimizes the engineering system's ability to move
intent to outcome.**

| Not the unit of optimization | The unit of optimization |
| --- | --- |
| Local efficiency of Platform, Product, SRE, Infrastructure, or Security | The system's ability to move intent to outcome |
| Ticket volume, automation percentage, capability counts | Flow, reliability, quality, risk, cost, consumer experience, learning speed |

Formal metrics are not defined here, and the right column is a set of
characteristics rather than a scorecard. See
[Design doctrine](design-doctrine.md).

The developer is not the platform team's customer as the purpose of the
firm. The developer is part of the product value chain.

## What converges and what does not

| Converges | Does not converge |
| --- | --- |
| The path from [intent](../02-capabilities/intent.md) to [outcome](../02-capabilities/output-and-outcome.md) | Deep domain expertise |
| How expertise is exposed and composed | Ownership of hard systems |
| How that path is governed | Novel work |
| How the system learns from use | Residual-risk judgment |
| How ownership is made discoverable | The reality of layers in implementation |

If a diagram shows one generic "engineer" box, it is the wrong diagram.

## Specialization and encoding

Specialization remains. Career paths for SRE, security, infrastructure,
platform, product, and related roles remain.

**Encode what is repeatable. Collaborate on what is novel.**
**Make exceptional work exceptional again.**

See [Expertise encoding](../02-capabilities/expertise-encoding.md).

Do not create a Convergence Engineering team, a Converged Engineering
silo, a job whose only purpose is to replace Platform Engineering, or
another layer product teams must petition.

**Convergence cannot be delegated to a Convergence function.**

A Platform Engineer, SRE, infrastructure engineer, product engineer, or
security engineer can practice Converged Engineering. The model is a way
of working, not a department.

## Ownership

**Shared contribution does not require shared accountability.**

Domain authority, capability ownership, and outcome ownership are
distinct. See
[Ownership and authority](../02-capabilities/ownership-and-authority.md).

**Ownership should be discoverable without being required for routing.**

## Role of capabilities

Capabilities are a **primary mechanism**: what the engineering system can
accomplish. They are not required to be APIs, platforms, or formal
contracts. They are not the only conceivable mechanism of Convergence.

See [Capabilities](../02-capabilities/README.md) and
[Conceptual model](conceptual-model.md).

## Distinctions

| Related model | What it addresses | Where Converged Engineering differs |
| --- | --- | --- |
| DevOps | The split between writing software and running it | Addresses a wider set of specialist boundaries. DevOps can exist inside a still-siloed delivery chain |
| Team Topologies | Team structures and interaction modes for fast flow | Restructures teams around streams. Converged Engineering leaves specialties intact and changes how their expertise is exposed and consumed, not primarily where team boundaries sit |
| Platform Engineering | Undifferentiated work, through internal products | A platform may participate in [experience](../02-capabilities/experience.md) or [realization](../02-capabilities/realization.md), but is not the definition of Convergence |
| SRE, infrastructure, product | Reliability, substrate, and product judgment | All remain, as expertise contributing to capabilities rather than as a generic role |
| AI agents | Consumption of capabilities at machine speed | Agents are possible consumers. They do not create Convergence; they expose the cost of tribal routing |

Automating tickets is not the model. Reducing unnecessary
[coordination](../02-capabilities/coordination-and-collaboration.md) while
preserving collaboration is closer.

A portal that routes the same tickets has not changed the model, and a
startup can practice Converged Engineering with little or no platform
organization. Product engineers do not become substitutes for security or
infrastructure expertise. Agents must not bypass governance; see
[AI-native engineering](../05-ai-native-engineering/README.md).

## What the model refuses

- "Everyone should just own everything."
- "The platform team is the customer of the business."
- "This model is whatever a vendor ships."
- "Automation equals maturity."
- The claim that the model is already an industry standard.
- A new silo named after the model.
- Maximum abstraction, automation, reuse, or self-service as the goal.
