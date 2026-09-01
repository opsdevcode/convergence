# Standard path as a composed capability

## Problem

A routine intent requires the consumer to assemble the organization.
Several specialties each hold a necessary piece, each piece is
individually reasonable, and the consumer becomes the integrator by
default.

## The pattern

Name the ability the organization already has, express it as one
[composite capability](../02-capabilities/composite-capabilities.md), and
let the contributing specialties supply realization and domain authority
rather than sequential approval.

`DeployApplication` composes workload, identity, connectivity, secrets,
observability, and reliability. The consumer expresses one intent. The
specialties still own their domains.

## When it applies

- The intent recurs and the common cases are settled.
- The contributing expertise exists and is willing to state its rules.
- Someone will own the composite, including its failures.
- The consumer can responsibly own the intent at that level.

## What it costs

| Cost | Detail |
| --- | --- |
| Ownership of the seam | Someone must own the composite, which is real work with no obvious home |
| Contract maintenance | Six contributing constraints now have to coexist and stay current |
| Concentration | Everything routine flows through one path, so its defects and compromises are amplified |
| Boundary arguments | "Standard" has to be defined, and the edge will be disputed |

Reuse creates leverage and concentration risk at the same time. That is
not a reason to avoid the pattern. It is a reason to know which paths
carry the most traffic.

## When not to use it

- The intent is rare, and a conversation is cheaper than a contract.
- The contributing rules are still moving, so the composite would encode
  a guess.
- No owner exists, in which case the composite becomes an unmaintained
  dependency that everyone relies on.
- The consumer does not actually own the intent at that level, and the
  abstraction would hide a responsibility that is legitimately theirs.

## Related

Composition must not silently expand authority. See
[Major Principle 5](../01-principles/05-distribute-execution.md) and
[designing experience and realization](../12-method/designing-experience-and-realization.md).

Failure mode: [Capability as a team rename](../08-anti-patterns/capability-as-a-team-rename.md).
