# Identifying capabilities

**Serves:** [Major Principle 1](../01-principles/01-specialization-remains-silos-dont.md)
and the [capability](../02-capabilities/capability.md) mechanism.

A trace shows an organization walking. Identification asks what that
organization can already accomplish.

The capability almost always already exists. You are naming something,
not creating it. Encoding changes its
[realization](../02-capabilities/realization.md) and its leverage, not
its existence.

## The three-way test

For each candidate, ask which of the three it describes. Getting this
wrong is the most common modelling error in the whole model.

| If it describes | It is | Example |
| --- | --- | --- |
| What the system can accomplish | Capability | `ProvideRelationalStorage` |
| How a consumer interacts with it | [Experience](../02-capabilities/experience.md) | The portal, the pull request, the conversation |
| How the organization fulfills it | [Realization](../02-capabilities/realization.md) | Terraform plus a managed service, or a DBA |

"Self-service database portal" fails the test. It is an experience
attached to a capability that existed before the portal did.

## Naming

Verb-led and intent-shaped. The name should survive a change of owner,
vendor, and implementation.

| Prefer | Avoid | Why |
| --- | --- | --- |
| `ProvideRelationalStorage` | `DatabaseTeamRequest` | Names a team, so it dies in a reorg |
| `EstablishServiceIdentity` | `OktaOnboarding` | Names a vendor, so it dies at renewal |
| `DeployApplication` | `CI/CD Pipeline` | Names a mechanism, not an ability |
| `AssessNovelSecurityArchitecture` | `SecurityReviewTicket` | Names a queue, not an accomplishment |
| `ProtectSensitiveData` | `Compliance` | Names a department, not an ability |

If a name only makes sense to people who know the current org chart, it
is not a capability name yet.

## One capability or two

Two candidates are the same capability when they satisfy the same class
of intent and differ only in how they are fulfilled.

Managed Postgres in one region and a self-hosted cluster in another are
one capability with two realizations, provided the consumer's intent and
eligibility are the same. If the consumer must reason differently about
what they will get, they are probably two capabilities, or one capability
with an honest constraint in its
[contract](../02-capabilities/capability-contract.md).

## Composition is relative

`DeployApplication` composes workload, identity, connectivity, secrets,
observability, and reliability. Each of those composes further. There is
no atomic layer to find, so do not spend the first pass looking for one.
See [composite capabilities](../02-capabilities/composite-capabilities.md).

Name the level people actually express intent at. Add composition
downward only when it changes a decision.

## Human-realized capabilities count

If the only realization is one specialist and a practice, it is still a
capability. It is fragile, and writing it down is what makes the
fragility visible instead of ambient.

Maturity is not automation. See
[capability characteristics](../02-capabilities/capability-characteristics.md).

## Traps

- Building a taxonomy before naming three real capabilities.
- Creating a catalog as the first deliverable, which produces an
  inventory of aspirations.
- Renaming existing teams as capabilities and keeping the same queue.
- Naming an intent nobody expresses, because it completes a diagram.
- Modelling downward until every cloud primitive has a capability name.
