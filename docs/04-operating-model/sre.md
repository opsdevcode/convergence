# SRE

Reliability expertise remains. SRE does not become unnecessary because
capabilities exist. If anything, capabilities without reliability
engineering become a faster way to ship fragile compositions.

## What does not disappear

- SLO design and error budgets
- Incident response and learning
- Production empiricism
- Toil reduction as engineering work
- The judgment to know when a system is not ready to be a capability

## What changes

Reliability should increasingly be a **property of capabilities**, not a
downstream operational phase that starts at handoff.

SRE expertise should be encoded into:

- reusable reliability capabilities (SLO wiring, health, progressive
  delivery, load shedding patterns)
- paved paths that already include those mechanisms
- policies (you cannot consume `DeployApplication` in production without
  declaring an SLO class)
- telemetry that feeds [learning](../00-foundations/terminology.md)
- automation that handles the known failure modes

SRE still meets novel systems as novel. The goal is that the *nth* similar
service does not require the nth custom operational invention.

## What this is not

SRE is not reduced to writing YAML for other people. Deep reliability work
on data stores, traffic, and failure landscapes remains. Encoding is how
that work multiplies. It is not a demotion.
