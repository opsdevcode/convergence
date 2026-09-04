# How to critique this

This repository is a proposed **synthesis / reasoning model**, not a finished
standard and not a new engineering discipline. Structured disagreement is
more useful than agreement that restates the text.

Read [The problem](problem.md), [Prior art](prior-art.md),
[Design doctrine](design-doctrine.md),
[Terminology](terminology.md), and the
[six Major Principles](../01-principles/README.md) before arguing from a
single later page. Applied sections can be wrong without the core being
wrong, and the reverse is also true. Frozen material is the reasoning
model. Method, operating-model vignettes, maturity, and adoption are
application guidance; they do not extend the conceptual core.

## What is frozen, what is not

| Layer | Treat as | Change path |
| --- | --- | --- |
| Definitions, six principles, design doctrine, conceptual loop, capability as mechanism | Frozen unless a contradiction is found | [RFC](../../rfcs/README.md) |
| Method, patterns, anti-patterns, operating-model vignettes, adoption sketches | Applied guidance; expected to improve with practice | Pull request, unless a change quietly redefines a frozen term |
| Architecture, AI-native consumption, maturity spectra, reference architecture | First versions of applied design, not extra principles | Pull request for clarification; RFC if a new concept would force a rewrite |
| [Open questions](open-questions.md) | Parked on purpose | Do not "complete" these to make v0.1 feel finished |

An RFC on a named candidate should say **what breaks without it**. Preference
for different wording is an editorial pull request, not an RFC.

## What to attack

Useful critique names a claim, shows where it fails, and proposes a
narrower claim or a parked question. Discipline-shaped questions that
have already been used internally:

| If you work in | Ask |
| --- | --- |
| Product | Does intent stay at a level the consumer can responsibly own, or does the model smuggle platform decisions into product language? |
| Platform | Where is this indistinguishable from a paved path or an IDP? Where does it refuse to become one? |
| SRE | Does learning actually change realizations, or does it only produce dashboards? Does distributed execution still leave someone on the hook? |
| Infrastructure / cloud | Does organizational independence hide the people who still get paged? Is reuse treated as automatically good? |
| Networking | Which boundaries are intentional (blast radius, trust zones) and which are ticket routing with extra steps? |
| Identity | Does the model confuse capability ownership with a security boundary? Does invoking a capability get treated as permission? |
| Security | Where would composition silently expand authority? Where is human review required and still first-class? |
| Data | Does learning treat pipelines, quality, and classification as expertise, or as telemetry about other people's systems? |
| AI engineering | Is the discipline (models, training, serving) kept distinct from AI as a consumer of other capabilities? |
| Anyone operating agents | Can an agent discover, parse, bound, and escalate without being granted authority by the mere fact of a tool schema? |

## Claims that should survive hostile reading

If any of these fail in the text, say so with a citation.

- Specialists remain necessary. Silos as a delivery API do not.
- A capability is what the system can accomplish, not a team, API, or
  platform feature.
- Experience and realization must stay distinct from capability.
- Human realization is not an immature stage.
- Friction is evaluated by the value it provides, not by whether it slows
  delivery.
- Organization can carry governance value; routing through org charts is
  still the failure mode.
- Encoding is broader than automation, and encoded expertise must remain
  challengeable.
- Execution, authority, ownership, privilege, and outcome ownership are
  not the same thing.
- Learning informs change; it does not mandate it, and organizations may
  ignore evidence.
- Abstraction and contracts represent knowledge; they are not reality.
- Composition of safe parts is not automatically safe.
- Federation is allowed. One enterprise graph, platform, or taxonomy is
  not required.
- Convergence cannot be delegated to a Convergence function.
- Ticket counts, catalog size, automation percentage, and platform
  adoption are not the definition of success.

The [anti-patterns](../08-anti-patterns/README.md) list failure modes that
look like adoption. If you have seen a different one in the wild, that is
a contribution. If you think one of those is actually correct practice,
that is a critique.

## What is not useful

| Move | Why it does not help |
| --- | --- |
| "This is just DevOps / Platform Engineering / SRE / Team Topologies" | Those are lineage, not insults. Say which frozen *relationship* (for example capability vs realization, or authority vs execution) is identical to a named neighbor, and which this synthesis still uses. Distinction is attempted in [Converged Engineering](converged-engineering.md) and [Prior art](prior-art.md). Do not treat "existing practice already covers the join" as a useless critique—that is a valid attack on usefulness. |
| "You need a platform / graph database / catalog to do this" | The model forbids that as a requirement. Argue that the prohibition is dishonest, with an example where practice cannot proceed without one. |
| "Add a seventh principle / maturity level / scoring rubric" | Open questions exist so those are not filled in for completeness. |
| "Name a vendor or product as the reference implementation" | Implementations do not define the model. [Reference implementations](../10-reference-implementations/README.md) stay empty until something can be described without becoming a buy list. |
| Restating a parked topic as if it were an omission | Parked means the authors refused to invent a framework. Argue that practice is blocked *without* a definition, not that the list is short. |
| Demanding an org chart, budget model, or Convergence team | Explicitly out of scope. Critique the *consequences* of leaving them unspecified if that is the issue. |

## How to send it

| Kind of disagreement | Where |
| --- | --- |
| Typo, broken link, unclear sentence that does not change meaning | Pull request. See [CONTRIBUTING.md](../../CONTRIBUTING.md). |
| Example, pattern, or anti-pattern from practice | Pull request or discussion; RFC only if it redefines a frozen term. |
| A frozen definition, principle, or mechanism is wrong | [RFC](../../rfcs/README.md). State the contradiction. |
| A parked topic is now blocking real work | RFC if it would change the core; otherwise describe the field evidence on the open-questions discussion, not a new principle. |

Disagreement about the model is expected. Vendor advocacy disguised as
theory is not. Follow the [Code of Conduct](../../CODE_OF_CONDUCT.md).
