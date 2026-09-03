# Identity

Identity expertise remains. Who and what may act, with which credentials,
under which policy, is scarce knowledge that most other capabilities
depend on.

## Scope note

This page is about the **identity discipline**: workload and human
identity, credentials, and access policy as expertise consumed through
capabilities. How an **AI agent** is authorized to act is a consumption
question, covered in
[Authorization and principals](../05-ai-native-engineering/authorization-and-principals.md).
The two meet at the same rule: invocation is not authority.

## What does not disappear

- Workload and human identity design
- Credential issuance, rotation, and revocation
- Authentication and authorization policy
- Federation and trust across boundaries
- Secrets management and its failure modes

## What changes

Identity should appear as **capabilities other capabilities compose**
rather than a queue every service crosses during setup.

| Was requested as | Becomes |
| --- | --- |
| A ticket to create a service account | `WorkloadIdentity` issued as part of a workload |
| Manual credential handoff | Issuance and rotation inside a contract |
| "Ask identity for access" | Policy stated where the capability is consumed |

Issuance and rotation are mechanical and belong encoded. The **policy**
behind them, who may hold what, is judgment and stays with identity as
domain authority. Encoding the mechanism does not delegate the decision.

Identity is where **authority, privilege, and execution** must not be
conflated. See
[Major Principle 5](../01-principles/05-distribute-execution.md). A
capability that issues identity must not become a way to acquire authority
nobody granted, and composition must not silently widen privilege.

## What this is not

Not an identity or access-management design. This repository defines no
token format, protocol, or directory, and it does not replace identity,
IAM, or security functions. It states where identity expertise is consumed
as a capability and where it remains a decision.
