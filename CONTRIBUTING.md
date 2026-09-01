# Contributing

This repository is a body of work, not a product backlog. Contributions
should improve clarity, correctness, or usefulness of the proposed model.
They should not attach the work to a vendor, product, or internal platform
brand.

Read [GOVERNANCE.md](GOVERNANCE.md) before proposing conceptual changes.

## What to contribute

### Editorial fixes (no RFC)

- Typos, broken links, grammar, and formatting
- Small clarifications that do not change meaning
- Diagram rendering fixes

Open a pull request. Keep the diff small.

### Examples (usually no RFC)

- Additional illustrations of an existing idea (for example, another
  composition similar to `DeployApplication`, or a human-realized
  capability similar to `AssessNovelSecurityArchitecture`)
- Operating-model vignettes that do not introduce new terms

If an example quietly redefines a term, it needs an RFC.

### New patterns and anti-patterns

Start as a discussion or draft in `docs/07-patterns/` or
`docs/08-anti-patterns/`. Recurring, well-supported patterns can later be
promoted through an RFC if they imply a change to the model or principles.

### Conceptual changes (RFC required)

Use an [RFC](rfcs/README.md) for:

- Changing the working definitions of Convergence or Converged Engineering
- Adding, removing, or restating principles
- Major changes to the capability model or contract
- New architecture concepts (including the capability graph)
- Terminology changes that would force a rewrite of existing docs

The v0.1 conceptual core is treated as frozen unless a contradiction is
found. Prefer [Open questions](docs/00-foundations/open-questions.md)
over new principles or lifecycle nodes.

## How to work

1. Prefer a pull request against the default branch.
2. Write in the same tone as existing documents: plain language, specific
   claims, no marketing.
3. Reuse terms from [terminology.md](docs/00-foundations/terminology.md).
   Do not mix Convergence, Converged Engineering, and capability.
4. Do not present a tool, platform, or vendor as the definition of the
   model.
5. Do not claim Convergence or Converged Engineering is an industry
   standard.
6. Do not imply that specialized engineering roles should disappear.
7. Do not propose a Convergence Engineering team or silo as the solution.
8. Do not revive "Capability Engineering" as the name of the overarching
   model unless an RFC does so.

## Review criteria

Maintainers will ask:

- Does this preserve "specialization remains; silos don't"?
- Is Converged Engineering still distinct from Platform Engineering, SRE,
  DevOps, and a generic "full stack" story?
- Are capabilities treated as a mechanism, not as a cure-all?
- Are claims proportionate to evidence, including about AI agents?
- Would a skeptical infrastructure, SRE, or security engineer recognize
  their work as still necessary?

## Conduct

Follow the [Code of Conduct](CODE_OF_CONDUCT.md). Disagreement about the
model is expected. Personal attacks and vendor advocacy disguised as theory
are not.
