# Realization

**Realization is the people, processes, technologies, policies,
services, and mechanisms through which a capability is fulfilled.**

A capability describes **what** can be accomplished. A realization
describes **how it is currently accomplished**.

The capability may remain stable while its realization changes.

**Consumers should depend on capabilities more strongly than they depend
on realizations.**

This is not a requirement that realization details always be hidden.
Some engineering consumers legitimately operate at lower abstraction.

## Example: ProvideRelationalStorage

Capability: `ProvideRelationalStorage`

Possible realizations:

- A DBA manually provisions a database
- Terraform and a cloud SQL service
- An internal platform plus managed PostgreSQL
- An external managed database service
- Human approval combined with automation

The product engineer depends on the capability (durable, eligible
relational storage for their intent). Which of the list above is true
this quarter is a realization choice owned by those with domain authority
and capability ownership.

## Human realization

`AssessNovelSecurityArchitecture` may be realized as a named security
architect, security standards, threat-modeling practice, and
organizational knowledge. If a successor later becomes the realization,
the capability can remain.

See [Organizational independence](organizational-independence.md).
