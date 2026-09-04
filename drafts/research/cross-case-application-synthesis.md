# Cross-case application synthesis

*Non-canonical research artifact. Evidence extraction from three worked
cases. Not a methodology, not named, not canonical application guidance,
not a revision of theory.*

**Question.** When this body of knowledge was actually useful across three
materially different problems, what did we repeatedly *do*?

**Evidence base (limitation, stated first).** All three cases were written
to long, similar section lists that already tracked the conceptual model
(intent → path → capability → experience/realization → composition →
authority → friction → observation → incentives → improved state →
wrong success → distinctiveness). Reconstructing "the order reasoning
occurred" therefore partly reconstructs the *assignment*, not an
independent field practice. This synthesis treats as **method-relevant**
only moves that changed a diagnosis or protected a design against a named
failure. Moves that appeared because the prompt asked for them, but did
little work, are classified incidental.

Cases:

1. Enterprise cloud onboarding (mature tooling; 4–8 week traversal)
2. Security/governance (pressure to remove friction / "platformize approval")
3. Production reliability/learning (locally green composition outage)

Shared case verdicts: useful as system-level reasoning and wrong-success
guardrails; therapy overlaps existing PE/DevOps/SRE/DevSecOps/TT
mechanisms.

---

## Phase 1 — Reconstruct each case

### Case 1 — Cloud onboarding

**Presented problem.** Onboarding a customer-facing production workload
takes 4–8 weeks despite CI/CD, IaC, IDP, scanning, identity, observability,
standards, service ownership, Team Topologies-style teams.

**Obvious/local solution.** Better portal / more self-service / more
automation / "the platform should own onboarding."

**How scope changed.** From "the platform" or "ten request types" to **the
engineering system for the class of intent** "eligible customer-facing
workload live under known constraints" — not the whole enterprise.

**Unit of reasoning.** That scoped system / candidate composite
(`OnboardRoutineCustomerWorkload`), not team SLAs.

**Distinctions that did work.** Org as delivery API; experience vs
realization (portal opens tickets); capability exists without automation
(human security review); accidental routing vs intentional SoD/novel
review; settled treated as novel (security calendar); unowned composite
seams; authority discoverable vs required for routing; local SLA vs path
elapsed time; steward cost vs distributed benefit.

**Assumptions challenged.** Mature IDP + TT ⇒ delivery system is designed.
Each team hitting SLA ⇒ system is fine. Capability ⇒ API.

**Wrong success exposed.** Portal adoption / ticket UX without changing
realization chain; team SLAs green, 4–8 weeks intact.

**Design that changed.** Not "build an IDP" (they have one). Name composite
and seams; one declaration; encode S1; keep independent prod auth and
novel collaboration; exception path; portal only if it is not eight
tickets.

### Case 2 — Security/governance

**Presented problem.** Security reviews delay releases. Proposal: move
security into the platform and automate approval. Product hears "pipeline
green ⇒ Security is done."

**Obvious/local solutions.** Automate all approval **or** defend every
existing gate as "security."

**How scope changed.** From "reduce review latency" / "Security the
bottleneck" to the system through which a **production change becomes an
accepted production outcome** — multiple non-collapsible intents
(customer, engineering, security, regulatory).

**Unit of reasoning.** Multi-objective engineering system for that class
of change; not review SLA.

**Distinctions that did work.** Accidental delay *around* intentional
approval (assignment wait vs SoD); experience vs realization splitting
the slogan into A/B/C; execution ≠ authority; settled vs novel as
*examination* not detector; capability ≠ automation; composite cannot
override security; challengeable encoding; learning ≠ action.

**Assumptions challenged.** Faster ⇒ better. Pipeline execution ⇒
security authority. "Put it in the platform" is one design. All human
review is SoD. All delay is waste.

**Wrong success exposed.** Review SLA / deploy frequency / coverage % /
portal adoption / ticket volume up while judgment, exceptions, and
authority disappear (automate too much) *or* specialists burn on S1
(automate too little).

**Design that changed.** Split S1 attest vs novel vs exception; encode
mechanical controls; keep independent auth and named residual risk;
evidence pack from the path; living review of encodings. Not "security
platform" as definition.

