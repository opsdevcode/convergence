# Field-test protocol (non-canonical)

*Not application guidance for the body of knowledge. Not a method. Not a
verdict on this organization, SAFe, Agile, Product, or Project Management.
Does not edit canonical theory, the frozen essay, or prior research notes.*

**Purpose.** Test whether the reasoning structure recovered in
[`cross-case-application-synthesis.md`](cross-case-application-synthesis.md)
is usable on **one real initiative**, without a 20-section research prompt
driving the answers — and whether it can distinguish **necessary
coordination** from **coordination produced by how work is represented and
planned**.

**This protocol does not conclude.** Practitioner observations below are
**hypotheses to investigate**.

---

## Constraints (do not violate)

Do **not** assume:

- Project Management is waste or should be removed
- centralized oversight is wrong
- Product is incorrectly organized
- engineers should own all planning
- SAFe is the problem, or that the org is “doing SAFe wrong”
- Agile is the problem
- unlimited engineering autonomy is good
- planning and governance should disappear
- capability-oriented representation is better until evidence says so
- decentralized execution automatically improves outcomes

Do **not**:

- invent missing evidence (mark **unknown**)
- populate declared-vs-observed examples unless the initiative shows them
- define “Product Engineering” for the organization
- ask “Do we need Project Managers?” or “Should we use SAFe?”
- canonicalize “system agility” or any new concept
- modify canonical docs, the essay, or prior cases
- treat a successful test as eliminating PM

A successful test makes required coordination **more intentional** and
exposes **why it exists**. It can also find that PM is essential
system-level coordination, that the hypothesis is wrong, or that the
capability lens adds little.

---

## Practitioner observations to test (not conclusions)

Record these as claims under investigation:

1. Centralized PM (driven from / close to Product) adds substantial
   complexity and can make engineering delivery harder.
2. There is no clear shared definition of “Product Engineering.”
3. The planning org describes itself as Agile / SAFe; lived delivery may
   not match claimed principles (centralized oversight, team roadmaps,
   hard-to-change sequencing, commitments before engineering uncertainty
   is resolved).
4. **Hypothesis (PM):** some PM work may be managing coordination that
   exists because the engineering system is **represented and planned
   through organizational boundaries** (team-centric roadmaps →
   cross-team dependencies → central oversight → more coordination).
5. **Hypothesis (flow):** teams may be Agile *inside* boxes while
   intent-to-outcome *between* boxes remains project-oriented and
   sequential.

Each must be **falsifiable** with the evidence below.

---

## Select one real initiative

Pick **one** in-flight or recently completed initiative that:

- has a stated Product/customer intent
- crosses more than one engineering team or specialist domain
- has visible PM / planning / SAFe (or equivalent) activity
- someone will grant access to plans, meetings, and people

Prefer a normal initiative over a political crisis. Do not pick three
parallel tests for v1.

**Unknowns about selection** are fine; document why this initiative was
chosen.

---

## Part A — Intent, ownership, and “who believes they own what”

Capture **Product’s stated intent/outcome** in their words.

Observe how responsibility is **currently divided** (belief and practice
may differ). Do not prescribe who *should* own what.

For each row, record owner(s) as claimed vs as practiced, and **unknown**:

| Concern | Product | PM | Eng teams | Platform / infra | Specialist domains | Other / unknown |
| --- | --- | --- | --- | --- | --- | --- |
| Customer / product intent | | | | | | |
| Prioritization | | | | | | |
| Roadmap | | | | | | |
| Project execution | | | | | | |
| Dependency coordination | | | | | | |
| Engineering decisions | | | | | | |
| Technical realization | | | | | | |
| Delivery dates | | | | | | |
| Capability evolution | | | | | | |
| Customer / business outcomes | | | | | | |

Use as **questions**, not canonical role definitions:

- **Product:** What outcome are we trying to create and why?
- **Project Management:** How is coordinated work planned, sequenced,
  tracked, and reported?
- **Engineering:** What must the engineering system become capable of
  doing to produce the outcome?
- **Specialist domains:** What expertise, authority, constraints, and
  realizations are required?

