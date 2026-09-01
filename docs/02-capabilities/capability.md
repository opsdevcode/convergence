# Capability

**A capability is an organization's ability to satisfy a class of intent
through the application of expertise, resources, and systems.**

A capability describes **what** the engineering system can accomplish.

**Expertise is what someone knows. Capability is what the engineering
system can accomplish with that expertise.**

## What a capability is not (inherently)

A capability is not inherently an API, a service, automation, a workflow,
a platform feature, a product, a team, or a person. Those may participate
in its [experience](experience.md) or [realization](realization.md).

A capability does not require a formal [contract](capability-contract.md)
to exist.

## How capabilities may appear

Capabilities may be implicit or explicit; human-realized,
technology-realized, or hybrid; primitive *relative to a given
abstraction*, or [composite](composite-capabilities.md).

"Primitive" is not an objective atomic unit. A capability that looks
simple at one level may itself be composed of others.

## Example: human-realized capability

If one security architect is the only person who can perform a novel
security architecture assessment, the organization possesses:

`AssessNovelSecurityArchitecture`

That architect possesses expertise. The organization possesses the
capability because it can use that expertise to satisfy the intent. The
capability is currently human-realized and organizationally fragile. It
is still a capability.

See [Worked examples](worked-examples.md) and
[Human-realized capability](../../diagrams/assess-novel-security-architecture.md).

## Consumers

A capability may be used by humans, products, software systems,
automation, authorized AI agents, and other capabilities.

**Your organizational structure should not become your software delivery
API.**
**Consumers should depend on capabilities more strongly than they depend
on realizations.**

Some engineering consumers legitimately operate at lower abstraction and
may need realization detail. That is not a license to make the org chart
the default interface.
