# Startup

Illustrative: roughly 10–30 engineers, little or no dedicated platform
organization, heavy use of managed cloud and SaaS, direct human
collaboration.

**Convergence should not require Convergence infrastructure.** Do not
build an elaborate internal platform or capability graph system at this
scale unless complexity already justifies it.

Capability contracts may be README conventions and a few required PR
checks. Git, CI/CD, IaC, documentation, and conversation are sufficient
**realizations** and **experiences** for many capabilities.

## End-to-end: ProvideRelationalStorage

**Intent:** A product engineer needs relational storage for a new
feature.

**Capability:** The company can provide eligible relational storage
(today: one managed Postgres offering).

**Experience:** A short doc in the engineering handbook plus a PR that
adds a Terraform module the team already uses. If stuck, ask in the
engineering channel (collaboration, not a ticket queue of record).

**Realization:** Managed cloud database; one person with deeper Postgres
knowledge reviews unusual sizes.

**Outcome:** The app persists data under the agreed backup and access
defaults.

**Learning:** The third "special" request for a second engine is
documented as out of contract; novel work stays with the specialist.

No capability catalog product is required. The capability is still real.
Human judgment on exceptions is still real.
