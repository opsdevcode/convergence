# Synthesis repositioning impact analysis

*Non-canonical. Framing impact only. Does not rewrite the project. Does
not modify canonical files. Planning research remains closed.*

Accepted positioning (provisional, not final copy):

> This body of knowledge synthesizes established ideas from product,
> platform, reliability, operations, systems, organizational, and other
> engineering practices into a common model for reasoning about how
> specialized expertise participates in software delivery.

Value: **joins among existing practices**, not invented mechanisms.

---

## Verdicts (front)

**1 — Repositioning magnitude: B**  
Several framing/prior-art/audience sections need changes. Frozen theory
remains stable. Not A (README-only would leave `convergence.md` “why
needed,” leftover “discipline,” and prior-art gaps). Not C/D.

**2 — Theory impact: A**  
No theory changes required. Principles and conceptual loop do not depend
on originality. Minor **positioning** sentences sit *around* theory
(e.g. “why it is needed”); those are framing, not conceptual edits.

**3 — Prior-art impact: B**  
Existing `prior-art.md` is already unusually honest. It should be
**strengthened** (DORA, Lean, Product Operating Model, systems
engineering as first-class neighbors). Not D: the corpus repeatedly
denies originality.

**4 — Audience impact: B**  
Audience should be more explicit. Current prose is written as if a
general practitioner must adopt the whole model. Synthesis-value: cost
is high; value peaks for cross-specialty reasoners. Not D: ICs are not
*excluded*; they are not the primary adopter of the full vocabulary.

**5 — Naming impact: C**  
Previous naming frame was **substantially wrong** if the goal was naming
a **discipline** (README still says the repo “once used Capability
Engineering as the name of the discipline”). “Convergence” as a *shift*
still sounds like a movement. Do not generate names here. Naming
criteria should now **avoid** discipline / specialty / methodology /
operating-model connotations.

**Recommended PR scope:** **make a focused synthesis-positioning PR**
(not a corpus-wide rewrite; not README-only; not deferred).

---

## Task 1 — Claim audit (KEEP / SOFTEN / CLARIFY / REMOVE)

| Location | Quote / gist | Risk | Class |
| --- | --- | --- | --- |
| `README.md` Kind | “Working body of knowledge, not a product or standard” | Compatible with synthesis | **KEEP** |
| `README.md` | “It is not a new specialty, team, or job family.” | Good; does not say “not a new discipline” | **CLARIFY** (add not a new discipline / not a replacement) |
| `README.md` | “This repository once used ‘Capability Engineering’ as the name of the **discipline**.” | Implies the project *was* a discipline | **SOFTEN** (historical name of the *mechanism/project*, not a discipline) |
| `README.md` Working def Convergence | “evolution of software delivery from an organization of engineering functions into an integrated engineering system” | Sounds like a historical movement / inevitable evolution | **SOFTEN** (working framing / synthesis lens, not an established industry evolution) |
| `docs/00-foundations/convergence.md` | Same evolution definition; “proposed name for an observed pressure… not a new engineering specialty” | Half-right; “observed pressure” is a thesis | **CLARIFY** |
| `convergence.md` | “Convergence is the hypothesis that these forces should collapse **delivery boundaries**” | Fine as hypothesis; can be read as unique program | **KEEP** with positioning nearby |
| `convergence.md` | “AI does not create the need for Convergence. It exposes the cost of not having it.” | Research: do not claim AI requires this model | **SOFTEN** (AI raises cost of org-as-API; does not require *this* synthesis) |
| `converged-engineering.md` | “This is a proposed model, not an established methodology.” | Good | **KEEP**; **CLARIFY** “synthesis / reasoning model” |
| `converged-engineering.md` Why it is needed | “Without an explicit model, organizations tend to add a platform hop…” | Implies this model is the necessary alternative to PE/you-build-it-you-run-it | **SOFTEN** (those failure modes; this synthesis is one way to name the join) |
| `prior-art.md` | “does not claim… component ideas are new”; “burden of demonstrating that the framing is useful”; table row “Proposed synthesis and lens” | Already the target positioning | **KEEP**; extend neighbor list |
| `prior-art.md` | “One way to understand the Convergence thesis is that DevOps demonstrated… Convergence asks whether similar reasoning should be applied more broadly” | Offered as thesis, not fact — good; still sounds like successor-to-DevOps | **CLARIFY** (extension of a *question*, not a successor movement) |
| `01-principles/*` | “working doctrine” | “Doctrine” can sound like a movement | **KEEP** (stable); optional later **SOFTEN** in headers only — not required in P0 |
| `04-operating-model/README.md` | “does not replace the engineering disciplines” | Excellent | **KEEP** |
| `02-capabilities/README.md` | “not a second discipline, not Platform Engineering” | Good | **KEEP** |
| `11-adoption/README.md` | “Convergence is recursively applicable from a startup to a federated enterprise” | Conflicts with abstraction-cost finding (one-team tax) | **CLARIFY** (principles may apply; full vocabulary not required at small scale) |
| `12-method/README.md` | Newcomers “how to actually do the work” as core path | Implies required methodology | **CLARIFY** (applied guidance; optional; not the identity) |
| `06-maturity-model/` | Spectra exist | Can look like a mandated maturity program | **KEEP** content; **CLARIFY** in README that it is applied, not identity |
| Architecture / IDP denials | Repeated “not an IDP / catalog / graph / required infrastructure” | Already correct | **KEEP** |

