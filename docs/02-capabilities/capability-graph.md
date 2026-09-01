# Capability graph

**A Capability Graph represents what the engineering system can
accomplish, how those capabilities relate and compose, what constrains
them, and which outcomes they contribute to.**

It is **not** inherently a graph database, a CMDB, a service catalog, an
org chart, a platform, or a runtime control plane. This repository does
not prescribe implementation.

An org chart describes who exists. A service catalog typically describes
available services. A capability graph describes **what the engineering
system can accomplish** and how those abilities relate.

## Potential relationships (not standardized)

Relationships may eventually include ideas such as composes, requires,
constrains, governs, observes, contributes-to. **Do not treat this as an
edge vocabulary standard.**

## Example

```
LaunchRegulatedAPI
        |
        +-- RunWorkload
        +-- EstablishIdentity
        +-- ProvideConnectivity
        +-- ProtectSensitiveData
        +-- ObserveService
        +-- EstablishReliability
```

Security expertise may contribute across several of these without
"Security Team" being a delivery stage.

See [Composite capabilities](composite-capabilities.md) and
[Converged architecture](../03-architecture/converged-architecture.md).

Consumers (humans, products, software, automation, authorized agents) are
entry points into the same conceptual graph with different experiences
and authorization. They should not each get a private org-routing
process.

**TODO:** Graph versioning, cycles, and paved paths as distinguished
subgraphs remain later architecture work.
