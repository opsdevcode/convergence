# DeployApplication composition

Illustrative names, not a catalog standard. Composition is relative;
these components are not objectively atomic.

```mermaid
flowchart TB
  Consumer["Consumer"]
  Deploy["DeployApplication"]

  Run["RunWorkload"]
  Id["EstablishIdentity"]
  Net["ProvideConnectivity"]
  Secrets["ManageSecrets"]
  Obs["ObserveService"]
  Rel["EstablishReliability"]

  Consumer --> Deploy
  Deploy --> Run
  Deploy --> Id
  Deploy --> Net
  Deploy --> Secrets
  Deploy --> Obs
  Deploy --> Rel
```

See [Composite capabilities](../docs/02-capabilities/composite-capabilities.md).
