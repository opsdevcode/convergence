# Anatomy of a capability

The following are **optional facets** often used to talk about a
capability. They are not a mandatory schema. A capability can exist with
little more than a recognized intent and some realization (including a
person).

Do not confuse the capability with its contract, experience, or
realization.

```text
Capability (what the system can accomplish)
├── Class of intent served
├── Composition (other capabilities, if any)
├── Contract (if explicit): expectations and constraints
├── Experience (how consumers interact)
├── Realization (how it is currently fulfilled)
├── Outcomes it can produce or contribute to
└── Learning / feedback paths
```

Contract-related facets, when used, may include inputs, expected
outcomes, constraints, policies, eligibility, reliability, cost,
ownership, exceptions, and lifecycle. See
[Capability contract](capability-contract.md).

Rigor should match complexity, risk, reuse, and scale.

## DeployApplication

`DeployApplication` is a [composite](composite-capabilities.md)
capability. A product engineer (or an agent acting for them) wants an
application running under a standard path. It may compose `RunWorkload`,
`EstablishIdentity`, `ProvideConnectivity`, `ManageSecrets`,
`ObserveService`, and `EstablishReliability`.

The consumer of `DeployApplication` should not have to file a request
with each providing team for the standard path. Specialists retain domain
authority over what those component capabilities encode.

See [DeployApplication composition](../../diagrams/deploy-application-composition.md)
and [Worked examples](worked-examples.md).
