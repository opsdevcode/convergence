# Worked examples

Two contrasting capabilities, same conceptual model. One is often
technology-realized. One is often human-realized. Both are capabilities.

Recurring names in this repository: `ProvideRelationalStorage`,
`DeployApplication`, `AssessNovelSecurityArchitecture`,
`LaunchRegulatedAPI`.

## ProvideRelationalStorage

**Intent (product engineer):** My application needs persistent relational
storage I am eligible to use. (Engineering-level intent they can own.
Not "open the DBA queue.")

**Capability:** The organization can satisfy a class of relational
storage intent (`ProvideRelationalStorage`).

**Experience:** Documentation and a request path (PR, API, portal, or
conversation) that states size class, data class, environment. Observation
of whether storage is usable.

**Realization (examples):** DBA by hand; Terraform plus cloud SQL;
platform plus managed PostgreSQL; human approval plus automation. The
capability can outlast a change of realization.

**Output:** A database instance exists.

**Outcome:** The application has usable, policy-fitting relational
persistence for the stated intent.

**Learning:** Repeated exceptions for the same data class become policy
in the contract; a missing observability default is added to realization.

See [Output and outcome](output-and-outcome.md) for contribution upward
to claim submission and cost (traced, not owned by this capability).

## AssessNovelSecurityArchitecture

**Intent (product or engineering lead):** We need a security architecture
assessment of a design we have not shipped before.

**Capability:** `AssessNovelSecurityArchitecture`. The organization can
satisfy that class of intent.

**Experience:** Request an assessment, provide context, collaborate with
a security architect, receive findings, discuss exceptions.

**Realization:** Sarah (expertise) plus standards, threat-modeling
practice, and organizational knowledge. Fragile if only Sarah can do it.
Still a capability.

**Output:** A written assessment, a meeting, a list of findings.

**Outcome:** The design has been assessed against the organization's
security expectations; residual risk is explicit enough for outcome
owners to decide.

**Learning:** The same "novel" request repeats. Part of the judgment is
encoded into standards or a narrower capability. Sarah's time moves back
toward remaining novel work.

If Sarah is replaced by Alex, consumers still use the capability, not
Sarah's calendar as the public API. See
[Organizational independence](organizational-independence.md).

## DeployApplication and LaunchRegulatedAPI

`DeployApplication` is a composite of workload, identity, connectivity,
secrets, observability, and reliability capabilities.
`LaunchRegulatedAPI` additionally depends on protecting sensitive data
and meeting governance that may remain human for exceptions. See
[Composite capabilities](composite-capabilities.md) and
[Regulated enterprise](../11-adoption/regulated-enterprise.md).
