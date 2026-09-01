# Product engineering

Product engineers remain responsible for customer-facing experiences and
for product judgment: what to build, for whom, and whether it worked.

## What does not disappear

- Product discovery and design
- Application architecture and domain logic
- Accountability for customer outcomes
- The need to understand constraints (latency, data class, regions) that
  affect the product

## What changes

Product engineers should consume **capabilities** (and compose them where
that is the right abstraction) instead of treating the company as a set
of teams to negotiate. Governance belongs in contracts and realizations
where the risk warrants it, not as a tour of the org.

They are part of the product value chain, not the internal customer of a
platform in the sense that the business exists to delight developers. A
good capability experience still matters because it is on the path to
customer outcomes.

Intent-level interfaces (`DeployApplication`, data access, workflow
triggers) are usually the right consumer interface when the consumer can
responsibly own that intent. Dropping to raw compute or filing four
coordinated requests should be exceptional for understood work, and that
exception should feed encoding, not become the architecture.

## What this is not

Product engineers do not absorb SRE, security, and infrastructure as a
personality type. When a capability is missing or wrong, the move is to
extend the capability with the specialists who own it, not to pretend the
product team can recreate that expertise under deadline.
