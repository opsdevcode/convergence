# Incentive compatibility — analysis against the existing corpus

*Non-canonical research note. Not part of the body of knowledge. Does not edit,*
*rename, or extend the canonical corpus, the frozen essay, or its editorial note.*
*No role, incentive model, funding mechanism, principle, model element, or name*
*is proposed. The problem is analyzed, not solved.*

**Question under test.** What happens when improving the engineering system
requires a locally rational capability owner to accept a locally worse outcome
so that the composed system produces a materially better one — and does this
merely need organizational implementation, or does it expose a weakness in the
theory (in particular, is "optimize the engineering system" too strong)?

Sources consulted: `01-principles/02-design-the-engineering-system.md`,
`00-foundations/design-doctrine.md`, `03-architecture/composition.md`,
`02-capabilities/ownership-and-authority.md`, `02-capabilities/output-and-outcome.md`,
`03-architecture/observation.md`, `02-capabilities/learning.md`,
`01-principles/06-close-the-loop.md`, `03-architecture/federation.md`,
`04-operating-model/README.md`, `04-operating-model/planning-staffing-funding.md`,
`08-anti-patterns/ticket-count-as-the-score.md`,
`08-anti-patterns/convergence-as-a-function.md`, `00-foundations/open-questions.md`.

## 1. The problem

A capability owner optimizing its own contract can be individually competent,
unbroken, and within its authority, and the composed system can still be worse
than it should be — and correcting that can require some owner to accept a
locally worse metric (cost, SLA, near-term delivery) for a better system
outcome. No one is incompetent; the incentives are simply misaligned. The
question is whether the theory can still claim to "optimize the engineering
system" when it neither controls those incentives nor can compel the trade.

## 2. What the corpus already claims

The corpus is not naive about this. It states the condition, names the
requirement, and refuses the mechanism:

- **Names the failure directly.** `04-operating-model/README.md`: *"System-level
  dysfunction may exist that no individual capability owner is incentivized or
  authorized to correct."* This is the exact problem, admitted in canon.
- **Makes incentive compatibility a stated requirement, not an assumption.**
  Repeated verbatim in the operating model and in `planning-staffing-funding.md`:
  *"Convergence requires incentive compatibility, not merely technical
  compatibility."* The theory does **not** assume incentives align; it names
  their alignment as a precondition it depends on.
- **Names the local↔system relation.** Principle 2: *"Optimize the path from
  intent to outcome. Do not optimize the local efficiency of a queue, a team, or
  a handoff as if that were the system."* Funding table: *"Local budget
  optimization → a locally cheap choice that is expensive for the system."*
- **Keeps the objective multi-dimensional.** Design doctrine: *"Judge the
  engineering system by how effectively it converts intent into outcomes while
  preserving necessary expertise, authority, judgment, accountability, context,
  constraints, and learning."* "Better" is explicitly not "faster."
- **Caps its own epistemic claim.** `observation.md`: the structure can *"make
  evidence explicit and attributable, so that not acting is visible as a
  decision. It cannot make the decision."* Principle 6: *"Learning informs
  change; it does not automatically mandate change."*
- **Locates stewardship without prescribing it.** *"Stewardship should exist at
  the level where the concern exists,"* and no council/office/role is prescribed
  (`convergence-as-a-function.md`).
- **Parks the mechanism.** `open-questions.md` files *incentive compatibility*
  and *system-level stewardship (organizational implementation)* as unsolved and
  explicitly declines budgeting/chargeback/compensation/procurement.

So the theory already contains the *diagnosis*, the *requirement*, the
*multi-objective judgment*, the *epistemic limit*, and the *bounding*. What it
does not contain — deliberately — is a mechanism to produce alignment.

## 3. Worked hostile examples

Each is stipulated so no one is incompetent and no authority is violated.

- **Platform (the base case).** Continue clearing 1,000 in-SLA requests, or spend
  three months building a shared capability that eliminates 700 of them while
  its own SLA and backlog worsen. Locally rational: A. Systemically rational: B.