Look for (only if evidence):

- Product roadmap items that are actually **projects**
- engineering roadmap items that are actually **implementations**
- project plans acting as the **integration layer** between capabilities
- teams measured on **outputs** while Product expects **outcomes**
- PM traversing dependencies that **no engineering-system abstraction**
  represents

---

## Part B — Declared operating model vs observed delivery

For this initiative only, two columns: **what the organization says
should happen** vs **what actually happened**.

Do not use the following rows unless evidence supports them; they are
prompts, not findings:

| If declared… | Check whether observed… |
| --- | --- |
| Teams are Agile | Work cannot proceed until another team’s roadmap item hits a milestone |
| Teams own delivery | Cross-team sequencing set by centralized project coordination |
| Planning is iterative | Dependencies/commitments form long sequential chains that are hard to change |
| Teams respond to learning | Plan change requires reconciling multiple project plans, roadmaps, milestones, stakeholders |

Also capture, without attributing to “SAFe” unless sourced:

1. SAFe as documented/intended (what artifacts/ceremonies this org cites)
2. This organization’s implementation of SAFe
3. Local processes layered on
4. Organizational structure
5. Product/PM practices
6. Legitimate enterprise governance
7. Actual engineering constraints

**The SAFe question is not “should we use SAFe?”** It is: which observed
behaviors arise from SAFe, which from this implementation, which would
exist under Scrum, Kanban, SAFe, or no named framework?

---

## Part C — Current plan: path, dependencies, PM activity

### C1. How work entered the system

Record:

- Product’s stated intent/outcome
- how the initiative entered the roadmap
- how engineering work was derived from it
- PM’s role
- team roadmap entries
- cross-team dependencies
- who **identified** each dependency
- who **tracks** each dependency
- who **decides** sequencing
- who **can change** sequencing
- meetings/processes that exist **because of** those dependencies
- what happens when a dependency slips
- how Product learns the initiative is “on track”
- how Engineering knows the required capability actually exists
- how the organization knows the intended outcome was achieved

Mark **unknown** freely.

### C2. Test this pattern (do not assume it)

If it appears:

Product defines initiative → assigned to an engineering team → team
discovers dependencies → those become other teams’ work → PM coordinates
those teams → delivery is a sequence of organizational commitments →
roadmap behaves like a long sequential chain.

**Do not immediately call it failure.** Ask **why** each transition
exists. Then (Part F) test whether a capability-oriented representation
would change any transition.

### C3. Project Management activity log

For each observed PM (or PM-like) activity — dependency meetings, project
plans, status meetings, milestone tracking, cross-team coordination,
escalation, approval tracking, dependency tracking, reporting, sequencing
decisions, delivery-date reconciliation — record:

**What problem is this activity solving?**

Then classify (multiple allowed):

1. necessary governance  
2. necessary portfolio coordination  
3. necessary specialist collaboration  
4. necessary dependency management  
5. organizational routing  
6. synchronization caused by sequencing  
7. status translation between organizational boundaries  
8. compensation for unclear ownership  
9. compensation for missing capability / interface / contract  
10. unknown  

**Do not** call meetings waste because they are coordination.

### C4. Coordination vs collaboration

Canonical distinction (do not redefine):

- **Coordination:** work required primarily to route execution through
  the organizational system.
- **Collaboration:** work required to solve a problem whose answer is
  not sufficiently understood or encoded.

Is centralized PM facilitating valuable collaboration, necessary
governance, organizational coordination, or a mix?

**Goal is not zero coordination.** Ask: which coordination exists because
the problem inherently requires it, and which exists because the current
planning/delivery model requires people to **manually synchronize
organizational boundaries**?

### C5. Local iteration vs system-level flow

Test whether each team can report Agile execution while intent-to-outcome
is still:

Team A sprint → wait → Team B planning/sprint → wait → Team C → outcome.

If present, distinguish **local iteration** from **system-level flow**.
Do not assume local Agile composes into an Agile engineering system.

### C6. Sequence cause (each apparent sequential dependency)

Classify (one primary if possible; note others):

