# Ownership without encoding

Product teams are told they now own reliability, security, and
infrastructure for their services. No expertise was encoded, no
capabilities were made explicit, and the specialists who held that
knowledge were reassigned or reduced.

The slogan is "you build it, you run it". The result is that every team
independently rediscovers the same production knowledge.

## Why it is tempting

It is a genuine correction of a real problem. Teams that cannot operate
what they ship do build fragile systems, and ownership without
consequence produces exactly that.

It also appears to reduce cost immediately: fewer central specialists,
faster decisions, no queue.

## What it costs

| Cost | Detail |
| --- | --- |
| Duplicated learning | Every team pays the tuition on the same lessons |
| Uneven outcomes | Reliability and security become a function of which team you joined |
| Lost depth | Specialists who leave take knowledge that was never written down |
| Invisible risk | Nobody holds a view of risk across the estate |
| Cognitive load | Product engineers hold production identity, threat modelling, and product judgment at once |

The last one is the giveaway. Nobody was asked to become full stack in
this sense, and expecting it is not a delivery model.

## How to recognize it

- Teams solving the same production problem in parallel, differently.
- Security or reliability quality varying widely by team.
- Specialists reduced or dispersed before their knowledge was encoded.
- New teams taking many months to reach a baseline that used to be
  provided.

## What to do instead

Ownership and encoding go together. Before moving accountability, make
the expertise consumable: standards, paved paths, policy, modules,
decision guidance, or a capability with a real contract. Any of the
[forms of encoding](../12-method/deciding-what-to-encode.md) will do; the
requirement is that the knowledge exists outside individual heads.

**Shared contribution does not require shared accountability.** A product
team can own an outcome while domain authority for identity, security,
and reliability stays with specialists who contribute through
capabilities.

## Related

[Major Principle 1](../01-principles/01-specialization-remains-silos-dont.md),
[Operating model](../04-operating-model/README.md), and
[Expertise encoding](../02-capabilities/expertise-encoding.md).
