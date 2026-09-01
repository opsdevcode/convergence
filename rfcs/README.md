# RFCs

RFCs (requests for comment) are the path for conceptual change. They exist so
that definitions do not drift through a series of well-meaning pull requests.

## When an RFC is required

- Changing the working definition of Convergence or Converged Engineering
- Adding, removing, or restating a principle
- Major changes to the capability model or contract
- Introducing or redefining architecture concepts (including the capability
  graph)
- Terminology changes that invalidate existing documents
- Repositioning "Capability Engineering" as the name of this body of work

## When an RFC is not required

- Typos, links, formatting
- Clarifications that keep the same meaning
- Additional examples of an already-defined idea
- Filling a placeholder section without changing foundations

If you are unsure, open a short issue first. Maintainers may ask for an RFC
after a pull request starts.

## Process

1. Copy [TEMPLATE.md](TEMPLATE.md) to `rfcs/NNNN-short-title.md`. Use the next
   unused number, starting at `0001`.
2. Open a pull request with the RFC in `Proposed` status.
3. Discussion happens on the pull request (and linked issues).
4. Maintainers set the status to `Accepted`, `Deferred`, or `Declined` and
   record the decision in the RFC.
5. An accepted RFC is implemented in the docs in a follow-up commit or PR.
   The RFC remains as the historical argument.

Numbers are not reused. Declined RFCs stay in the tree.

## Status values

| Status | Meaning |
| --- | --- |
| Proposed | Open for discussion |
| Accepted | Maintainers agree; docs should be updated |
| Deferred | Not now; may revisit |
| Declined | Will not be adopted as written |

## Quality bar

An RFC should state the problem, the proposed change, what it is not, and
which documents would need to change. "I prefer different wording" is usually
an editorial PR, not an RFC.