- **1 — Security.** A reusable control removes three days of downstream
  coordination but worsens the security team's quarterly delivery metric.
- **2 — Infrastructure.** Accepts higher *direct* cost to provide a capability
  that removes larger costs spread across product teams.
- **3 — Product.** Spends its own capacity improving a shared capability whose
  value accrues mostly to *other* product teams.
- **4 — Reliability.** SRE asks a product team to accept slower features now to
  reduce system-level operational risk later. Here "better" is *risk*, not
  speed — and the sacrifice runs the other direction (delivery yields to
  reliability).
- **5 — Regulated domain.** A domain *should* refuse the globally faster option
  because its obligation is intentionally independent. "Globally better" must not
  collapse into "faster," and the corpus already forbids overriding this.
- **6 — Federation.** Org A bears the cost; Org B captures the benefit; neither
  has authority over the other.
- **7 — AI / agent consumption.** A specialist domain must invest to make its
  expertise safely agent-consumable while most productivity gain appears
  elsewhere. Structurally identical to Platform/Infrastructure.

The common shape: cost concentrates on one owner; benefit disperses across the
system; and in cases 4 and 5 the *objective itself* (risk, independent
obligation) is not delivery speed. The corpus handles the *structure and the
constraints* of every case. In every case the residue is the same: who is
motivated and authorized to make the trade.

## 4. Local rationality vs. system rationality

The corpus already frames the divergence correctly and refuses the naive
resolution. It rejects local metrics as the score (`ticket-count-as-the-score.md`),
insists the path is the unit of optimization (Principle 2), and warns that
activity metrics reward handoffs and that "local budget optimization can conflict
with engineering-system optimization." What it cannot do is *close* the
divergence: a rational local owner can read all of this and still choose A,
because the theory gives no mechanism that changes what A is measured on. The
divergence is described precisely and left unresolved by design.

## 5. Authority constraints

The safeguards against "system optimization" becoming a mandate to override
owners are strong and already present:

- Domain authority and ownership **do not transfer through composition**
  (`composition.md`); a composite cannot promise more than contributors permit,
  and the honest responses are narrow / refuse / route — never override.
- *Converge where outcomes require coherence; preserve autonomy where they
  don't* (Principle 2, `federation.md`). Untidiness is not a reason to converge.
- A central optimizer is the named anti-pattern (`convergence-as-a-function.md`).

Consequence for question 5: system optimization **cannot** legitimately license
a central authority to override a domain owner, because the model gives no such
authority and explicitly forbids the composite from acquiring it. Consequence
for question 6: domain authority is a *hard upper bound* on system optimization —
"globally better" is only reachable within what every contributing authority
permits. Consequence for question 7: local optimization is *correct* precisely
when the local domain exists to protect an independent obligation (regulation,
separation of duties, independent authority), which the design doctrine's
intentional-constraint reasoning already protects.

## 6. Evidence and observability

This is where the theory is strongest and where its honest claim actually lives.
`observation.md` already routes attributed cross-composition evidence to where it
can be acted on, insists silence is not health, counts abandonment and
conversation, and — critically — states the ceiling: make **not acting visible as
a decision**; do not pretend to make the decision. `ticket-count-as-the-score.md`
adds the honest measurement caveat: *"'The engineering system moves intent to
outcome more effectively' does not fit in a quarterly review."*

So on questions 3, 4, 8, 9, and 10:

- **Recognition** of "locally worse is globally better" can be produced by
  outcome ownership plus attributed observation (elapsed time counted honestly
  including work driven into informal channels, coordination cost, downstream
  effects, exception and abandonment volume as information — multi-objective, not
  a single score).
- **Determination and action**, however, require motive force the model does not
  supply. Outcome ownership gives recognition, not leverage over contributors.
  Composite ownership gives seam levers (narrow / refuse / route) and attributed
  evidence, not the power to change a contributor's incentives. **Neither owner
  can change another owner's incentives; both can only make the misalignment
  observable and attributable.** That is the model's real, bounded contribution.