**No REMOVE** of frozen principles or the loop. Remove only the *implication* that this is/was a discipline, if a sentence cannot be softened.

---

## Task 2 — Identity audit (do not fix)

| Place | What it says it is | What it is not |
| --- | --- | --- |
| README Kind | Working **body of knowledge** | Product, standard |
| README / terminology | Convergence = **shift**; Converged Engineering = **design of the system** | New specialty |
| `convergence.md` | Proposed **name**, **framing**, **hypothesis** | Established term, new specialty |
| `converged-engineering.md` | Proposed **model** | Established methodology |
| `prior-art.md` | Early working **body of knowledge**; **proposed synthesis and lens** | Replacement of TT/DevOps/PE |
| Principles | Working **doctrine** | — |
| `how-to-critique.md` | Proposed **model**, not finished **standard** | — |
| Method | How to do **the work** | Not a second lifecycle |
| Operating model section | How disciplines are **consumed** | Not a replacement operating model for the firm |
| README history | Former name of the **discipline** | — |

**Inconsistencies (ANALYSIS):**

- Simultaneously: body of knowledge, model, doctrine, hypothesis, shift,
  synthesis, and (historically) discipline.
- “Operating model” **folder** vs “not an operating model for the
  company” — easy to misread as a new OM.
- Method sits on the **start-here** path equal to principles → reads as
  methodology even though the method README denies adding to the core.
- “Evolution of software delivery” reads as a **movement** more than a
  **reasoning model**.

Target identity for positioning: **synthesis + cross-domain
engineering-system reasoning model**. Keep “body of knowledge” as the
*repository kind*. Demote “discipline,” “movement,” “methodology,”
“operating model” as identity labels.

---

## Task 3 — Prior-art audit (do not rewrite)

**Adequate credit today:** Conway, STS, DevOps, CD, SRE, IaC, Team
Topologies, Platform Engineering, IBE, 1ES, AI-agent platforms. Honesty
note invites omissions. Principle 3 cites Conway as not original.

**Under-weight relative to synthesis-value / public-evidence work:**

| Neighbor | In corpus? | Gap |
| --- | --- | --- |
| **DORA / Accelerate** | Not a first-class `prior-art.md` section | Strongest empirical neighbor for coupling/handoffs |
| **Lean / value-stream** | Doctrine uses flow/local vs global without naming Lean as lineage | Understates Lean |
| **Product Operating Model / SVPG** | Product is a *problem* actor and an OM page; POM is not credited as outcome/empowerment prior art | Rhetorical risk: looks like we invented intent/outcome |
| **Systems engineering / Parnas / contracts** | Capability Engineering disambiguation only | Composition/contracts look more original than they are |
| **Sociotechnical** | Credited | KEEP |

**Rhetorical-strength-by-understatement flags:**

- `converged-engineering.md` “Without an explicit model…” — can be read
  as PE/TT/POM are not explicit models.
- DevOps “applied more broadly” — successor narrative.
- Missing POM/DORA/Lean in the comparison table while claiming
  synthesis of “established ideas.”

The new positioning should be comfortable saying **these mechanisms
already exist**. The page *almost* does; the **set of neighbors is
incomplete**.

