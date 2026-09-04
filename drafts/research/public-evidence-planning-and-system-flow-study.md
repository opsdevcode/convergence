# Public-evidence study: planning, coordination, and system-level flow

*Non-canonical research artifact. Accessed September 2026. Not a field test of any
employer. Not a transformation playbook. Not a revision of canonical theory.*

**How to read this document.** Three categories are kept separate:

- **PUBLIC EVIDENCE** — claims a cited source actually makes.
- **OUR INTERPRETATION** — inference, synthesis, or extension by this study.
- **EXISTING THEORY** — statements from this repository’s canonical corpus
  (labeled as such; not treated as public evidence).

If a source only supports part of a claim, the claim is narrowed. Empirical
survey research is not treated as causal proof. Practitioner articles are not
treated as empirical.

---

## Research questions

**Primary.** Are team-centric planning, project-oriented coordination, locally
Agile execution, and cross-team dependency management *separate* problems, or
recurring manifestations of a deeper pattern in which **organizational
structure becomes part of the interface through which delivery is planned and
executed**?

**Secondary.** Does capability-oriented reasoning explain that relationship in
a way that existing disciplines do not already provide?

This study is designed to be able to conclude that existing work already
explains the problem adequately.

---

## Phase 1 — Prior-art map (sources on their own terms)

### 1. DORA / Accelerate

**PUBLIC EVIDENCE.** DORA’s “loosely coupled teams” capability states that
software delivery performance is associated with architectures and teams that
can test, deploy, and change **without depending on other teams**, with little
fine-grained coordination, independent on-demand testing, and independent
deploy/release. Tight coupling is described as forcing constant coordination
and bureaucratic change management. The page explicitly links this to Conway
and the Inverse Conway Maneuver. Measurement items include hours per week of
cross-team coordination, number of handoffs, wait times for reviews/approvals,
and percent of deployments that must be coordinated with other services
(DORA, “Loosely coupled teams,” dora.dev; last updated 2025-10-20).

The 2017 State of DevOps Report states that loosely coupled architectures and
teams are **the strongest predictor of continuous delivery** in that year’s
model, and that delivery teams that can test, deploy, and change without
depending on other teams for work, resources, or approvals perform better
(Puppet/DORA, 2017). Later reports (2021, 2022) continue to associate loosely
coupled architecture with delivery performance (DORA Accelerate reports).

The 2019 Accelerate State of DevOps Report found that **formal change
approvals by an external body (e.g. CAB)** were associated with being 2.6×
more likely to be low performers; DORA recommends peer review and automation
rather than external approval bodies (DORA, 2019).

**Limitation (PUBLIC EVIDENCE / method).** These are primarily **survey-based
correlations**, not randomized or quasi-experimental proofs that changing
planning models *causes* performance. DORA measures software delivery
performance (throughput/stability), not “roadmap green” or portfolio
predictability as primary outcomes.

**Unit of reasoning:** team + architecture enabling independent delivery.  
**Dependencies:** minimize fine-grained team/service dependencies.  
**Planning:** not a planning-method body; change-approval is in scope.  
**Outcomes vs outputs:** delivery metrics, not customer product outcomes.  
**Capabilities:** “capability” in DORA means research-identified practices,
not this corpus’s capability construct.

### 2. Team Topologies

**PUBLIC EVIDENCE.** Official material treats **blocking dependencies and
handovers** as a primary obstacle to fast flow: functionally siloed paths to
production introduce delays even in organizations that “practice DevOps”
(teamtopologies.com, “Fast flow”). Stream-aligned teams are described as
owning a slice end-to-end with **no hand-offs to other teams for any
purpose** in the intended pattern. Three interaction modes: collaboration,
X-as-a-Service, facilitating. X-as-a-Service is consumption with minimal
interaction (API, docs, self-service) so teams need not wait on each other
(teamtopologies.com key concepts; XaaS newsletter, March 2025).

InfoQ article by Team Topologies practitioners (2020): not all dependencies
can be removed; the aim is **non-blocking** dependencies via a clear contract
so teams can evolve independently (Skelton/Pais-related InfoQ, “Enabling
Effective Remote Working”).

**Limitation.** Official TT material is **practitioner/organizational design
guidance**, not a large-n empirical study of delivery performance (it cites
experience and related research, including Conway).

**Unit:** team-of-teams, cognitive load, flow of change.  
**Boundaries:** designed via team types and interaction modes.  
**Planning:** not a portfolio/PMO method.  
**Capabilities:** “platform capabilities” as XaaS offerings — adjacent to,
not identical with, this corpus.