| Code | Cause |
| --- | --- |
| A | Hard technical dependency |
| B | Safety / regulatory / governance constraint |
| C | Scarce resource / capacity |
| D | Legitimate domain authority |
| E | Missing capability contract / interface |
| F | Organizational roadmap sequencing |
| G | Centralized planning mechanics |
| H | Project milestone dependency |
| I | Incomplete information |
| J | Product commitment |
| K | Implementation choice |
| L | SAFe-specific practice |
| M | Local practice attributed to SAFe |
| N | Historical organizational habit |
| O | Unknown |

**Only E and F strongly support the planning/PM hypothesis** in the
parallelism test below (user: C and D in the *first* parallelism list
were “missing contract” and “planning around team-owned initiatives”).
Map: **E ≈ missing contract; F ≈ team-roadmap sequencing.**  
**A, B, C, D** (technical, governance, capacity, domain authority) may be
legitimate constraints. **G, H, L, M, N** may be planning-created; prove
with evidence, do not assume.

Also apply the shorter parallelism list where useful:

- A technically sequential  
- B governance/authority sequencing  
- C teams lack shared contract/constraint information to begin
  independently  
- D planning organized around completion of team-owned initiatives  
- E portfolio/resource sequencing  

Only **C and D** in *that* list strongly support the planning hypothesis.

---

## Part D — Engineering autonomy and learning

**Autonomy is not assumed good.** Record what teams **are actually
authorized** to change on this initiative:

- implementation
- sequencing
- start against an agreed contract before another realization is complete
- negotiate capability expectations with another engineering domain
- change technical approach based on learning
- challenge an assumed dependency
- run work concurrently
- change estimates when complexity is discovered
- escalate a constraint that invalidates the original plan

Where they **cannot**, record what prevents it (only with evidence):
domain authority, regulation, safety, architecture, Product decision,
project plan, roadmap commitment, SAFe ceremony, local policy, another
team’s roadmap, resource allocation, unclear ownership, culture,
unknown.

**Planning horizon vs engineering uncertainty**

Trace (if it exists): Product intent → initiative → project plan → team
roadmap commitments → dependency dates → cross-team sequencing →
delivery forecast.

Ask: does this create **apparent certainty** before engineering has
discovered actual dependencies, capability gaps, integration constraints,
risk, complexity, or novelty?

When learning invalidates the plan: does the planning system **absorb**
it, or must engineering **conform** to the existing plan?

Connect to existing theory: learning informs change; it does not mandate
it. Do not assume the answer.

**System agility (field-test only — do not canonicalize)**

Provisional: the engineering system’s ability to change how it pursues
an intended outcome when evidence changes what is known.

Observe if evidence exists:

- time from new evidence to plan adjustment
- number of organizational boundaries to change direction
- number of plans/roadmaps to reconcile
- authority required to change sequencing
- ability to start independent work concurrently
- ability to challenge invalid assumptions
- ability to preserve legitimate constraints while changing realization

---

## Part E — Wrong-success checks (this initiative)

Ask whether the org could report some of the following **while** the
intended engineering/product **capability still does not exist** or the
customer/business **outcome remains unavailable**. Record only metrics
actually used.

**Engineering / delivery proxies:** local SLAs, portal adoption, ticket
volume, scan coverage, component capacity, MTTR, review SLA.

**Product / PM proxies:** roadmap green, milestones achieved, project on
schedule, dependency tickets closed, team initiatives completed,
governance gates passed.

**Agile / SAFe-shaped proxies (if used):** sprint commitments met,
velocity stable, PI objectives green, ceremonies completed, dependencies
tracked, teams individually delivering.

**While possibly:** intent-to-outcome lead time poor; blocked across
teams; engineering learning cannot easily change the plan; coordination
burden up; dependencies increasingly sequential; Product receives
outputs without a usable capability; customer/business outcome delayed.

Conversely: do **not** assume schedule/milestone performance is
irrelevant. Record what those measures **do** tell you and what they
**do not**.

---

## Part F — Experimental plan (counterfactual — after C–E)

**Do not remove Project Management.** Ask: if dependencies were expressed
as capabilities, contracts, constraints, authority requirements, and
**actual** prerequisites:

