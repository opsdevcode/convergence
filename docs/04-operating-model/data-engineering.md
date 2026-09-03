# Data engineering

Data expertise remains. Pipelines, storage, schema, quality, lineage, and
classification are deep work, and getting them wrong is expensive in ways
that surface late.

## What does not disappear

- Pipeline and storage design
- Schema, contracts, and data quality
- Lineage and provenance
- Classification and access governance
- The judgment about what is safe to expose and to whom

## What changes

Data work should increasingly appear as **capabilities with contracts**
rather than bespoke integrations negotiated per consumer.

| Was requested as | Becomes |
| --- | --- |
| A one-off pipeline built by ticket | `CreateDataPipeline` with a stated contract |
| Direct access to a raw store | An eligible, classified access capability |
| "Which team owns this dataset?" | Discoverable ownership, not a routing prerequisite |

Treating a dataset as a product with an owner, a contract, and consumers
is not new; it is close to what the data-mesh literature already argues.
Convergence does not claim to have invented it. The point here is only
that data is one more discipline whose expertise is consumed as
capabilities, not through org navigation.

## Two things data adds

**Classification is intentional constraint.** Which data class may flow
where is a governance boundary, often regulatory. It belongs stated in the
contract and enforced in realization, at the
[edge and in the node](../07-patterns/policy-at-the-edge-or-in-the-node.md),
not discovered after a consumer has committed.

**Learning is itself data.** The evidence the system learns from, usage,
failures, incidents, cost, flows through data capabilities. Data
engineering is therefore part of how the loop
[closes](../01-principles/06-close-the-loop.md), not only a consumer of it.
See [Observation](../03-architecture/observation.md).

## What this is not

Not a data platform mandate, and not a claim that a catalog or mesh
product is required. A dataset with an owner and a written contract is the
capability. The tooling is realization.