---

## Task 4 — Value-proposition audit

Current “why use this”:

- Problem: specialization became the delivery architecture (`problem.md`,
  README).
- Why needed: avoid platform-hop / YBIYRI-without-encoding / agents
  navigating org charts (`converged-engineering.md`).
- Unit: intent-to-outcome engineering system (Principle 2).
- Prior-art: framing usefulness, not originality.

**Defensible after synthesis-value B:** diagnostic reasoning at
**joins**; bundled category errors; not unique designs vs a strong
stack.

**“Joins” language:** **not** a corpus term. **Substance is strongly
present** (Task 13). Using “joins” in **positioning copy** is a **useful
explanation** of existing material, **not** new theory — **if** it stays
marketing/framing and is not added as a conceptual node.

Joins the corpus already reasons about: Product↔Platform,
Platform↔Security, intent↔specialist expertise, capability↔realization,
experience↔fulfillment, composition↔authority, execution↔accountability,
local success↔system path (anti-patterns + Principle 2).

Drop or soften value props that imply: you cannot do this with TT+PE+POM;
this is required at every scale; AI requires this.

---

## Task 5 — Audience audit

**Appears written for:** a general “you” (product engineer in traces;
“practitioners”; critique table by specialty). Start-here path assumes
full vocabulary adoption.

**Synthesis-value:** architects, staff/principals, platform and
security/reliability/infra leaders, VP Eng — **primary**. Product
leadership — partial. Individual ICs — **weak for the whole model**,
strong for a few sentences (org chart isn’t the API).

**Need explicit audience framing? Yes (P0/P1).** Do not exclude ICs;
state that **full model** is for **cross-specialty design**, and
**individual distinctions** may be used alone.

---

## Task 6 — Abstraction-cost audit

Places that imply everyone must adopt the whole model:

- README start-here: problem → foundations → **all six principles** →
  **all of capabilities** → **method**.
- Adoption “recursively applicable” from startup.
- Maturity spectra as a numbered section equal to architecture.

**Should the project state** that people may use individual principles,
distinctions, diagnostic questions, or method **without** the full
vocabulary? **Yes.** Do not write that guidance in this task. P0: one
README/foundations sentence.

---

## Task 7 — Theory vs application boundary

`how-to-critique.md` already separates frozen vs applied vs parked.
README table matches. Method README: nothing adds to the conceptual
core.

**Still muddy:** start-here treats method as identity; “operating model”
name; maturity as a peer section; RFC scope listing “architecture” with
frozen core.

Planning branch evidence: useful application must **not** become frozen
theory. Boundary is **structurally** clear, **narratively** weak.

P1: README one paragraph: frozen = reasoning model; applied = optional
illustrations; no new theory from research drafts.

---

## Task 8 — Naming implications (no names)

**Communicate:** synthesis; reasoning model; engineering system;
cross-domain; complementary to named neighbors.

**Avoid:** new specialty; job family; methodology product; operating
system for orgs; movement (“the Convergence”); successor-to-DevOps;
platform/IDP brand; implying originality of capabilities/XaaS/SLOs.

**Previous assumptions that were wrong for this positioning:** treating
the thing to be named as a **discipline** (Capability Engineering
history); treating **Convergence** as an **industry evolution** to
brand. Naming a **reasoning synthesis** is a different job. Do not
restart naming research in this PR.

---

## Task 9 — README impact (do not rewrite)

| | |
| --- | --- |
| **Change** | Opening identity (what it is / is not); working definitions tone (“evolution”); leftover “discipline”; start-here (audience + optional full vocab); prior-art sentence to include DORA/Lean/POM; value = joins/synthesis |
| **Remain** | Problem gist; loop diagram; “what this is not” bullets (extend, don’t replace); principles quotes; doc table; license; RFC pointer |
| **Add** | Who benefits; “use a distinction without the whole model”; “not a new discipline”; “not a replacement for …” list matching synthesis-value |
| **Remove / demote** | “name of the discipline”; method as step 5 for *everyone*; any implied must-adopt-all |

Skeptical five-minute path: what / not / prior art / what synthesis
adds / who / where to start (problem + doctrine + prior-art, **not**
method first).

---

## Task 10 — Introduction impact (`convergence.md` + `converged-engineering.md`)

