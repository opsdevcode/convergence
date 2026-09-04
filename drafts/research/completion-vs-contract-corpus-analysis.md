# Completion vs dependency-sufficiency: corpus consistency

*Non-canonical. Corpus analysis only. Not new public-evidence research.
Not planning methodology. Does not modify canonical files.*

The strong planning hypothesis is closed. This document only asks whether
the **narrow remainder** is already inside the theory.

---

## 1. Narrowed research finding (provisional, non-canonical)

> Do not treat completion of another realization as the prerequisite when
> a sufficient contract, interface, constraint, decision, or authority
> already exists that allows work to proceed safely.

**Conditional.** Sequential execution remains legitimate for technical or
runtime dependency, safety, regulation, governance, authority, scarce
resources, unresolved uncertainty, genuinely novel work, or inability to
establish a reliable contract/interface.

This is **not** “teams should always work in parallel.”

Two readings of that sentence must be kept apart:

| Reading | Meaning |
| --- | --- |
| **Delivery / consumption** | A consumer of an *existing* capability should not wait on another team’s *project finish* or *replacement realization* if the capability’s current expectations already allow safe progress |
| **Construction / planning** | Downstream *building* may start against a spec before an upstream *implementation* exists |

The corpus is a theory of the engineering system’s **abilities, consumption,
and fulfillment**. It is not a planning-object theory. Those readings must
be scored separately.

---

## 2. Relevant existing canonical statements

Quoted or tightly paraphrased. Files are the source of truth.

**Capability vs realization**

- A capability is “an organization’s ability to satisfy a class of intent”
  (`docs/02-capabilities/capability.md`).
- Realization is “how it is currently accomplished.” “The capability may
  remain stable while its realization changes.”
- **“Consumers should depend on capabilities more strongly than they
  depend on realizations.”** (same sentence in `capability.md` and
  `realization.md`.)
- That is “not a requirement that realization details always be hidden.”
- Encoding “does not create the capability from nothing”
  (`docs/00-foundations/conceptual-model.md`).
- Learning example: the capability existed *before* encoding; realization
  and leverage changed (`docs/02-capabilities/learning.md`).

**Organizational independence / Principle 3**

- “Organizational structure should not become the software delivery API”
  (`docs/01-principles/03-organization-is-an-implementation-detail.md`).
- Abstracted out of the execution path: “Organizational sequence as the
  delivery interface.”
- Designed into the path: SoD, independent authority, regulatory
  obligation, human judgment.
- Organizational independence: consumers can “discover and **use**” a
  capability “without understanding the organizational structure
  responsible for its **realization**”
  (`docs/02-capabilities/organizational-independence.md`). Spectrum; not
  opacity. Ownership remains discoverable.

**Contracts**

- “Explicit description of expectations and constraints governing the
  **consumption and fulfillment** of a capability”
  (`docs/02-capabilities/capability-contract.md`).
- A capability **can exist without** a formal contract.
- “A contract that lies is worse than a short honest one.”
- Rigor proportional to risk/scale. Governance: encode expectations in
  realization; review remains for exceptions and novel risk.

**Composition**

- Transfers consumer-intent obligation and seam accountability; **does
  not** transfer domain authority or ownership of contributors
  (`docs/03-architecture/composition.md`).
- Valid only when “contracts, constraints, and relevant authorities of
  contributing capabilities can coexist.”
- Safety of parts does not guarantee safety of composition.
- Composition must not silently expand authority.

**Authority**

- Authority ≠ execution ≠ privilege ≠ ownership
  (`docs/02-capabilities/ownership-and-authority.md`,
  `docs/01-principles/05-distribute-execution.md`).
- Invocation is not authority (`docs/08-anti-patterns/invocation-as-authority.md`).

**Accidental vs intentional friction**

- “Remove accidental friction. Design intentional friction.”
  (`docs/00-foundations/design-doctrine.md`).