## 7. Economics and funding

The corpus is explicit and disciplined: it names the funding failure modes
(per-team budgets starve seams; adoption-as-target corrupts platforms; local
budget optimization is system-expensive; commercial contracts encode delivery
boundaries), states that *"a capability must not exist to justify its
realization,"* and then **refuses to prescribe** budgeting, chargeback, showback,
cost allocation, compensation, or procurement. The adversarial rule holds here:
none of chargeback/central platform funding/EA authority is assumed, and the
note does not introduce them. Funding is named as a boundary-drawing force and
left to organizations.

## 8. Federation

Variation 6 is the sharpest. Stewardship-at-scope says the concern should be
owned "at the level where the concern exists" — but across a federation boundary
that level may have **no shared authority at all**. `federation.md` is explicit
that no coordinating body is required and that only obligations/constraints cross
the boundary. So the theory correctly *locates* the concern and correctly
*refuses* to invent a supra-authority — which means, honestly, that in the
federated case it can make the asymmetry observable and can support a negotiated
obligation at the boundary, but it cannot resolve who pays. That is a limit the
theory owns rather than hides.

## 9. Does "optimize the engineering system" survive literally?

Tested hard: it survives as a **directional / unit-of-reasoning claim**, not as a
claim of achieved or computed optimization — but only because the surrounding
canon hedges it, and those hedges are currently implicit and scattered.

- The corpus never claims to *compute* a global optimum, and its multi-objective,
  selective-convergence, preserve-autonomy language is inconsistent with there
  being one global optimum to compute. (Adversarial rule satisfied: no single
  knowable optimum is assumed.)
- The corpus never claims to *compel* the trade — `observation.md` explicitly
  disclaims it.
- The corpus already names incentive compatibility as a **required precondition**,
  so it does not assume alignment.

Given all three, "optimize the path from intent to outcome" reads as "treat the
system/path as the objective and the unit of reasoning," which is defensible.
**What is not defensible is the *misreading*** — that Convergence *delivers*
system optimization irrespective of incentives. The theory does not make that
claim, but nothing in one place prevents a reader from hearing it, and the
theory's own admission ("dysfunction may persist that no owner is incentivized or
authorized to correct") sits in a different document from the optimization
language. The word does not need to be *weakened*; its **dependency needs to be
made explicit**. Weakening "optimize" alone would actually lose a correct claim
(that the system is the right thing to optimize *for*) while leaving the
misreading intact.

## 10. What the theory can legitimately require vs. what organizations decide

- **Legitimately the theory's to require/claim:** that the system/path is the
  correct unit of reasoning and design; that incentive compatibility is a
  precondition for system-level results; that system-level tradeoffs be made
  observable, attributable, and reason-able so that not acting is a visible
  decision; that domain authority is a hard constraint on any system-level
  change; that "better" is multi-objective.
- **Organizations' to decide (theory should bound, not solve):** budgeting,
  chargeback/showback, cost allocation, compensation and performance metrics,
  procurement, headcount, and who is empowered to authorize and fund a
  locally-worse/globally-better trade. These are leadership, org-design, and
  economic choices the theory deliberately declines.

## 11. Strongest case that this is only an implementation problem

Everything conceptual needed to *reason about* the misalignment already exists:
the unit of optimization, the requirement of incentive compatibility, attributed
observability, multi-objective judgment, domain-authority constraints, and
stewardship-at-scope. The only thing absent is a *mechanism to align incentives*,
which is intrinsically organizational and economic (budgets, metrics, leadership,
org design). The theory already names it, bounds it, and parks it. On this view
nothing in the model is incoherent; organizations simply have to do the
non-technical work, exactly as the corpus says.

## 12. Strongest case that this exposes a conceptual gap