### Case 3 — Reliability/learning

**Presented problem.** Major outage. No contributor obviously violated
local expectations. Dashboards can be green. Interaction of retries,
token refresh, timeouts, DB cap, plus a deploy.

**Obvious/local solutions.** Blame the red-ish component (DB); raise
`max_connections`; add dashboards/alerts; SRE/platform owns all knobs;
permanent CAB freeze.

**How scope changed.** From "the app," "SRE," or "the incident" to the
system for **keeping (and changing) the customer lookup path in an
accepted production state.**

**Unit of reasoning.** Composite runtime path; **seam** as the failure
locus, not a service.

**Distinctions that did work.** Output / local success / composite
success / customer outcome; parts ≠ whole; unowned seam; authority ≠
execution in IR; encoded expertise challengeable (handbook independence
assumption); observation ≠ evidence ≠ learning ≠ action; freeze as
temporary intentional vs permanent accidental; wrong success of scaling
the cap.

**Assumptions challenged.** Local contract hold ⇒ system hold. Root cause
is a component. Settled retry guidance is safe in every composition.
More observability boards fix attribution.

**Wrong success exposed.** Component capacity up, recurrence remains;
MTTR down, same failure mode; freeze becomes the new org API.

**Design that changed.** Name the seam; change defaults where domains
agree; composite constraint on shipping all knobs at once; minimal joined
observation; challenge the handbook. Not a new control plane.

---

## Phase 2 — Cross-case recurrence

### All three cases (did useful work)

| Move | Question | Failure exposed | Enabling distinction | Decision changed/protected | Kind |
| --- | --- | --- | --- | --- | --- |
| Scope to a class of intent, not a team/tool | What system is this actually about? | Optimizing platform, Security, or SRE as if they were the system | Unit of reasoning = engineering system for a class of intent | Refused "build a platform / give it to Security / SRE owns all knobs" as the definition | Diagnostic |
| Separate local success from system/outcome | Can every part be fine and the whole still fail? | SLA/dashboard/review-time theater | Local vs system; output vs outcome; parts ≠ composition | Kept end-to-end / customer outcome as the score | Diagnostic |
| Identify implicit capabilities (incl. human-realized) | What can the system already accomplish? | "We don't have a capability until it's an API" | Expertise vs capability; capability ≠ automation | Kept human review/assessment as a capability with a bad realization | Diagnostic |
| Split experience from realization | Did we change how it's used or how it's fulfilled? | Portal / pipeline / dashboard cosmetics | Experience vs realization | Refused A (new front door, same routing) | Diagnostic + design |
| Classify friction (delay ≠ waste) | What value does this interaction provide? | Delete SoD/novel review **or** keep every queue | Accidental vs intentional vs contextual | Strip routing; keep independent obligation and novel judgment | Diagnostic + design |
| Settled vs novel as examination | Is this repeatable *enough to encode*, and who judges? | Automate approval because the form is familiar; or never encode | Encode/collaborate; domain authority decides; can become novel again | Split S1 vs novel; challenge handbook after incident | Diagnostic + design |
| Name composition / seams / unowned coherence | Who is accountable for the interaction? | Consumer or IC as integrator; blame a component | Composite vs contributor; seam vs component | Name seam ownership without domain takeover | Diagnostic + design |
| Preserve authority while changing execution | Who may decide vs who may perform? | Pipeline/platform/SRE becomes the authority | Authority ≠ execution; domain vs capability vs outcome | Distributed execution, independent refuse/SoD | Design |
| Ask what would look like success and still be wrong | Which metric can improve while the outcome/system does not? | Adoption, coverage, capacity, MTTR, review SLA | Local metric vs intent-to-outcome while preserving constraints | Chose different evidence; refused several therapies | Observational / iterative |
| Minimum mixed mechanisms, not one product | What is the smallest change to *what is depended on*? | Default to IDP / security platform / control plane | Realization is many forms | Git, docs, policy, humans, exceptions, some automation | Design |

### Exactly two cases (useful, not universal)

