# Infrastructure and cloud

Deep infrastructure expertise remains. Cloud, facilities, compute, storage,
and the messy reality of accounts, quotas, and regions do not vanish because
product teams speak in intents.

## What does not disappear

- Substrate design and operation
- Capacity, performance, and failure domains
- Cloud vendor and networking realities
- Identity providers and low-level isolation
- The work of making unsafe things hard and safe things easy

## What changes

Infrastructure should increasingly become an **implementation detail of
higher-level capabilities** rather than something application teams request
directly.

Infrastructure and cloud engineers should spend more of their time
engineering reusable capabilities (and the lower-level capabilities those
compose) and less time fulfilling individual infrastructure requests that
differ only in the ticket metadata.

Direct access to raw substrate remains for specialists, break-glass, and
novel architectures. It should not be the default developer API.

## Networking and identity

The same pattern applies. Networking and identity expertise is not
"undifferentiated heavy lifting" to be ignored. It is scarce knowledge that
should appear as composable capabilities (`Connectivity`, `WorkloadIdentity`)
with contracts that security and product can rely on.

## What this is not

This is not "the cloud team is obsolete because Kubernetes exists." Managed
services and platforms still need people who understand them. The request
catalog should shrink as a *primary* interface, not the skill.