`convergence.md` **oversells** *scope as historical evolution* more than
*novelty of parts* (it already denies new components). Soften evolution
/ AI / successor-to-DevOps. Keep specialty-not-new.

`converged-engineering.md` “Why it is needed” **oversells uniqueness of
the model** vs neighboring explicit models. Soften to: these failure
modes; this synthesis names the join.

Do not rewrite here.

---

## Task 11 — Principles impact

| # | Principle | Impact |
| --- | --- | --- |
| 1 | Specialization remains. Silos don't. | **UNCHANGED** |
| 2 | Design the engineering system, not the handoffs. | **UNCHANGED** (this *is* the synthesis unit) |
| 3 | Organization is an implementation detail, not a delivery interface. | **UNCHANGED** (already cites Conway) |
| 4 | Encode what is repeatable. Collaborate on what is novel. | **UNCHANGED** |
| 5 | Distribute execution. Preserve accountability. | **UNCHANGED** |
| 6 | Close the loop from intent to learning. | **UNCHANGED** |

**All six survive unchanged.** No substantive theory change. Optional
**POSITIONING CONTEXT** only in README/foundations (“these principles
are a synthesis lens, not a new physics”) — not inside principle files
for P0.

---

## Task 12 — Conceptual model impact

The loop does **not** depend on claiming originality. It is a
**taxonomy of established relations** (intent/outcome, ability vs
fulfillment, feedback). It still functions as a **synthesis diagram**.
**Do not modify the model.**

---

## Task 13 — “Joins” test

| Join | Corpus location | Support |
| --- | --- | --- |
| Product intent ↔ specialist expertise | `problem.md` supply chain; Principle 1; OM product vs security pages | **SUPPORTED BY CORPUS** |
| Platform experience vs specialist realization | experience vs realization; portal-as-ticket-router; PE OM | **SUPPORTED BY CORPUS** |
| Security authority vs distributed execution | Principle 5; composition; invocation-as-authority; security OM | **SUPPORTED BY CORPUS** |
| Composite vs contributing domain ownership | `composition.md` tables | **SUPPORTED BY CORPUS** |
| Org independence vs discoverable ownership | Principle 3; organizational-independence.md | **SUPPORTED BY CORPUS** |
| Automation vs human judgment | Principle 4; automation-as-maturity | **SUPPORTED BY CORPUS** |
| Local success vs system outcome | Principle 2; ticket-count anti-pattern; design doctrine | **SUPPORTED BY CORPUS** |

Word “joins”: **INFERRED AFTER THE FACT** as positioning shorthand.
Phenomenon: **strongly present throughout**. Not retrospective
storytelling of empty files.

---

## Task 14 — Claims we should never make

Drawn from planning, public-evidence, corpus-analysis, and
synthesis-value:

- We invented capability-based / capability-oriented engineering.
- Existing disciplines cannot solve cross-team or multi-specialty delivery.
- Platform Engineering is insufficient or obsolete.
- Team Topologies only reorganizes teams.
- This replaces DevOps, SRE, POM, DORA, Lean, or systems engineering.
- This eliminates coordination or specialization.
- This is a new engineering discipline, specialty, or job family.
- AI requires this model.
- Planning around capabilities is a validated improvement (planning
  branch closed; remainder is application guidance only).
- Every practitioner must adopt the full vocabulary.
- A portal, catalog, graph, or IDP is Convergence.
- Composite ownership includes domain authority over contributors.
- Local green metrics (tickets, automation %, team SLA) *are* system
  success — also: do not claim we *invented* that warning.

---

## Task 15 — Claims we can defend (narrow)

Prefer “this model…”:

- This model **synthesizes** established practices into a common
  **engineering-system** vocabulary for a **class of intent**.
- This model **does not claim** its component mechanisms are original.
- This model is **complementary** to POM, TT, PE, DORA, DevOps, SRE,
  Lean, and systems engineering; it does not replace them.
- This model is useful primarily where those practices **meet**
  (specialist expertise as delivery interface vs queue vs platform
  monopoly vs product-only empowerment).
- Distinctions already in the corpus (capability vs realization,
  experience vs realization, authority vs execution, accidental vs
  intentional friction, human realization valid) help **recognize
  category errors**; they do not uniquely generate designs.
- Practitioners may use **parts** of the model without adopting all of
  it.