The theory *requires* a precondition it cannot produce and does not, in one
place, tie that dependency to its strongest verb. "Optimize the engineering
system" is stated as the objective; the admission that optimization may be
unreachable absent incentives sits elsewhere; and the model's actual deliverable
(observability, not enforcement) is stated in a third place. A rigorous reader
can therefore extract an over-claim by composition even though no single sentence
makes it. That is not a *missing concept* (incentive compatibility is already in
the model as a named requirement), but it is an unstated *conditionality* between
the optimization claim and that requirement. Left implicit, it makes the
system-optimization claim look stronger than the theory can defend.

## 13. Smallest statement the theory would need (if clarification is required)

Not to be added now. The minimal, concept-free clarification would say, in one
place near the optimization language:

> System-level optimization is what Convergence reasons and designs *toward*; it
> is the unit of reasoning, not something the model computes or can compel.
> Convergence *requires* incentive compatibility as a precondition and does not
> supply it. Where incentives are misaligned, Convergence's contribution is to
> make the system-level tradeoff observable, attributable, and reason-able — so
> that failing to act is a visible decision — while domain authority remains a
> hard constraint and "better" remains multi-objective, not "faster."

This introduces no role, mechanism, or model element; it only links claims the
corpus already makes (unit of reasoning; incentive compatibility as requirement;
observation makes not-acting visible; domain authority as constraint;
multi-objective judgment).

## 14. Remaining unanswered questions (correctly left open)

- Who is authorized and motivated to decide a locally-worse result is globally
  better, and to fund it, when cost and benefit fall on different owners?
- How does an emergent, cross-domain concern acquire stewardship at a scope that
  may have no shared authority (esp. federation)?
- How is system-level effectiveness expressed honestly for decision-makers
  without collapsing into a single score (the `ticket-count` tension)?

These remain the parked *incentive compatibility* and *system-level stewardship*
questions. This note does not answer them.

## 15. Verdict

**B. Existing theory needs clarification but no new concept.**

The theory already contains everything needed to *reason about* incentive
misalignment — the unit of optimization, incentive compatibility as a named
requirement, attributed observability, multi-objective judgment,
domain-authority constraints, and stewardship-at-scope — and it correctly caps
its own claim to "make not acting a visible decision." No concept is missing (not
D). The claim is not false and need not be softened at the word level (not E as
primary). It is more than merely an implementation concern to bound (C is true
but shallower). And it is not already fully handled, because the *conditionality*
between "optimize the engineering system" and the incentive-compatibility
precondition is implicit and scattered across documents (not A).

**Why B over the near-misses.**
- **E is secondary.** "Optimize" is defensible as a directional / unit-of-reasoning
  claim given the existing hedges; the honest fix is to state the dependency, not
  to weaken the verb (which would discard a correct claim and leave the misreading
  intact). E only becomes correct if one refuses to add the clarification — in
  which case the language would indeed overstate.
- **C is secondary/subsumed.** Yes, the *incentive mechanism* is an implementation
  concern the theory should bound and not solve — and it already does. But C alone
  does not address the intellectual-defensibility of the optimization claim; the
  deeper point is that the theory must explicitly acknowledge its dependency on
  that bounded concern. B contains C's conclusion (mechanism stays out of scope)
  and adds the missing linkage.
- **D rejected.** The model can fully locate and describe the misalignment with
  existing constructs; what is absent is a deliberately-excluded mechanism, not a
  concept required for coherence.
- **A rejected.** The dependency is real and currently unstated in one place.

The deepest accurate reading is therefore B: a single clarifying linkage —
using only concepts already in the corpus — would make the system-optimization
claim fully defensible, and no new theory, role, or economic mechanism is
warranted.

## Recurring natural language (observations only — not name proposals)

- incentive compatibility
- misalignment
- local rationality / system rationality
- trade / trade-off
- observable / attributable / reason-able
- precondition
- stewardship at the scope of the concern
- multi-objective ("better" is not "faster")
- unit of optimization / unit of reasoning