### 3. Product Operating Model / SVPG

**PUBLIC EVIDENCE.** Cagan distinguishes **empowered product teams**
(cross-functional; measured by outcomes; empowered to solve problems) from
**feature teams** (output; prioritized feature roadmaps) and **delivery
teams** (implement assigned work) (SVPG, “Product vs Feature Teams”). Feature
teams receive roadmaps; the PM role often becomes project facilitation.

“Revenge of the PMO” (SVPG): historically PMOs herded functions to deliver
roadmaps on time/budget; Agile sidelined them; **SAFe is argued** (by Cagan,
explicitly second-hand regarding SAFe use in leading product companies) to
restore program-centric, top-down decision making (PM, architect, RTE) with
engineering teams assigned parts — **output not outcome**. Cagan states he
does not personally know a leading tech product company using SAFe
(practitioner opinion, not a survey). He also says **program/project mindset
is the problem**, while still advocating a scaled coordination role he prefers
to call Delivery Managers (SVPG Scaling Agile FAQ).

**Limitation.** Authoritative for a widely used **normative product model**;
not independent empirical evaluation of SAFe vs POM.

### 4. Agile (Manifesto)

**PUBLIC EVIDENCE.** Values include **responding to change over following a
plan**; working software as primary measure of progress; welcome changing
requirements even late; self-organizing teams; frequent delivery
(agilemanifesto.org, 2001, and principles).

**Limitation.** Team- and project-scale values. **Does not specify** how
multi-team portfolios should plan. Compatible with both “local sprints” and
system-level sequential programs.

### 5. SAFe (as designed)

**PUBLIC EVIDENCE (official).** PI Planning is a cadenced ART event (typically
2 days / 8–12 weeks) to align teams to a shared mission, **identify
dependencies**, foster cross-team collaboration, match demand to capacity,
and produce **committed PI objectives** plus an **ART planning board** of
feature dates and dependencies (framework.scaledagile.com/pi-planning; last
update 2026-03-15). SAFe quotes Lean product-development sources that future
tasks can’t be fully predetermined and planning should be distributed — while
the event itself is a **synchronized, committed plan**.

SAFe’s “Accelerating Flow” article: principle “make value flow without
interruptions”; six flow metrics including Flow Time and **Flow Efficiency**
(active time / elapsed time); flow requires individuals and teams in the
value stream to **synchronize** around value-creating activities
(framework.scaledagile.com/accelerating-flow-with-safe).

**OUR INTERPRETATION (not a claim that SAFe is “fake Agile”).** As designed,
SAFe **treats cross-team feature dependencies as first-class planning
objects** and invests ceremony and roles (RTE, planning board) in making them
visible and sequenced. That is **intrinsic framework complexity aimed at
coordination**, not an accidental bug. Whether that complexity is net
positive is a separate empirical question this study did **not** settle.

### 6. Lean / value-stream

**PUBLIC EVIDENCE.** Poppendieck Lean software development: wastes include
**waiting** and **handoffs**; value-stream maps typically show most elapsed
time is queue time, not coding (Poppendieck & Poppendieck, *Lean Software
Development*, 2003 — widely cited; software VSM descriptions in secondary
academic summaries). Little’s Law / queueing: high utilization and large
batches increase cycle time. **Resource efficiency vs flow efficiency** is
standard Lean: busy teams ≠ fast end-to-end flow.

**Limitation.** Foundational and widely replicated as **practice**; original
books are conceptual/practitioner, not DORA-style surveys.

### 7. DevOps

**PUBLIC EVIDENCE.** Historical claim (cultural/tooling): reduce
dev-vs-ops wall, automate delivery, shared responsibility (lineage: Velocity
2009, Debois DevOpsDays). DORA is the main empirical program associated with
the movement. Does not by itself specify product roadmaps or PMOs.

### 8. SRE

**PUBLIC EVIDENCE.** Google SRE literature: reliability as engineering, error
budgets, toil reduction, blameless postmortems (Beyer et al., *Site
Reliability Engineering*, 2016). Strong on production learning; **weak as a
planning/portfolio theory**. Overlap with “local green / system red” is
incident/SLO, not roadmap mechanics.

### 9. Platform Engineering

**PUBLIC EVIDENCE.** Community and vendor literature emphasize IDPs, golden
paths, reduced cognitive load (platformengineering.org and related).
**Empirical base is thinner than DORA.** TT XaaS is the closest primary
*model* of non-blocking platform consumption.

### 10. Sociotechnical systems / systems thinking

