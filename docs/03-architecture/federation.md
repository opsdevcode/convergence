# Federation

Federation is a boundary condition of Convergence, not a separate
framework and not a stage of maturity.

**Convergence does not require one homogeneous enterprise engineering
system. Convergence can exist as a federation of engineering systems that
become coherent at the boundaries where they must interact. Convergence is
recursively applicable.**

## Which engineering system

The phrase "the engineering system" means the relevant system through
which a class of intent moves toward outcome. That system may exist at
team, domain, business-unit, regional, enterprise, or cross-organizational
scope.

This matters structurally because everything else in this section applies
at whichever scope is relevant. A team can practice Converged Engineering
within itself while sitting inside a division that has not. Two companies
sharing a delivery path can converge at their shared boundary without
either reorganizing.

## What a boundary is

A federation boundary exists where two engineering systems must interact
but need not share realization. Boundaries commonly follow legal entity
separation, regulatory jurisdiction, data residency, acquisition history,
or genuine domain autonomy.

The architectural question at a boundary is not "how do we make these the
same" but "what has to be true on both sides".

| Crosses the boundary | Stays local |
| --- | --- |
| The intent being expressed | How that intent is fulfilled |
| The obligations both sides must satisfy | The tools, vendors, and sequence used |
| The constraints that carry regulatory or risk weight | Team structure and internal process |
| What each side can rely on from the other | Realization detail |

**Standardize obligations before standardizing realizations.**
**Shared intent and constraints do not require shared realization.**

Two regions can satisfy the same data-protection obligation with
different managed services. Requiring one implementation because it is
tidier converts a coherence requirement into a uniformity mandate.

## Converge selectively

**Converge where outcomes require coherence. Preserve autonomy where they
don't.**

**Convergence seeks coherence where coherence provides value, not
uniformity everywhere.**

| Converge when | Preserve autonomy when |
| --- | --- |
| An outcome depends on both sides behaving compatibly | Each side's outcomes are independent |
| An obligation applies across the boundary | The constraint is genuinely local |
| Consumers must cross the boundary for routine intent | Crossing is rare and deliberate |
| Inconsistency creates real risk | Inconsistency is merely untidy |

Untidiness is not a reason to converge. That single distinction prevents
most federation programs from becoming standardization programs.

## Formalism at the boundary

**Formalism should scale with organizational distance, risk, consequence,
reuse, and complexity.**

Organizational distance is the term doing the work here. A capability
consumed across a legal entity boundary needs more explicit contracts and
evidence than the same capability consumed inside one team, because less
shared context can be assumed and less can be corrected by conversation.

## Graphs are federated by default

A [capability graph](capability-graph-structure.md) in a federated system
is normally partial and composed from several domain views.

**Useful incompleteness is better than fictional completeness.**

No single enterprise graph, registry, or global capability taxonomy is
required, and attempting one across a federation boundary usually
produces a naming argument rather than a shared understanding.

## Trust is unresolved

What one engineering system can rely on from another, and what has to be
verified rather than assumed, is not settled here. Federation is currently
a boundary condition, not a trust protocol.

Trust across federation boundaries is named as an
[RFC candidate](../00-foundations/open-questions.md). An RFC would have to
establish what may be relied upon, what must be verified, and what happens
when a boundary is crossed under time pressure.

## Not implied

- Federation is not a lower maturity state to grow out of.
- Federation does not require a coordinating body, council, or shared
  platform. See
  [Convergence as a function](../08-anti-patterns/convergence-as-a-function.md).
- There is no federation maturity model in this repository.