- Abstraction cost is **meaningful**; the full model is aimed at
  **cross-specialty** reasoning, not at replacing an IC’s home
  discipline.
- Frozen core is a **reasoning model**; method/OM/maturity/adoption are
  **applied** and must not silently become new theory.

Do **not** defend: industry-wide empirical superiority; planning-object
causality; uniqueness of the loop versus a competent stack.

---

## Task 16 — Minimum repositioning plan

| Pri | File | Section | Type | Why | Semantic intent |
| --- | --- | --- | --- | --- | --- |
| P0 | `README.md` | Kind, defs, what this is not, start-here, prior-art para, leftover discipline sentence | positioning / audience / navigation | First-read identity | Synthesis + reasoning model; not discipline; not replacement; who; optional full vocab; start with problem + prior art |
| P0 | `docs/00-foundations/convergence.md` | Working definition, forces/AI, prior-art blurb | positioning | “Evolution” / AI overclaim | Framing as synthesis lens/hypothesis, not industry movement; AI does not require this model |
| P0 | `docs/00-foundations/converged-engineering.md` | Why it is needed; opening “proposed model” | positioning | Sounds uniquely necessary | Failure modes remain; this is a join-naming synthesis, not the only explicit model |
| P0 | `docs/00-foundations/prior-art.md` | Lineage list + table + “what it claims” | prior-art | Missing DORA/Lean/POM/SE | These mechanisms already exist; Convergence row stays “proposed synthesis and lens” |
| P1 | `docs/00-foundations/README.md` | Layer table / intro | positioning / navigation | Foundations index still says “shift” as identity | Point to synthesis positioning |
| P1 | `docs/00-foundations/how-to-critique.md` | What is frozen; “just DevOps” row | clarification | Align critique with synthesis-value | Attack usefulness of *join*, not originality of parts |
| P1 | `docs/00-foundations/terminology.md` | Convergence / Converged Engineering | positioning | Defs echo “evolution” | Same as README; not a specialty |
| P1 | `docs/11-adoption/README.md` | Recursively applicable | audience / clarification | Conflicts with cost finding | Same principles ≠ required full vocabulary at one-team scale |
| P1 | `docs/12-method/README.md` + README start-here | How to do the work | navigation | Method reads as identity | Applied, optional |
| P2 | `docs/04-operating-model/README.md` | Title/intro | clarification | Folder name “operating model” | Already says not replacing disciplines; one sentence: not a new firm OM |
| P2 | Principle file headers “doctrine” | Optional | positioning | Movement vibe | **Defer**; not required for honesty |
| P2 | Maturity README | Intro | navigation | Looks like a program | Already non-scoring; one “applied only” reminder |

**Do not:** edit six principle bodies; conceptual model; capability
mechanism pages; composition; anti-pattern bodies; diagrams; RFC
process (except if README RFC sentence needs “positioning” not “new
concepts”).

---

## Task 17 — Change budget

Canonical markdown under `docs/` plus root README / ROADMAP / critique
path: **on the order of 90+ files**.

| | Estimate |
| --- | --- |
| **Require edits** for honest positioning | **8–10** (table above P0+P1) |
| **May benefit** (P2) | **3–5** |
| **Should remain untouched** | **All frozen principle bodies, conceptual loop, capability/architecture mechanism pages, patterns, most OM discipline pages, diagrams** — **~80+** |

If a plan touches most of the corpus, it is **too broad**. This plan
changes **framing around stable theory**. Challenge: do not “fix”
every “doctrine” header or OM page.

---

## Final recommendation

**Make a focused synthesis-positioning PR.**

Not “no changes” (leftover discipline; evolution; AI; incomplete prior
art; start-here methodology vibe). Not broader corpus PR. Not defer
until validation (honesty of *claim* does not wait on interviews).

Do not perform the PR in this task.

---

## Stop-report checklist (for the assistant reply)

1. Verdicts B, A, B, B, C  
2. All six principles survive unchanged  
3. Conceptual model survives unchanged  
4. ~8–10 files require edits  
5. P0: README, convergence.md, converged-engineering.md, prior-art.md  
6. Never-make list in Task 14  
7. Defend list in Task 15  
8. Naming: previous frame was discipline/movement; criteria must avoid that  
9. PR: focused synthesis-positioning  