- Slowness is not the test. Independent approval can be intentional;
  ticket-chain routing for *settled* routine intent is usually accidental.
- Method: for each interaction, record **what it decides**, **who holds
  authority**, **what it waits on**
  (`docs/12-method/tracing-a-flow.md`,
  `docs/12-method/evaluating-interactions.md`).

**Experience design**

- “What they learn about constraints **before committing**”
  (`docs/12-method/designing-experience-and-realization.md`).
- Consumption **eligibility**: failure when “the answer arrives after they
  have committed effort” (`docs/03-architecture/consumption.md`).

**Repeatable vs novel**

- “Encode what is repeatable. Collaborate on what is novel”
  (`docs/01-principles/04-encode-what-is-repeatable.md`).
- Do not encode unsettled judgment
  (`docs/12-method/deciding-what-to-encode.md`).
- Abstraction must not manufacture false certainty
  (`conceptual-model.md`).
- “Useful incompleteness is better than fictional completeness”
  (`docs/03-architecture/federation.md`).

**Anti-pattern**

- Capability as a team rename: consumers still need the team to know how
  to ask; realization is “the team”
  (`docs/08-anti-patterns/capability-as-a-team-rename.md`).

---

## 3. What those statements already imply

**Delivery reading — implied.**

If the engineering system **already possesses** a capability that
satisfies the class of intent, the consumer’s dependency is on **what
that capability currently guarantees**, not on:

- which team currently realizes it,
- whether a *successor* realization (Terraform replacing a DBA, a new
  architect) has finished being built,
- organizational sequence as the way to obtain it.

Principle 3’s left column (org sequence as delivery interface) plus
“depend on capabilities more strongly than realizations” plus
organizational independence (“use” without knowing realizing structure)
already condemn **waiting on another team’s project as the consumer-facing
API** when the capability is already there.

Evaluating interactions already treats “queue for a settled rule” as
accidental *shape* of a possibly intentional *control*. Waiting for
**authorization** can be the control; waiting to **discover the team**
or **re-enter a ticket** is not.

Eligibility-before-commitment already says: the consumer needs sufficient
expectation **before** sinking effort — that is dependency-sufficiency
for *consumption*, in other words.

**Authority already blocks “start anyway.”**

A contract or interface does not grant domain authority. Execution does
not imply authority. Composition must not widen authority. Regulatory
and SoD waits are *designed into the path*, not defects.

**False contracts already condemned.**

Lying or premature encoding is already out of bounds (contract honesty,
don’t encode moving targets, expose uncertainty, composition validity).

**Novel work already sequential-or-collaborative.**

Principle 4 and coordination/collaboration: if the answer is not
sufficiently encoded, collaboration is the legitimate mode — not a fake
stable contract.

---

## 4. What they do NOT imply

They do **not** imply:

- Parallel construction of a capability that **does not yet exist**.
- Treating a draft interface as a capability.
- That Capability Contract is a **pre-existence** artifact for unblocking
  downstream implementation programs.
- That composition is a **Gantt** of contributor completion vs contract
  milestones.
- That organizational independence applies to **imaginary** capabilities.
- A planning object, capability roadmap, or “plan around contracts.”
- That every finish-to-start wait is accidental.
- Originality versus Parnas / API-first / CDC (the corpus does not need
  that).

Conceptual model is explicit: encoding changes realization; **it does
not create the capability from nothing.**

---

## 5. Completion vs dependency-sufficiency

**Does the theory distinguish realization completion from dependency
sufficiency?**

| | In the corpus? |
| --- | --- |
| What vs how (capability vs realization) | **Yes, explicit** |
| Consumer should not couple to *which* realization | **Yes, explicit** |
| Consumer should not use org sequence as the interface | **Yes, explicit** |
| Wait for **decision/authority** vs wait for **queue/routing** | **Yes, in method** (`what it decides` / `who holds authority` / `what it waits on`) |
| Wait for **contributor implementation to finish** vs wait until **expectations are sufficient** | **Not named** as a pair |
| Sufficiency of a contract **before the capability exists** | **Not supported**; opposite pressure from “does not create the capability from nothing” |

