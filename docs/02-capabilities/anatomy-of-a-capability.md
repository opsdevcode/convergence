# Anatomy of a capability

A capability can be described as:

```text
Capability
├── Intent
├── Contract
├── Inputs
├── Outputs
├── Dependencies
├── Policies
├── Reliability
├── Security
├── Observability
├── Cost
├── Ownership
├── Lifecycle
├── Outcomes
└── Feedback
```

These are **facets**, not a mandatory form. A secrets-issuance capability
used by three internal services needs less ceremony than a customer-facing
payments path. A prototype capability may have a clear intent and owner and
almost nothing else. That is still a capability. It is a weak one.

## Facets

**Intent.** What this capability is for, in consumer language. If you cannot
state the intent, you probably have a pile of scripts, not a capability.

**Contract.** How consumers bind to the capability: interface, versioning,
compatibility promises. See
[Capability contract](capability-contract.md).

**Inputs.** Parameters, artifacts, and context the consumer must supply
(application image, environment class, data classification, identity of the
requesting principal).

**Outputs.** What success returns (handles, URLs, identities). Returning a
ticket as the primary output should be treated as a smell. Include failure
modes that consumers must handle.

**Dependencies.** Other capabilities this one composes or assumes. This is
the local view of the [capability graph](capability-graph.md).

**Policies.** Constraints that always apply, or that bind based on inputs
(production vs. non-production, data class, region).

**Reliability.** Commitments and mechanisms: availability objectives,
degradation behavior, retry and idempotency expectations, dependency
failure handling.

**Security.** Authentication and authorization of consumers, isolation,
secrets handling, threat assumptions. Distinct from "the security team will
look at it later."

**Observability.** What is emitted, what consumers can see, what providers
use to operate and to learn.

**Cost.** How consumption is attributed, what expensive modes exist, and
whether the contract includes budgets or quotas.

**Ownership.** Who provides it, who to escalate to for novel failure, and
how product teams share responsibility for outcomes.

**Lifecycle.** Version, deprecation, and replacement. Capabilities die;
unversioned org knowledge does not die so much as rot.

**Outcomes.** Which customer or business outcomes this capability is meant
to support, and how you would know.

**Feedback.** How learning re-enters the capability: incident encodings,
usage metrics, contract tests born from failure.

## Example: DeployApplication

`DeployApplication` is a high-level capability. A product engineer (or an
agent acting for that engineer) wants an application running in an
environment under the organization's standard path.

It may compose, among others:

| Underlying capability (illustrative) | Expertise typically encoded |
| --- | --- |
| Compute | Workload placement, capacity, runtime |
| Networking | Connectivity, DNS, ingress, segmentation |
| Identity | Workload identity, roles, audience |
| Secrets | Injection, rotation, access |
| Security | Image and config policy, isolation baselines |
| Observability | Logs, metrics, traces, alerting hooks |
| Deployment | Rollout, revision, rollback |
| Reliability | Health, disruption budgets, SLO wiring |

The consumer of `DeployApplication` should not need to understand each
implementation, or file a request with each providing team, for the
*standard* path. They may still need to understand failure output ("policy
denied: data class") and how to observe the composition.

They are not expected to become network engineers. Network engineers are
expected to make the networking capability safe to compose.

See [DeployApplication composition](../../diagrams/deploy-application-composition.md).

## Premature precision

v0.1 does not define a file format, API, or catalog schema. Organizations
will implement contracts differently. The model exists so those
implementations can be compared, not so this repository can ship a product.