- Which PM activities would **remain**?
- Which would become **easier**?
- Which might **disappear**?
- Which would **move earlier**?
- Which would become **evidence/observation** rather than meetings?
- Which would still require **human judgment**?
- Which remain because of **portfolio-level** concerns?

Sketch (do not assume superiority):

Product intent → required engineering capabilities → contracts /
constraints / authority → parallel realizations A/B/C where legitimate →
composition → outcome → learning.

Preserve in the sketch: Product intent, prioritization, domain
authority, governance, ownership, specialist expertise, necessary
project/portfolio coordination.

If this **redraws the same dependencies**, record that. Falsification of
the PM hypothesis includes: coordination would remain; PM is providing
essential system-level coordination; complexity originates elsewhere;
hypothesis is wrong.

**The PM question is:** what coordination does the engineering system
require, and **why**? Then map existing PM activities to: portfolio
decision-making, valuable facilitation, governance, risk management,
synchronization, organizational routing, status aggregation, dependency
chasing, translation between teams, compensation for missing contracts,
unclear capability ownership, or planning around organizational
boundaries.

---

## Part G — Apply the lens (minimum)

Use the synthesis’s load-bearing moves **as questions**, not a ceremony.
Stop if the initiative is single-team with no composition story.

1. Class of intent and what outcome would count (do not collapse Product
   vs security vs reliability vs date).
2. Engineering system scoped to that class — not “PM,” “the ART,” or
   “the platform” as the unit.
3. What actually happens (including PM and SAFe-shaped artifacts).
4. Local success vs system outcome (Part E).
5. Experience vs realization; accidental vs intentional friction
   (including PM meetings).
6. Implicit capabilities; settled vs novel (domain authority judges).
7. Composite seams; authority ≠ execution; refuse/exception vs override.
8. Smallest counterfactual (Part F); what evidence would show real
   change vs wrong success.

Do not fill every canonical template. **Unknown** is a valid result.

---

## Verdicts (choose after evidence, not before)

### Planning / representation verdict

Choose one:

- Team-centric roadmaps **materially create** cross-team coordination
  that a capability/contract representation would reduce.
- Mix of legitimate dependencies and planning-created sequencing; the
  lens helps distinguish them.
- Sequencing is mostly technical, governance, or capacity; planning
  model is not the main driver.
- Insufficient evidence / lens does not help.

### Organizational-coordination (PM) verdict

Choose one:

- PM is largely **compensating** for missing system abstractions
  (ownership, contracts, capability interfaces).
- PM mix of essential portfolio/governance work **and** boundary
  synchronization; the test made the split visible.
- PM is providing **necessary** system-level coordination that would
  remain under capability-oriented planning.
- Hypothesis is **wrong** or untestable on this initiative.

A success is **clarity**, not eliminating PM.

### System flow verdict

Choose **exactly one**:

**A.** Local Agile execution is being undermined by a planning/delivery
system that creates **materially unnecessary** sequential dependencies.

**B.** The system contains both legitimate sequencing and
organizationally created sequencing; capability-oriented reasoning helps
distinguish them.

**C.** The delivery system is mostly constrained by legitimate
technical, governance, or capacity dependencies rather than the planning
model.

**D.** The capability lens does not materially improve understanding of
system flow.

Do not optimize toward A or B.

### Lens / method verdict (from prior synthesis)

Did an engineer (or the facilitator) reach a better diagnosis **without**
being walked through twenty research sections? Yes / mixed / no /
unknown.

---

## What this test cannot do

- Prove or disprove the body of knowledge as a whole
- Produce a canonical method
- Authorize a reorg, a SAFe removal, or a PM reduction
- Fill incentive/funding open questions
- Attribute blame to Product, PM, or SAFe by default

---

## Outputs of the test (when run)

A single notes file under `drafts/research/` (e.g. dated
`field-test-<initiative-slug>.md`) containing: evidence tables, unknowns,
classifications, the three verdicts, and what would be needed to
falsify them further. No canonical edits unless a later, separate
decision says the theory itself broke.