**PUBLIC EVIDENCE.** Trist & Bamforth (1951): joint optimization of social and
technical systems. Local optimization of a part can sub-optimize the whole
(classic systems-thinking claim; also Lean “optimize the whole”).

### 11. Conway / Inverse Conway

**PUBLIC EVIDENCE.** Conway (1968): organizations are constrained to produce
designs that copy their **communication structures**
(http://www.melconway.com/Home/Committees_Paper.html). Inverse Conway
Maneuver: shape teams to encourage desired architecture (LeRoy & Simons,
2010, commonly cited; DORA restates it).

**Limitation.** Conway’s original paper is observational/argumentative, not a
modern controlled study. Still the standard citation for org↔system
mirroring.

### 12. Flow / dependency research

**PUBLIC EVIDENCE.** DORA (wait, handoffs, coordinated deploys). TT (blocking
vs non-blocking). SAFe (visualize dependencies). Mik Kersten *Project to
Product* / Flow Framework (five/six flow metrics; SAFe cites related flow
metrics). **No single RCT** of “team roadmaps vs capability roadmaps” was
located.

---

## Phases 2–3 — Dependencies and local Agile vs system flow

**PUBLIC EVIDENCE — empirical (survey).** DORA: independent test/deploy and
low coordination overhead associated with higher delivery performance;
external CAB associated with lower performance (2017, 2019, capability page
2025). Architecture that requires simultaneous multi-service release is
described as producing orchestration, handoffs, and long lead times (DORA
loosely coupled teams).

**PUBLIC EVIDENCE — conceptual/practitioner.** Team Topologies: even mature
Agile teams are crippled by blocking dependencies between teams
(teamtopologies.com). Lean: wait time dominates lead time. SAFe: ART-level
flow issues include cross-team dependencies (official flow guidance;
secondary SAFe commentary notes ART metrics reveal issues invisible at team
level — treat ART-level “invisible at team” as **SAFe-aligned commentary**,
not an independent experiment).

**PUBLIC EVIDENCE — local vs system.** Agile Manifesto is team-scale.
SAFe explicitly adds ART/PI synchronization *because* multiple teams share a
mission. Lean flow efficiency can be low while utilization (local busyness)
is high. **Together these support:** teams can iterate locally while
end-to-end work waits in inter-team queues.

**Label:** Public evidence for “local Agile + sequential system” is
**strong as a conceptual/practitioner pattern** (Lean + TT + SAFe’s own
design) and **moderate as empirical** (DORA on coupling/handoffs/approvals,
not on “sprints inside a PI train” specifically).

**Do not use “waterfall” as a slur.** The documented behavior is: **cadenced
local iteration plus queued, dependency-sequenced handoffs across teams.**

---

## Phase 4 — SAFe: designed vs attributed implementations

**SAFe as designed (PUBLIC EVIDENCE).** Synchronized PI planning; committed
objectives; ART planning board of **dates and dependencies**; RTE-led
coordination; Lean Portfolio Management and flow metrics; stated intent to
improve flow and decentralize some decisions while **aligning the train**.

**Intrinsic complexity (OUR INTERPRETATION of the official design):**
managing many-team feature dependencies is **the job** of PI Planning and the
planning board. Complexity of visualization, commitment, and sequencing is
**intentional**.

**Implementation complexity (PUBLIC EVIDENCE is mixed):** Cagan and many
practitioners describe SAFe adoptions as restoring PMO/command-and-control
(practitioner reports, not a representative sample). Official SAFe would
reject “that’s not real SAFe” as the whole story — **this study does not use
that escape.** Both can be true: the framework **centers dependency
management**; organizations can add more gates, longer commitment horizons,
and weaker team empowerment than the framework’s Lean rhetoric suggests.

**What problem that complexity intends to solve (PUBLIC EVIDENCE):**
alignment of many teams, capacity matching, visible dependencies, reduced
WIP, shared mission — as stated in PI Planning benefits.

**Empirical outcome studies of SAFe vs alternatives:** **not assembled at
DORA quality in this artifact.** Treat outcome claims as **insufficient
empirical** here.

---

## Phase 5 — Product operating model

**PUBLIC EVIDENCE.** POM already explains a large planning problem:
**feature/project roadmaps + output measurement + PM-as-coordinator** vs
**problems/outcomes + empowered discovery**. It already attacks
project-mindset and “Agile teams implementing stakeholder roadmaps.”

**If POM explains the planning problem well:** **yes, for product-team
empowerment and output-vs-outcome.** It is **thinner** on specialist-domain
coupling (identity, network, security as delivery APIs) and on **composition
of capabilities** that are not “the product team’s backlog.”

---

## Phase 6 — Does Team Topologies already suffice?

**PUBLIC EVIDENCE.** TT already models blocking vs non-blocking dependencies,
interaction modes, platform as XaaS, cognitive load, Conway, stream alignment
without handoffs.

**OUR INTERPRETATION.** For **team-of-teams flow**, TT is a necessary and
near-sufficient *organizational* model. It does not by itself provide:
product strategy (POM), empirical delivery metrics (DORA), reliability
learning (SRE), or **planning abstractions other than teams and services**.
Reducing TT to “reorg” would be inaccurate; it is an **interaction and
boundary** model.

---

## Phase 7 — DORA language on local practices vs broader system

**PUBLIC EVIDENCE (paraphrase of actual claims).** Local CD practices are
amplified by loosely coupled architecture; architecture that forces
coordination, shared integration environments, and big-bang multi-service
releases undermines performance; external approval bodies hurt performance;
wait/handoff/coordination time are first-class measurements.

This **does** support: **local team practices are insufficient when
architecture and organization require cross-team orchestration.** DORA’s
actual emphasis is **architecture + team independence**, not “stop using
roadmaps.”

---

## Phase 8 — Why project/program management exists

**PUBLIC EVIDENCE — legitimate functions (PMI / standard PM discourse).**
Portfolio and program management exist to coordinate related work, resources,
risk, stakeholders, benefits, and governance across projects (PMI *Standard
for Program Management* / portfolio standards — conceptual professional
body). Large engineering systems have real sequencing, regulatory evidence,
and scarce specialists.

**PUBLIC EVIDENCE — “projectification.”** Midler (1995) “projectification of
the firm”; Hodgson & Cicmil and Packendorff & Lindgren: spread of project as
organizing form, tools of planning/control, professionalization of PM;
critiques include control, short-termism, rebureaucratisation (academic,
**not** software-delivery RCTs).

**PUBLIC EVIDENCE — software-specific critique.** Cagan: PMO as on-time
roadmap delivery; SAFe as appealing to that model (practitioner).

**Documented failure modes (mixed evidence types):** status theater,
dependency chasing, planning overhead, output optimization, **false
certainty** (Agile: responding to change vs following a plan; Lean: forecasts
under high variability). **Empirical quantification of “PM causes delay” in
software orgs: not located as a clean causal study.**

**Counterargument (must be treated seriously):** large systems **inherently**
need coordination; removing a PMO without changing coupling **moves**
coordination into Slack, architects, or hidden queues.

---

## Phase 9 — Product / project / engineering boundaries

**PUBLIC EVIDENCE — disagreement is real.**

| Body | Product | Project/program | Engineering |
| --- | --- | --- | --- |
| SVPG POM | Outcomes, discovery, value/viability | Often the *problem* when it dominates | Feasibility; engineers as problem-solvers on the product team |
| SAFe | Product Management / PO roles; features/epics | ART, PI, LPM, RTE | Teams implement; System Architect guidance |
| DORA | Lean product management as a capability in some reports | Change management as constraint | Team + architecture independence |
| TT | Stream = value slice | Not a PM method | Team types include platform/complicated-subsystem |
| Classic PM | Sponsor/requirements | Plan, track, integrate | Execute WBS |

**OUR INTERPRETATION.** Industry **does not share one map**. That disagreement
is evidence that “who owns intent vs plan vs technical ability” is contested,
not that any one map is proven.

---

## Phase 10 — Public-evidence archetype

Proposed chain:

PRODUCT INTENT → INITIATIVE/PROJECT → TEAM ROADMAP ITEMS → CROSS-TEAM
DEPENDENCIES → PROGRAM/PROJECT COORDINATION → MILESTONES/COMMITMENTS →
SEQUENTIAL ORGANIZATIONAL DELIVERY → LOCAL TEAM ITERATION → OUTCOME

| Link | Evidence | Strength |
| --- | --- | --- |
| Intent → initiative/project | POM (feature/project roadmaps); SAFe epics/features; standard PM | **Strongly evidenced** as a common organizing pattern |
| Initiative → team backlog items | SAFe team breakouts; Scrum team backlogs; POM feature teams | **Strongly evidenced** |
| Team items → explicit cross-team dependencies | SAFe PI Planning / ART board **by design**; TT blocking dependencies | **Strongly evidenced** that this *occurs and is managed* |
| Dependencies → program coordination | SAFe RTE, SoS, planning board; classic PMO | **Strongly evidenced** as designed response |
| Coordination → milestones/commitments | SAFe PI objectives; project milestones | **Strongly evidenced** |
| Commitments → sequential delivery | Planning board strings/dates; Lean queues between stages | **Moderately evidenced** (mechanism clear; not always sequential) |
| Local iteration during that | Scrum/Kanban inside trains; Manifesto team practices | **Strongly evidenced** as compatible |
| … → customer outcome | Often assumed; POM says output ≠ outcome; DORA measures delivery not product success | **Partially evidenced / often inferential** |

**Archetype decision:** **Do not reject.** Treat as a **documented common
pattern**, with the last mile to *customer/business outcome* weaker than the
middle (dependencies and coordination). Not proven universal.

---

## Phase 11 — Organization-as-planning-interface (not canonicalized)

**EXISTING THEORY (corpus):** organizational structure should not unnecessarily
become the **delivery** interface.

**Hypothesis (this study, not canonical):** organizational structure should
not unnecessarily become the **planning** interface.

Proposed mechanism and attack:

| Arrow | Classification | Why |
| --- | --- | --- |
| Org plans work by ownership boundaries | **Partially supported** | Team/ART/backlog ownership is how Scrum/SAFe/TT plan; Conway is about *design* communication, not proven as *planning* causality |
| Ownership → roadmap boundaries | **Partially supported** | Feature-team roadmaps (POM); team rows on ART boards (SAFe). Not proven necessary |
| Roadmap boundaries → explicit dependencies | **Supported** as a designed effect in SAFe; **partial** elsewhere | PI Planning’s purpose includes identifying dependencies among team plans |
| Dependencies → coordination | **Supported** (near tautological once dependencies are blocking) | TT, SAFe, DORA coordination overhead |
| Coordination → sequencing/synchronization | **Supported** in SAFe design; **partial** generally | Cadence and planning boards sequence work |
| Sequencing → longer intent-to-outcome time | **Partially supported** | Lean queues; DORA coupling. Sequencing can also *reduce* rework. Not always net delay |
| Centralized coordination **emerges to manage** that structure | **Partially supported / contested** | SAFe *prescribes* central ART coordination as the solution. Cagan sees PMO *return*. Could be compensation **or** inherent scale **or** both. **Not independently established as “because org is the planning interface.”** |

**The chain as a whole: not accepted.** Pieces sound reasonable; several
arrows are **partial**; the last is **not uniquely evidenced**.

---

## Phase 12 — Capability counterfactual

**EXISTING THEORY.** Intent → capabilities → contracts/constraints/authority →
realizations → composition → outcome → learning.

**Would this change planning? (OUR INTERPRETATION, unproven empirically.)**
It *could* shift the planning object from “Team B’s project finish” to
“capability contract/constraint.” That *might* allow: parallel realizations
behind a stable what; earlier specialist constraints; explicit intentional
dependencies; authority ≠ execution. **No public trial of this planning
representation vs team roadmaps was located.**

**Do not assume parallelism is safe** just because the language allows it
(DORA: contract tests, mocks — technical parallelism ≠ org parallelism).

---

## Phase 13 — Parallelism

**PUBLIC EVIDENCE.** DORA: contract testing, test doubles, independent
deploy, versioned APIs — **technical** decoupling. TT: XaaS after
collaboration stabilizes an interface. **Organizational** parallelism
requires non-blocking dependencies, not only capability vocabulary.

**Hypothesis “team/project planning converts concurrent capability work into
sequential delivery”:** **plausible**, **not independently established.**
SAFe sequencing may reflect real technical order **or** planning artifacts.

---

## Phase 14 — Centralized coordination: compensation vs inherent

**Compensation hypothesis:** PM/program layers manage dependencies that are
**expressed as team/project completions**.

**Inherent-coordination counterargument (must stand):** scale, regulation,
shared platforms, scarce experts, and portfolio investment **require**
visible coordination regardless of abstraction. Capability thinking would
**move** coordination (to contract design, composition ownership, exception
paths), not delete it.

**What capability reasoning could plausibly do (INTERPRETATION, not
evidence):**

| Effect | Plausible? |
| --- | --- |
| Eliminate | Some **routing/status translation** if contracts are consumed without waiting for a team’s “project done” |
| Reduce | Blocking waits **if** XaaS/DORA coupling is achieved — that is TT/DORA, not a new proof |
| Move earlier | Constraint/authority discovery before build |
| Make explicit | Intentional vs accidental dependencies |
| Encode/automate | Settled checks (DevSecOps/policy-as-code) |
| Preserve unchanged | Portfolio, SoD, novel collaboration, scarce-capacity sequencing |

**Necessary coordination is not failure.**

---

## Phase 15 — Wrong success

**PUBLIC EVIDENCE.** POM: shipping features/on-time ≠ outcomes. Lean: high
utilization ≠ flow. DORA: local deploy metrics vs (separately) product
success — DORA does not claim sprint velocity. SAFe Flow Predictability:
planned vs actual **business value** at PI — acknowledges team activity ≠
value. Systems thinking: local optima.

**OUR INTERPRETATION.** “Wrong success” as used in prior internal cases is
**mostly a useful phrase** for **local optimization / output vs outcome /
flow vs resource efficiency**. It is **not a new construct**. It *is* a
compact diagnostic question. **Do not formalize.**

---

## Phase 16 — Prior-art collision

### Strongest YES (existing stack is enough)

DORA (coupling, handoffs, wait, approvals) + Team Topologies (blocking vs
XaaS, team types) + POM (outcomes vs roadmaps, project mindset) + Lean (value
stream, queues, flow efficiency) + systems thinking (local vs whole) +
DevOps/SRE (delivery and production learning) **already let a skilled
practitioner** diagnose: locally Agile teams, sequential inter-team flow,
dependency boards, PMO/RTE coordination, and green local metrics with poor
end-to-end performance.

A valid **YES** does not need new vocabulary.

### Strongest NO (without vocabulary)

Existing approaches are **fragmented by room**: product coaches apply POM;
platform groups apply TT/XaaS; SRE applies SLOs; PMO applies SAFe boards;
architects apply Conway. **The relationship** “specialist-domain expertise is
consumed through org routing **and** that same structure is how **plans and
dependencies are written**” is usually **split**: TT/DORA emphasize *delivery*
coupling; POM emphasizes *product* empowerment; SAFe *operationalizes*
dependency planning. Few sources **jointly** model (a) specialist capabilities
that are not a stream-aligned team’s product, (b) authority vs execution, (c)
composition seams, and (d) planning objects, as one reasoning pass.

That is a **fragmentation / joint-application** gap, not a missing physics.

---

## Phase 17 — What capability reasoning adds

**Hypothesis:** a shared abstraction — what the **engineering system can do**
independent of which org box realizes it — connecting product intent,
specialist constraints, and composition.

**Support from sources:** DORA/TT already use **service contracts** and
**platform capabilities (XaaS)**. POM already uses **outcomes**. The
remainder is **synthesis across specialist domains and planning**, which
**this study does not empirically validate**.

---

## Phase 18 — “Product Engineering”

**PUBLIC EVIDENCE.** No single stable industry standard. Uses include: (a)
lifecycle discipline blending engineering, design, and business (Atlassian
product-engineering page — vendor/education, not a standard); (b) “product
engineer” as product-minded IC vs specialist SWE (PostHog, 2020s practitioner
blogs); (c) outsourcing firms’ “product engineering services.” Overlaps
confusedly with product management, software engineering, and platform
engineering.

**Ambiguity is documented as inconsistent usage, not as a measured
organizational failure mode.** This study **does not define** the term.

---

## Phase 19 — “System agility”

**Do not canonicalize.** Nearby public concepts: Agile “responding to change”;
SAFe “business agility”; resilience; dynamic capabilities (Teece — strategy
literature); DORA experimentation/loosely coupled change; POM discovery.

**Provisional idea** (change how the system pursues an outcome when evidence
changes) is **already covered** by those terms. No new name is warranted.

---

## Phase 20 — Claim / evidence table

| Claim | Source(s) | Type | Strength | Emp/con | Competing interpretation | Conf. |
| --- | --- | --- | --- | --- | --- | --- |
| Independent team test/deploy with low coordination associated with better software delivery performance | DORA 2017; loosely coupled teams page 2025 | Research program / survey | High for association | Empirical (survey) | Reverse causality; better orgs adopt decoupling | Med-high |
| External CAB-style approval associated with worse delivery performance | DORA 2019 | Survey | High for association | Empirical | Confounding with bureaucracy overall | Med |
| Blocking inter-team dependencies harm flow | Team Topologies official | Practitioner model | High as guidance | Conceptual | Some blocking is technically required | Med |
| SAFe PI Planning exists to identify dependencies and commit a multi-team plan | SAFe official PI Planning | Framework spec | High | Conceptual (normative) | Implementations vary | High |
| Feature/project roadmaps + output teams vs empowered outcome teams | SVPG Cagan | Practitioner | High as a widely used distinction | Conceptual | Some domains need output delivery | Med |
| Most elapsed time can be wait/handoff | Lean/Poppendieck | Practitioner/Lean | High as pattern | Conceptual | Not always true in small teams | Med |
| Conway: design mirrors communication structure | Conway 1968 | Essay | Classic | Observational | Causation bidirectional; weak original sample | Med |
| SAFe restores PMO/project mindset | Cagan “Revenge of the PMO” | Opinion + anecdotal contacts | Low–med as empirics | Practitioner | SAFe intends Lean flow and team planning | Low–med |
| Combined archetype (intent→team roadmaps→deps→PMO→local sprints) is universal | This study | Inference | — | Inferential | Many orgs don’t use SAFe; some are already decoupled | — |
| Capability-oriented *planning* outperforms team-roadmap planning | — | — | **None located** | — | May be equivalent to TT XaaS + DORA contracts | — |
| “Product Engineering” has one industry definition | Vendor/blog usage | Mixed | **Unsupported** | Conceptual | Multiple meanings | High that it is ambiguous |
| Projectification is a documented social/org phenomenon | Midler; Hodgson/Cicmil; Packendorff | Academic | Med | Conceptual/qualitative | Not specific to software flow | Med |

---

## Phase 21 — What this theory / hypothesis got wrong or overstated

**PUBLIC EVIDENCE that challenges or shrinks the planning hypothesis:**

1. **DORA’s primary lever is architecture + independent delivery**, not
   renaming roadmaps to capabilities. If coupling is fixed, many planning
   symptoms shrink **without** a new planning ontology.
2. **Team Topologies already names blocking vs non-blocking** and XaaS —
   the “org as delivery interface” thesis is largely **already TT+DORA**.
3. **POM already names project/feature-roadmap pathology** — product-side
   planning is not an open problem in that literature.
4. **SAFe as designed is not “unaware” of flow** — it has flow metrics and
   says wait/WIP are the enemy; the hypothesis must not caricature SAFe as
   ignorant of system flow.
5. **Coordination is often inherent** at scale; treating PM as compensatory
   **undervalues** portfolio, risk, and regulatory integration.
6. **Sequencing is often technically or legally required** (DORA does not
   claim all dependencies are bad; TT says not all can be removed).
7. **Wrong success is not original** — it restates local optimization /
   output vs outcome / flow efficiency.
8. **No empirical study** of capability-oriented planning was found; claiming
   planning improvement would **overstate**.

**EXISTING THEORY** already parks incentive compatibility and stewardship —
public evidence does not close those.

---

## Phase 22 — Verdicts

**Verdict 1 — Industry problem: B**  
Individual elements (coupling, blocking dependencies, feature roadmaps, PI
dependency boards, wait-dominated lead time, output vs outcome) are **well
supported**. The **combined** “this is one deep planning-interface problem”
is **partly inferential**.

**Verdict 2 — Planning hypothesis: B**  
Organization-as-planning-interface is a **plausible synthesis** of documented
mechanisms (especially SAFe’s designed dependency planning + team backlogs).
It is **not independently established** as a distinct causal law. Existing
explanations (DORA coupling, TT interactions, POM project-mindset) are
clearer for many readers.

**Verdict 3 — Capability reasoning: B**  
Provides a **coherent synthesis** across product, platform, and specialist
domains. It **does not** (on public evidence) add a validated mechanism
beyond contracts, XaaS, and loosely coupled architecture. **C is a close
second** if the remaining gap is only packaging.

**Verdict 4 — Coordination: B**  
Centralized coordination is **one important response** to cross-team
dependencies **and** a **necessary function** at scale. Evidence does **not**
strongly show it is *usually* mere compensation. **A would overclaim.**

**Verdict 5 — Local Agile vs system flow: B**  
The distinction is **real and documented** (Lean flow vs utilization; TT
between-team wait; SAFe team vs ART). It is **already fully explained** in
those bodies. This study should not treat it as a discovery.

---

## Final synthesis (plain language)

1. **Is the problem real beyond one company?** Yes: coupling, handoffs,
   blocking dependencies, feature/project roadmaps, and multi-team
   coordination are **industry-documented**.
2. **Strongly supported:** DORA-style independent delivery; wait/handoffs;
   TT blocking vs XaaS; POM output vs outcome; SAFe *manages* team
   dependencies explicitly; Lean queue-dominated lead time.
3. **Practitioner inference:** Cagan on SAFe; “PMO exists because roadmaps
   are team-shaped”; capability planning would unlock parallelism.
4. **Is team-centric planning implicated?** **As a common pattern, yes**
   (backlogs, ART team rows). **As the unique root cause, unproven** —
   architecture may dominate.
5. **Centralized PM:** **combination** — necessary portfolio/governance
   function **and** sometimes the operationalization of team-shaped
   dependencies. Not “the cause” in a single sense.
6. **Does SAFe matter?** It **matters as a widely used designed system for
   dependency-centric multi-team planning**. It is **not** the only way the
   pattern appears. Do not equate the industry problem with SAFe.
7. **Can locally Agile teams compose into a sequential system?** **Yes —
   that is consistent with Lean + TT + SAFe’s own structure.**
8. **Does capability reasoning expose what others miss?** **Mostly it
   joins rooms** (product, platform, specialists, composition). **Little
   that a joint application of POM+TT+DORA+Lean would miss**, except
   emphasis on specialist capabilities that are not stream-aligned products.
9. **More parallelism?** **Only if** contracts/XaaS/independent deploy
   exist — which is **DORA/TT**, empirically stronger than “capability
   language.”
10. **What the theory/hypothesis currently overstates:** planning-interface
    as a **new** causal law; PM as primarily compensatory; originality of
    wrong success; capability planning benefits.
11. **Unresolved:** causal tests of planning representations; SAFe outcome
    empirics vs POM; when coordination is inherent vs induced; specialist
    domains outside product-team literature.
12. **Next:** see below.

---

## Next-action choice

**Strengthen the public-evidence research.**

Not a field test of any employer (wrong corpus shape). Not theory revision
(no contradiction found; overstatement is in the *planning extension*, which
is not canonical). Not formalizing planning guidance (would freeze an
unvalidated ontology). Not stopping entirely (the **industry problem
elements** are real; the **planning-interface chain** is the weak part).

**What to strengthen:** (1) empirical literature on SAFe/PI dependency load
vs loosely coupled architecture; (2) whether “planning object = team
initiative” vs “planning object = service/contract” shows up as a measured
difference; (3) keep POM+TT+DORA as the baseline that must be beaten.

This action is **not performed here**.

---

## Sources (minimum bibliographic)

- Conway, M. E. (Apr 1968). “How Do Committees Invent?” *Datamation*.
  http://www.melconway.com/Home/Committees_Paper.html
- Beck et al. (2001). Manifesto for Agile Software Development.
  https://agilemanifesto.org/ ; principles: https://agilemanifesto.org/principles.html
- DORA (2017). State of DevOps Report. https://dora.dev/research/2017/dora-report/2017-state-of-devops-report.pdf
- DORA (2019). Accelerate State of DevOps Report.
  https://dora.dev/research/2019/dora-report/2019-dora-accelerate-state-of-devops-report.pdf
- DORA (2021, 2022). Accelerate State of DevOps Reports. https://dora.dev/research/
- DORA. “Loosely coupled teams.” https://dora.dev/capabilities/loosely-coupled-teams/ (updated 2025-10-20)
- Scaled Agile. “PI Planning.” https://framework.scaledagile.com/pi-planning (update 2026-03-15)
- Scaled Agile. “Accelerating Flow with SAFe.” https://framework.scaledagile.com/accelerating-flow-with-safe
- Team Topologies. Key concepts; Fast flow; X-as-a-Service newsletter (Mar 2025). https://teamtopologies.com/
- Skelton/Pais-related. “Enabling Effective Remote Working.” InfoQ.
  https://www.infoq.com/articles/remote-working-team-topologies/
- Cagan, M. “Product vs Feature Teams.” https://www.svpg.com/product-vs-feature-teams/
- Cagan, M. “Revenge of the PMO.” https://www.svpg.com/revenge-of-the-pmo/
- Cagan, M. “Scaling Agile FAQ.” https://www.svpg.com/scaling-agile-faq/
- Poppendieck, M. & Poppendieck, T. (2003). *Lean Software Development.*
- Midler, C. (1995). “Projectification of the firm: The Renault case.” *Scandinavian Journal of Management.*
- Packendorff, J. & Lindgren, M. (2014). “Projectification and its consequences.” *SAJEMS.*
- Trist, E. & Bamforth, K. (1951). *Human Relations* (sociotechnical).
- Beyer et al. (2016). *Site Reliability Engineering.* O’Reilly / sre.google
- This repository: `docs/01-principles/03-organization-is-an-implementation-detail.md` (**EXISTING THEORY** only)