**Test 1.** “The consumer depends on what must be true, not necessarily
on completion of the mechanism that ultimately makes it true.”

- **Supported** when “what must be true” is an **existing** capability’s
  expectations, and “mechanism” is the current or successor **realization**.
- **Not supported** if “what must be true” is a hoped-for ability. A
  capability that does not exist cannot be assumed into existence.

The narrowed sentence’s phrase **“already exists”** (sufficient contract
/ constraint / authority) is doing the load-bearing work. The corpus
agrees **only** in that conditional form, and mainly for **use**, not
for **inventing** the upstream ability.

---

## 6. Contract analysis (Test 2)

Capability Contract governs **consumption and fulfillment of a
capability**.

It is **not** primarily specified as a planning token for work that
precedes the capability. Facets (intent, constraints, eligibility,
ownership, lifecycle) *could* be read as “enough to proceed,” but the
document’s job is: state expectations for using/fulfilling something the
organization **can** do, with rigor matching scale.

A capability **without** a formal contract can still exist. Therefore
the contract is **not** the existence condition, and **not** defined as
the artifact that licenses independent downstream *construction*.

**Do not expand** Capability Contract to mean “spec sufficient for
parallel programs.” The corpus does not support that expansion.

Eligibility-before-commitment is the nearest **consumption** analogue:
know constraints before sinking effort. That is still not contract-first
development of missing contributors.

---

## 7. Authority / governance limits (Test 4)

Existing doctrine **already prevents** the remainder from becoming
“start anyway.”

| Wait | Corpus treatment |
| --- | --- |
| Implementation / queue for settled fulfillment | Often accidental routing if the capability exists |
| Authorization / independent judgment / SoD / regulation | Intentional; preserve and design into the path |
| Unsettled novel risk | Collaboration; do not encode a guess |

Waiting for **implementation** and waiting for **authorization** are
already distinguishable via method fields (decides vs waits on) and
Principle 5. No new authority machinery is required. Any canonical
“clarification” that blurred them would be a regression.

---

## 8. Counterexamples (Test 8)

| Hostile case | Already protected? | How |
| --- | --- | --- |
| 1. Interface defined, feasibility uncertain | **Yes** | False certainty forbidden; don’t encode uncharacterized risk |
| 2. Contract exists, upstream cannot satisfy | **Yes** | Lying contract worse than honest short one; operate/evolve when contract and behavior diverge |
| 3. Regulatory approval must precede downstream work | **Yes** | Intentional friction; authority preserved |
| 4. Schema agreed, semantics unsettled | **Yes** | Representation ≠ reality; still novel; collaborate |
| 5. Mock succeeds, integration fails | **Yes** | Parts ≠ composition safety; learning from outcome/incident |
| 6. Contract as premature commitment on novel work | **Yes** | Principle 4; deciding-what-to-encode “nothing yet” |
| 7. Downstream builds on unapproved assumptions | **Yes** | Invocation ≠ authority; eligibility; domain authority |
| 8. Many consumers force a premature abstraction | **Yes** | Appropriate leverage, not max abstraction; useful incompleteness |

**If the narrowed claim needed substantial new machinery to survive
these, it should not become canonical.** It does **not** need new
machinery: the hostile cases are already the theory’s load-bearing
limits. That is evidence **against** a new conceptual node, principle,
or contract expansion.

---

## 9. Corpus gap analysis

**Test 3 — Composition.** Explains independent **ownership** and
**authority** of contributors, and that contributor **contracts** must
coexist. Does **not** distinguish “depend on contributor contract” from
“depend on contributor implementation completion.” The missing sentence
would be a **scheduling** claim. Composition is **structure**, not a
plan. Adding it there would mix layers.

