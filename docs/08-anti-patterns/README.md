# Anti-patterns

Failure modes that recur when organizations adopt this model. Each one is
tempting for a real reason, which is why it keeps happening.

The format is deliberate: why the move is attractive, what it costs, how
to recognize it, and what to do instead. None of these is written to mock
the people who did the tempting thing under pressure.

| Anti-pattern | Short form |
| --- | --- |
| [Portal as ticket router](portal-as-ticket-router.md) | The queue got a nicer front door |
| [Capability as a team rename](capability-as-a-team-rename.md) | New vocabulary, same request path |
| [Automation as maturity](automation-as-maturity.md) | Human realization treated as a lower stage |
| [Catalog first](catalog-first.md) | An inventory of aspirations before any real path |
| [Convergence as a function](convergence-as-a-function.md) | A team or VP owns Convergence, and becomes the new routing layer |
| [Invocation as authority](invocation-as-authority.md) | Whoever can call it is treated as entitled to it |
| [Ownership without encoding](ownership-without-encoding.md) | "You build it, you run it" with no expertise transferred |
| [Ticket count as the score](ticket-count-as-the-score.md) | Optimizing the signal instead of the system |

## Not yet written up

Named for completeness, still to expand:

- Measuring platform success only as developer satisfaction
- Treating Converged Engineering as a synonym for Platform Engineering or
  DevOps
- Requiring one enterprise graph or a global capability taxonomy
- Maximizing reuse, abstraction, or self-service as if that were the goal
- Contracts or models treated as perfect representations of reality
- Treating every handoff, approval, or organizational boundary as waste

## Related

Positive designs are in [Patterns](../07-patterns/README.md). The
reasoning lens that distinguishes a real control from inherited process
is the [design doctrine](../00-foundations/design-doctrine.md).
