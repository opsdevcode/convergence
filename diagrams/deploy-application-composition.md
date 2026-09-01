# DeployApplication composition

Illustrative only. Names are examples, not a catalog standard.

The consumer invokes `DeployApplication`. That capability composes others.
The consumer of the high-level capability does not have to consume each
provider's process.

```mermaid
flowchart TB
  Consumer["Consumer: human, product, software, automation, or agent"]
  Deploy["DeployApplication"]

  Compute["Compute"]
  Net["Networking"]
  Id["Identity"]
  Secrets["Secrets"]
  Sec["Security"]
  Obs["Observability"]
  Dep["Deployment"]
  Rel["Reliability"]

  Consumer --> Deploy
  Deploy --> Compute
  Deploy --> Net
  Deploy --> Id
  Deploy --> Secrets
  Deploy --> Sec
  Deploy --> Obs
  Deploy --> Dep
  Deploy --> Rel
```

See [Anatomy of a capability](../docs/02-capabilities/anatomy-of-a-capability.md).