**Test 5 — Intentional friction.** Sequencing **can** be accidental
(org sequence as interface) or intentional (SoD, novel judgment). That
classification **is already explicit**. Do not create a new
completion-vs-contract friction type.

**Test 6 — Organizational independence.** Defined on **discover and
use** of a capability. It **does** imply that another team’s internal
project should not automatically be the **consumer-facing** dependency
**for an established capability**. It does **not** extend to
capabilities that are only intended. Independence is not a license to
plan against a ghost.

**Test 7 — Method.** Practitioners are already asked what an interaction
**waits on** and **decides**. They are not explicitly asked: “Is this
wait for realization completion, or is sufficiency (contract, constraint,
decision, authority) already present?” That is a **diagnostic phrasing**
gap in **applied method**, not a hole in the conceptual core. Method
README: nothing there adds to the conceptual core; v0.1 method is
expected to improve as guidance.

**Test 9 — Relabeling.** Connecting Parnas/API-first to this corpus does
**not** require claiming originality. The internal question is whether
Capability / Realization / Organizational Independence **fails to let a
reader reach the delivery reading.** They do reach it. The construction
reading is **out of scope**, not an internal gap.

**Test 10 — Scope.** Lowest impact: **nowhere in theory.** Optional later
method question is application guidance only.

---

## 10. Exact verdict

**D — Application guidance only. Do not change canonical theory.**

Not **A**: the completion-vs-sufficiency pair is not *stated*.

Not **C**: there is no missing concept. Hostile cases are already
handled. Expanding contracts or composition into planning would be new
theory the planning research already declined.

Not **B** as a theory edit: the delivery reading is **already implied**
by realization dependence, Principle 3, organizational independence, and
the team-rename anti-pattern. Making “don’t wait on project completion”
explicit in `realization.md` would either (a) restate those sentences or
(b) be misread as licensing parallel **construction** against
not-yet-existing capabilities — the reading the conceptual model
forbids.

The method could someday ask a sharper wait question. That would still
be **application**, and this analysis **does not** schedule that edit.

---

## 11. Minimal recommendation

**No canonical edit.** Do not add a principle, planning object,
capability-roadmap, contract expansion, or composition-scheduling clause.

Treat the narrowed remainder as:

- a **practical consequence** of existing delivery doctrine when the
  capability and sufficient expectations **already exist**;
- **out of theoretical scope** when used as a general rule for
  sequencing work that **creates** missing abilities.

Practitioners who need a prompt already have: trace what each
interaction waits on and decides; evaluate whether that wait is
authority/judgment or routing; do not encode the novel.

---

## Tests 1–10 (compact)

| Test | Result |
| --- | --- |
| 1 Capability vs realization | Enough for **existing** abilities; not for assumed-into-existence abilities |
| 2 Contracts | Govern consumption/fulfillment of a capability; **do not** expand to pre-capability parallel-work licenses |
| 3 Composition | Independent contributor **authority/contracts**, not implementation-completion semantics |
| 4 Authority | Already blocks “start anyway” |
| 5 Intentional friction | Sequencing already classifiable; already explicit; no new class |
| 6 Org independence | Established capabilities only; not ghost capabilities |
| 7 Method | Nearby questions exist; sharper phrasing = method/application, not theory |
| 8 Counterexamples | Survives **because** existing limits apply — reason **not** to canonicalize |
| 9 Relabeling | No genuine internal conceptual gap to close |
| 10 Scope | Nowhere in theory; optional application only |

---

## Why no canonical edit (A/D explanation)

The planning research narrowed to a **conditional delivery hygiene**
rule. That rule is what Principle 3 and capability-vs-realization were
already for: consumers use **what the system can do**, not **how a
particular realization project is progressing**, unless the wait is
itself the designed control (authority, safety, novelty, truth of the
contract).

Writing it again as theory would preserve research momentum, not
understanding. The strong planning hypothesis is not to be rescued
through a “small clarification.”