| Move | Cases | Notes |
| --- | --- | --- |
| Org chart as routine delivery API / traversal | 1, 2 (and IR routing in 3) | Core in onboarding; present in security queues; in reliability mainly *during IR*, not the originating failure |
| Slogan/proposal disambiguation (A/B/C) | 2 primarily; 1 as portal-as-router (a subset of A) | Load-bearing in security; the onboarding portal is the same pattern with less political heat |
| Execution impersonates authority | 2 (pipeline); 3 (less: deploy success ≠ healthy composition) | Strongest in security; reliability is "local contract ≠ system" more than "check = authority" |
| Incentive: cost on steward, benefit elsewhere | 1, 2 (3 mentioned politics blocking action, thinner) | Named, not solved |
| Learning loop / challengeable encoding as the *plot* | 2 (stale S1), 3 (retry handbook); 1 as observation table only | Load-bearing in 3; protective in 2; supporting in 1 |
| Independent organizational separation as governance value (SoD) | 1, 2 | Reliability: DB cap is analogous *constraint*, not org SoD |

### Only one case (situational)

- **Onboarding:** declaration vs eight queues as the improved *experience*; IDP already present as the trap.
- **Security:** explicit A/B/C of "platformize"; SoD as first-class; AI amplifying C; regulatory intent as a fourth non-collapsible intent.
- **Reliability:** emergent all-green failure; IR collaboration vs coordination; observation of *composition edges*; blame-component vs freeze-org; closest SRE/RE overlap.

Canonical ideas that existed but did **little unique work** in the cases:
full capability graph, maturity scores, federation as a worked structure
(mentioned, not exercised), contract schemas, scoring.

---

## Phase 3 — Necessity test

| Candidate | Class | If removed |
| --- | --- | --- |
| Scope to class of intent / engineering system | **A Load-bearing** | Case 1 stays "fix the portal"; case 2 stays "reduce review time"; case 3 stays "fix the DB." |
| Local success vs system outcome | **A Load-bearing** | Wrong-success is invisible; all three diagnoses collapse. |
| Experience vs realization | **A Load-bearing** (1, 2); **B Useful** (3) | Case 1 cannot indict the IDP; case 2 cannot split A/B/C. Case 3 still works via parts≠whole. |
| Accidental vs intentional friction | **A Load-bearing** (1, 2); **B Useful** (3 freeze) | Case 2 becomes automate-all or keep-all. Case 1 deletes SoD or keeps ten tickets. |
| Composite / seams / unowned coherence | **A Load-bearing** | No place for "nobody owns the traversal/interaction" without a czar or a blamed team. |
| Authority ≠ execution | **A Load-bearing** (2); **B Useful** (1, 3) | Case 2 cannot refuse C. Cases 1 and 3 still diagnose routing/seams. |
| Settled vs novel (examination) | **A Load-bearing** | Security calendar and retry handbook both get the wrong therapy. |
| Capability ≠ automation / implicit capabilities | **B Useful** | Without it, "automate security" or "we have no capability." Not the *only* path to the same design, but it blocked a false fork. |
| Encode/collaborate | **B Useful** (design implication of settled/novel) | Follows from settled/novel; skipping the *forms* list wouldn't lose the diagnosis. |
| Abstract routing, not accountability | **B Useful** | Restates authority+experience; protective phrasing, not an independent discovery. |
| Output vs outcome | **B Useful** (3); **C Supporting** (1, 2) | Essential to the reliability writeup; onboard/security used "local vs system" more than the output/outcome vocabulary. |
| Observation vs learning vs action | **A Load-bearing** (3); **C Supporting** (1, 2) | Case 3's intellectual payload. Others used it as a table. |
| Coordination vs collaboration | **B Useful** | Named the IR war room vs queue-hunting; security/onboarding used it as a column. Skippable if accidental/intentional is done well. |
| Incentive compatibility | **C Supporting** | Explains why encoding doesn't happen; none of the three *designs* depended on solving it. Protective honesty, not a method step. |
| AI stress | **D Incidental** as method | Raised the cost of C in case 2; not used as an application move in 1 or 3's core. |
| Full accountabilities matrix (every row) | **C Supporting** | Clarified case 3; onboarding didn't need every cell filled to reach the design. |
| Federation recursion | **D Incidental** in this evidence | Asserted, not demonstrated. |

---

## Phase 4 — Natural shape

