# Enterprise

Illustrative: large organization, many specialized functions,
substantial coordination cost. This is not a recommendation to reorganize.

Show the model without assuming a new org chart:

- **Capability ownership** for composites such as `DeployApplication` or
  `LaunchRegulatedAPI` is explicit and discoverable.
- **Domain authority** for security, identity, networking, reliability
  remains with specialists who contribute to those capabilities.
- **Composite capabilities** make contribution visible without making
  each specialty a delivery stage.
- **Multiple experiences:** API for standard paths, human collaboration
  for novel assessment, documentation for discovery.
- **Multiple realizations:** managed services in some regions, internal
  platforms in others, people for exceptions. The capability name can
  stay stable.
- **Organizational independence** varies by capability; ownership is
  still listed.
- **Outcome tracing:** `ProvideRelationalStorage` contributes to product
  and customer outcomes it does not own.

The consumer path is consumer → capability → realization, not consumer →
team → team → team. See
[Consumer to capability to realization](../../diagrams/consumer-capability-realization.md).