**Not a fixed linear sequence** that an engineer must walk in numbered
order. The prompt order was linear; the *dependencies* that actually
mattered are:

1. **You cannot classify the portal, the pipeline, or the DB metric until
   you have named the system and the intended outcome.** Intent/scope
   first is not only canonical bias — in all three, the local framing
   (portal, review latency, component RCA) was the trap.
2. **You cannot classify friction or encodings until you have a current
   path / current composition.** Trace (or equivalent: "what actually
   happens") is diagnostic prerequisite.
3. **Distinctions are applied where the proposal is tempting**, not as a
   complete inventory. Case 2 needed authority≠execution more than case
   1; case 3 needed parts≠whole more than a portal analysis.
4. **Wrong-success is a recurring check**, not a last chapter. It is
   applied to the *obvious solution* early and to the *improved state*
   late.
5. **Learning/iteration is the natural end when the problem is
   invalidation** (case 3, stale S1). For onboarding it was a
   *should-observe* appendix. So Outcome/Evidence/Learning is a genuine
   end for failure/invalidation problems, and a **continuing obligation**
   for design problems — not always the dramatic last act.

**Inferred shape:** a **diagnostic pass** (what system, what outcome,
what happens now, local vs system) → **distinction pass** (only the
distinctions the tempting answer violates) → **design pass** (change
what is depended on; preserve authority and intentional constraint) →
**observational pass** (what would fake success; what evidence would
show the system moved). Optionally **iterate** when evidence invalidates
encodings.

That is closer to **nested / opportunistic loops** than to a lifecycle
or a teaching sequence. It is not "questions in no order": skip intent
and you solve the wrong problem. It is not strictly Intent→…→Learning as
the *method*: Learning was load-bearing in one case and supporting in
two.

**Did reasoning naturally begin with INTENT?** Yes, in the sense of
"don't accept the presented KPI as the intent." Customer/engineering/
security/reliability intents were separated because collapsing them *was*
the local optimization.

**Did it naturally end with OUTCOME / EVIDENCE / LEARNING?** It ended
with an **improved state plus wrong-success tests** in all three. Formal
learning-loop tracing was the spine only of case 3.

---

## Phase 5 — Conceptual model as application method

**B. It provides the skeleton but additional reasoning moves are required.**

The loop (intent → capability → experience/realization → outcome →
learning) **oriented** every case: class of intent, implicit
capabilities, experience/realization split, outcome vs local output,
learning as belief change.

It is **not already the practical method** (not A): engineers still had
to apply friction classification, composite/seams, authority≠execution,
settled-as-examination, and the wrong-success check — none of which are
*steps* of the loop, even though they attach to it.

It is **not a totally different shape** (not C): we did not apply a
rival sequence (e.g. start from org chart redesign, or from SLO only).

It did **more than little work** (not D): without "what can the system
accomplish" vs "how it's fulfilled/consumed," cases 1 and 2 lose their
sharpest diagnoses.

The extra moves are mostly **design doctrine + principles 1, 3, 4, 5 +
composition/observation**, i.e. the rest of the v0.1 core, not a new
method layered on.

The repo already has a method section (trace / evaluate / identify /
decide / design / operate). These cases look like **that method plus an
explicit wrong-success / local-vs-system check**. That is important: we
may be rediscovering `docs/12-method` rather than discovering a new
application structure. The cases did not independently derive "trace
then evaluate"; they were asked to trace, then classify, then design.

---

## Phase 6 — Distinctions that actually mattered

| Distinction | Classification | Evidence |
| --- | --- | --- |
| Local success vs system outcome | **Repeatedly load-bearing** | All three; the recurring payload |
| Experience vs realization | **Repeatedly load-bearing** | Portal; slogan A vs B vs C; post-incident same deploy UX vs new refusal |
| Accidental vs intentional friction | **Repeatedly load-bearing** | Onboarding tickets vs SoD; assignment wait vs approval; freeze vs encode |
| Composite vs contributor / seam vs component | **Repeatedly load-bearing** | Unowned path; unowned retry×token×cap; cannot override security |
| Authority vs execution | **Situationally load-bearing** | Essential in security; clarifying in IR; less decisive in onboarding diagnosis |
| Domain vs capability owner vs outcome owner | **Situationally load-bearing** | Needed to avoid "platform owns security" and "SRE owns identity"; onboarding used a lighter version |
| Settled vs novel expertise | **Repeatedly load-bearing** | Security calendar; retry handbook; S1 vs novel |
| Expertise vs capability | **Useful vocabulary** | Blocked "not a capability until automated"; a skilled reader might say "the org can already do X" without the word |
| Capability vs realization | **Repeatedly load-bearing** | Same as what vs how; paired with experience split |
| Encoded vs living expertise | **Situationally load-bearing** | Spine of case 3 and stale-S1; supporting in onboarding observation |
| Coordination vs collaboration | **Useful vocabulary** | IR and "duplicated interpretation wearing collaboration's clothes" |
| Output vs outcome | **Situationally load-bearing** | Case 3; elsewhere "local vs system" carried the weight |
| Observation vs learning | **Situationally load-bearing** | Case 3 |
| Learning vs organizational action | **Situationally load-bearing** | Case 3; incentives in 1–2 |
| Abstract routing not accountability | **Useful vocabulary** | Protective restatement of authority + discoverability |

No distinction from the list demonstrated **zero** value; several are
vocabulary for a load-bearing move already named. **Federation, graphs,
contracts-as-schema** had little demonstrated practical value *in these
three writes*.

---

## Phase 7 — Wrong success

**Structure (not a new named concept):** a change improves a **local,
visible, owned metric or artifact** that is *correlated* with the
problem while the **conversion of intent to outcome**, **composition
coherence**, or **preserved constraints/authority** does not improve —
and often degrades.

Manifestations in the cases:

- Better experience, same realization/routing (portal, extra form).
- Contributor optimized, composition the same or worse (team SLA, DB
  cap, review SLA).
- Execution automated, authority confused (pipeline green).
- Intentional friction removed because it was slow (SoD, novel judgment).
- Symptom component fixed, seam unsafe (raise connections).
- Controls added that become permanent accidental routing (post-incident
  CAB).
- More signals (dashboards, alerts, coverage %) without seam attribution
  or exception visibility.

**Deeper pattern:** optimizing a **proxy that a specialist team or
tooling program can move** instead of the **scoped engineering system's
outcome under its legitimate constraints.**

**Question that consistently reveals it:**

> After this change, what can get better on a dashboard while a consumer
> still cannot achieve the intent, or while a constraint/authority that
> should hold no longer holds?

Or shorter: **What will look like success if the system did not actually
improve?**

That question worked in all three. It is diagnostic *and* a stopping
test on the proposed design.

---

## Phase 8 — The design move (what happened after diagnosis)

Recurred, in relationship (not a step list):

- **Scope** around a class of intent — *first*, or the design solves the
  KPI.
- **Identify existing implicit capabilities** — so design is
  re-realization, not invention from zero.
- **Separate stable WHAT from HOW** and **experience from realization**
  — so the design changes dependence, not necessarily the org or the
  portal.
- **Identify routing vs obligation** (friction class) — so the design
  does not delete SoD/novel/security refusal.
- **Encode only after examination; keep collaboration for novel** —
  design split (S1 vs exception).
- **Name composition and seams; do not take domain authority** — design
  of accountability.
- **Improve observation toward the system/seam/outcome**, not more local
  boards — design of evidence.
- **Minimum mixed realizations** — docs, Git, policy, humans, some
  automation.

**Did not recur as a mandatory design block:** new platform; reorg;
chargeback; full catalog; AI; federation architecture.

**Order after diagnosis was not unique:** case 1 designed the declaration
path; case 2 designed the S1/novel/exception split; case 3 designed seam
constraint + encoding challenge. Same *kinds* of move; different
emphasis.

---

## Phase 9 — Recursion and scale

| Scale | Evidence in the cases |
| --- | --- |
| One capability | Yes: environment, S1 attest, retry defaults, storage cap — analyzed as leaves |
| Composite | Yes: all three named a composite and seams |
| Product value flow | Partial: claim-status API as the running example, not a full value-stream map |
| Domain | Yes: security domain, identity, data — as authorities, not as the unit of optimization |
| Enterprise | Assumed setting; **not** an enterprise-wide application of the method |
| Federation | **Theoretical only** — mentioned as compatible, not worked |

Recursion of the *lens* (apply the same questions to a leaf or a
composite) is **demonstrated**. Recursion across enterprise/federation
is **not demonstrated** by these cases. Canonical theory claims it;
this evidence base does not prove it.

---

## Phase 10 — Entry conditions and when not to use it

**Appears most valuable when several of these hold:**

- Multiple specialized domains participate in one intent-to-outcome.
- Local teams/tools look successful; outcomes or elapsed system
  performance do not.
- A portal, pipeline, platform, or dashboard is offered as the fix.
- Automation or "shift left" risks erasing independent authority.
- Repeated expertise is consumed through people (or through stale
  encodings).
- Failure or delay is interaction/seams, not a single broken owner.
- Nobody owns composite coherence.
- Metrics reward local success.
- The tempting answers are reorg, central platform, or delete the
  specialist function.

**Probably unnecessary overhead when:**

- A single team owns intent, realization, and outcome (startup, one
  service, no specialist supply chain).
- The problem is a known bug, capacity shortfall, or skill gap *inside
  one domain* with no composition story.
- The work is genuinely novel end-to-end (research), and the need is
  collaboration, not a delivery API.
- You are choosing a library version or a vendor SKU with no
  organizational routing.

Using the full distinction inventory on those problems would be
ceremony. The cases are all **multi-domain, mature-tooling,
wrong-success-prone** enterprises. That is the demonstrated niche, not
a universal engineering method.

---

## Phase 11 — Prior-art test

A skilled practitioner **could assemble much of the same reasoning**
from:

- **Systems thinking:** local vs global, don't optimize the part.
- **Value-stream mapping:** elapsed time, wait, rework, the consumer as
  integrator.
- **Platform Engineering:** golden path, cognitive load — with a known
  failure mode (portal-as-router) this lens names.
- **Team Topologies:** XaaS vs collaboration.
- **DevSecOps / policy-as-code:** encode controls, shift left — with a
  known failure mode (pipeline = authority).
- **SRE / resilience engineering:** SLO, interaction failure, blameless
  PIR, don't add blunt controls.
- **Intent-based approaches:** declare desired state, automate how.

**Could they assemble it as one pass across onboarding + security
politics + composition outage?** Unusually yes if the person is already
fluent in several of these. **Usually no** — those practices are
applied in different rooms (platform program, security transformation,
SRE incident). The cases' value was a **single lens that refused the
room's default KPI** in all three rooms.

**Application value: B. Coherent synthesis of reasoning usually
distributed across disciplines.**

Not A (distinct method with unique moves unknown to those fields).
Not merely C if "checklist" means generic quality questions — the
wrong-success question and experience/realization split are specific
enough to change proposals. Not D: slogan PE/DevSecOps/SRE commonly
*are* the wrong-success modes the cases describe.

Synthesis is not novelty. The cases keep saying that.

---

## Phase 12 — Method vs checklist

A method would need: starting condition, unit of reasoning, dependencies
between moves, decisions from observations, feedback, stopping
conditions.

**Present:**

- Starting condition: multi-domain intent-to-outcome looking locally
  fine or locally "too slow," with a tempting proxy fix.
- Unit: engineering system scoped to a class of intent.
- Some dependencies: scope before therapy; path before friction class;
  tempting answer before which distinction to apply.
- Feedback: learning/wrong-success as re-entry (strong in case 3).
- A weak stopping idea: improved state uses minimum mechanisms;
  intentional constraints remain; proxy metrics are not the score.
  **No operational "we're done" test** (how much latency, how much
  encoding) — by design of the theory, and still missing for practice.

**Absent or weak:**

- Forced order of all distinctions (and forcing one would be false).
- A unique inference rule from observation to decision (practitioner
  judgment dominates: what is S1, who owns the composite, whether to
  freeze).
- Evidence that someone *without* the 20-section prompt converges on
  this — the dependencies we see are partly prompt-shaped.

**Finding:** this is **more than a random checklist** (there is a unit,
a starting trap, and a wrong-success stop-check) and **less than a
mature method** (no field-proven sequence, no sufficiency test, heavy
judgment, existing `12-method` not independently rediscovered).

Do not manufacture more dependencies to promote it.

---

## Phase 13 — What is missing for practical use

| Need | Kind |
| --- | --- |
| How to pick and bound a class of intent without boiling the ocean | **Application guidance** (method docs start this; cases always used a pre-chosen API) |
| How to trace a real path (interviews, tickets, elapsed time including chat) | **Application guidance** |
| How domain authority *judges* settled vs novel in practice | **Under-specified theory + application**; parked as examination not detector |
| How an unowned composite acquires a steward | **Organizational implementation** (open question) |
| Incentive/funding for encoding | **Organizational implementation** |
| What evidence is enough to call improvement | **Application guidance**; theory refuses a score — practitioners still need signals |
| Facilitating multi-domain analysis without a Convergence function | **Application guidance / org** |
| Instrumenting composition edges | **Open question** (emergent composition risk) + SRE practice |
| Whether an engineer not following a research prompt gets here | **Missing empirical evidence** — not missing theory |

**Not missing:** another principle, a path-owner role, a platform
mandate, a global optimum.

---

## Phase 14 — Minimal emerging structure (non-canonical, not named)

Supported as **core** (at least two cases, load-bearing or useful):

1. **Name the class of intent and the outcome that would count.**  
   *Question:* What result is being caused, at a level a consumer can
   own, without collapsing other legitimate intents?  
   *Why:* The presented KPI is often the trap.  
   *Cases:* all three.  
   *If skipped:* you optimize the portal, the review SLA, or the
   component.  
   *Canonical:* intent, outcome, multi-objective design doctrine,
   Principle 2 unit.

2. **Scope the engineering system to that class of intent.**  
   *Question:* Through what sociotechnical system does this intent move
   — and what is it *not* (one team, the platform, the pipeline)?  
   *Why:* Therapy follows the unit.  
   *Cases:* all three.  
   *If skipped:* same as (1).  
   *Canonical:* Principle 2, conceptual model, federation "which
   system" (scale unproven).

3. **See what actually happens (trace), including local metrics.**  
   *Question:* What is the current path/composition, and which local
   successes already exist?  
   *Why:* Friction and seams are in the actual path.  
   *Cases:* all three.  
   *If skipped:* generic sermons.  
   *Canonical:* method "trace"; observation.

4. **Ask whether local success is system success (wrong-success check).**  
   *Question:* What can look better while the intent still fails or a
   legitimate constraint is gone?  
   *Why:* Recurring payload of all three cases.  
   *Cases:* all three.  
   *If skipped:* PE/DevSecOps/SRE default programs look like wins.  
   *Canonical:* design doctrine measurement; ticket-count anti-pattern;
   composition "parts ≠ whole."

5. **Split how it is consumed from how it is fulfilled; split routing
   from obligation.**  
   *Question:* Did we only change the front door? Is this delay
   accidental, intentional, or contextual?  
   *Why:* Cases 1–2 diagnoses; case 3 freeze.  
   *Cases:* all three.  
   *If skipped:* portal-as-router; delete SoD; permanent CAB.  
   *Canonical:* experience/realization; design doctrine.

6. **Treat what the system can already do as capabilities, including
   human-realized; examine settled vs novel before encoding.**  
   *Question:* What expertise is being consumed through people or stale
   defaults, and is it settled *enough*?  
   *Why:* Blocks automate-all and encode-never.  
   *Cases:* all three.  
   *If skipped:* C in security; handbook-as-reality in reliability.  
   *Canonical:* capability definition; Principle 4.

7. **If multiple contributors: name the composite's seams; do not
   transfer domain authority; refuse or exception rather than average.**  
   *Question:* Who is accountable for the interaction, and what must
   remain independently refuse-able?  
   *Why:* Unowned path; unowned cascade; cannot override security.  
   *Cases:* all three.  
   *If skipped:* czar or blamed component.  
   *Canonical:* composition.md, Principle 5.

8. **Change the smallest realization mix so consumers depend on the
   stable what; keep collaboration for novel; make system/seam evidence
   able to challenge encodings.**  
   *Question:* What is the minimum that changes dependence and
   learning, not the org chart?  
   *Why:* All three improved states.  
   *If skipped:* diagnosis without a design, or "build a platform."  
   *Canonical:* Principle 4–6; observation; learning.

**Situational (not core):** AI agent test; full SoD legal analysis;
incentive mapping; federation; IR command model; exhaustive
accountability matrices.

**Not numbered as a unique sequence:** 4 can (and should) interrupt 8.
5–7 are applied where the tempting answer lives, not always in this
order.

---

## Phase 15 — Try to break it

**Would this structure have discovered the important thing?**

1. **Onboarding — yes**, if (1)–(5) and (7) are done. The IDP indictment
   is (5)+(4). Unowned composite is (7). Risk: someone stops at (3)
   "there are ten tickets" (obvious) without (5) and gets "more portal."
2. **Security — yes**, if (1) doesn't collapse intents, (5) splits the
   slogan, (6) examines S1, (7) refuses override. Risk: (4) alone says
   "don't optimize review SLA" but not A vs C. **Missing if skipped:**
   authority≠execution is inside (7)/(5) here but easy to under-run.
3. **Reliability — yes**, if (4) and (7) are strong. Risk: the structure
   sounds like a *design-time* onboarding method; an incident commander
   may not "scope a class of intent" first — they mitigate. The lens
   applies more cleanly in **PIR/learning** than in minute-zero IR.
   **Ordering problem:** putting (8) before recovery is false. IR is
   collaboration under uncertainty; the structure is not an IR method.

**Unnecessary moves if treated as always-on:** incentive essays, AI
sections, filling every capability template in case 3 before naming the
seam.

**Missing moves:** facilitation (how to get identity and data in a room
without a new function); *sufficiency*; live tracing technique; **when
to stop diagnosing and mitigate** (case 3).

**Concepts that only work retrospectively:** neat S1 vs novel tables;
clean A/B/C — in the room the slogan is muddy. The structure can create
**false confidence** that classification is objective (the corpus says
it isn't).

**Practitioner judgment dominates:** settled-enough; who stewards the
composite; whether a freeze is still earning its keep.

**Do not repair here.** These are limits of the emerging structure.

---

## Final verdict

**B. A repeatable reasoning structure emerged, but it is not mature
enough to call a method.**

Evidence: the same unit, trap, distinctions, and wrong-success check
did useful work in three different problem classes. There are real
dependencies (don't skip intent/scope; don't skip local-vs-system). That
is more than a bag of questions.

It is not **A**: the sequence was prompt-shaped; `12-method` already
resembles it; no field proof; no sufficiency test; IR vs design-time
ordering is unresolved; judgment dominates the hard calls.

It is not **C** as the *best* fit: a pure checklist would not have a
unit of reasoning or a consistent "don't treat the proxy as the system"
dependency. Calling it *only* a checklist undersells the load-bearing
core (moves 1–4, 7).

It is not **D**: the three cases are coherent with each other.

**B** is the honest middle: **a reusable diagnostic/design lens with a
small set of load-bearing moves**, not a shippable method.

## Second verdict — distinctiveness

**B. Its value is primarily coherent synthesis across existing
disciplines.**

Not A: no unique technical move. Not D: the default applications of PE,
DevSecOps, and component-RACI SRE are exactly the wrong-success modes.
Not C as primary: packaging helps, but the experience/realization and
parts≠whole checks are doing diagnostic work, not just labeling.

## Recommendation

**Conduct a real-world field test.**

Do **not** formalize canonical application guidance yet: that would
freeze a structure discovered under identical research prompts, duplicate
`docs/12-method` with extra polish, and hide the IR-vs-design-time crack.

Do **not** run another fictional case next: a fourth paper scenario will
almost certainly reproduce B.

Do **not** revise theory: the cases did not find a contradiction; they
found application and incentive/stewardship gaps already parked.

Do **not** stop development of the *lens*, but **stop treating paper
cases as method discovery**.

A field test (one real onboarding path, one real security-approval
debate, or one real PIR) answers the question this artifact cannot:
whether an engineer **without** a 20-section template uses these moves
and avoids wrong success. That evidence should decide whether to
later thin `12-method` into this smaller structure, or to leave the
corpus as a body of knowledge plus existing method docs.

This recommendation is not performed here.
