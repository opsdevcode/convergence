# Planning object and system flow

*Non-canonical research. Accessed September 2026. Causal/comparative investigation
only. Not a methodology. Not an argument for capability roadmaps. Not an argument
against SAFe or project management. Does not modify canonical theory.*

**Categories kept separate**

- **PUBLIC EVIDENCE** — what a cited source actually claims.
- **OUR INTERPRETATION** — inference in this study.
- **EXISTING THEORY** — this repository’s canonical corpus (not public evidence).

**Provisional vocabulary (this study only).** A *planning object* is the thing
around which work, commitments, dependencies, sequencing, and progress are
represented (project, initiative, feature, epic, team deliverable, milestone,
service, API, contract, capability, outcome). Not proposed for canonicalization.

**Primary question.** Does planning around team initiatives / projects / features /
ownership versus capabilities / services / contracts / interfaces / intent
materially affect dependency structure, sequencing, synchronization, wait,
concurrency, independent delivery, coordination burden, replanning, and
intent-to-outcome lead time?

Three causal hypotheses are tested. None is assumed.

---

## Phase 1 — Baseline from the prior public-evidence study

Prior study (`drafts/research/public-evidence-planning-and-system-flow-study.md`)
verdicts: industry pattern **B**; planning-interface hypothesis **B**; capability
reasoning **B** (C close); coordination **B**; local Agile vs system flow **B**.

**What those sources already establish (PUBLIC EVIDENCE, not re-reviewed):**

| Body | Established for *this* question | Does **not** establish |
| --- | --- | --- |
| **DORA** | Survey association: loosely coupled architecture/teams (independent test/deploy, low fine-grained coordination) with software delivery performance; 2017: strongest predictor of CD that year; wait/handoffs/coordinated deploys measured; external CAB associated with worse performance (2019) | That *portfolio planning object* (project vs capability) is an independent cause; that changing roadmaps without architecture changes flow |
| **Team Topologies** | Blocking vs non-blocking team dependencies; X-as-a-Service as self-service consumption with minimal interaction | That renaming a dependency to a “capability” in a plan changes flow without XaaS actually existing |
| **Product Operating Model** | Feature/project/output roadmaps vs empowered outcome teams; discovery authority | That outcome statements change *engineering* dependency graphs |
| **Lean** | Wait/handoffs/queues dominate elapsed time; local utilization ≠ flow | Planning-object identity as a variable |
| **SAFe (official)** | PI Planning exists to identify team/feature dependencies, match capacity, produce committed PI objectives and an ART planning board of dates/dependencies | That this is *only* compensation for avoidable coupling, or that it is *only* inherent scale |

**Evidence gap.** No located public study isolates: *same architecture, same
teams, different planning object → measured flow difference.* That is the gap
this document tries to bound with adjacent evidence.

---

## Phase 2 — Architecture as the cause (strongest NO to Hypothesis A)

**PUBLIC EVIDENCE.** DORA (“Loosely coupled teams,” updated 2025-10-20):
performance associated with ability to make large-scale changes **without
depending on other teams**, independent on-demand test and deploy, little
fine-grained coordination. Tight coupling forces constant coordination. 2017
report: loosely coupled architecture/teams **strongest predictor of continuous
delivery** in that model.

Conway (1968): organizations produce designs copying communication structures —
architecture and organization **co-evolve**; not a claim that *plans* cause
coupling.

Parnas (1972): modularization criterion determines whether modules can be
developed independently. Decomposition by **processing steps (flowchart)** vs
**information hiding (interfaces that hide design decisions)**. Independent
development is an explicit benefit of the latter.

**Strongest NO (OUR INTERPRETATION of that evidence).** If Team A must wait for
Team B because of shared databases, lock-step releases, or missing interfaces,
**changing the row label on a plan does not create independent testability.**
DORA’s measured construct is architectural/team independence, not planning
ontology. If architecture dominates, Hypothesis A is at most a second-order
amplifier.

**If architecture dominates the evidence: say so.** For *software delivery
performance as DORA defines it*, **architecture (plus team independence)
dominates** relative to any planning-object variable that has been measured.

---

## Phase 3 — Organizational structure as a distinct cause

**PUBLIC EVIDENCE.** Conway: communication structure ↔ design. Inverse Conway
Maneuver (as restated by DORA): shape teams toward desired architecture. Team
Topologies: component/functional silos and handoffs vs stream-aligned teams
with no production-path handoffs; cognitive load; interaction modes. Specialist
and complicated-subsystem teams are **legitimate** in TT, not errors.

**Do not collapse architecture and organization.** Architecture can couple teams
that are already “stream-aligned” (shared integration env). Organization can
couple teams that have APIs (ticket queues, sequential approvals). DORA
measures both coordination hours and architectural deploy coupling.

**Planning around teams (OUR INTERPRETATION).** Team-owned backlogs are a
**representation of ownership**. That does not prove they *cause* ownership.
TT treats team boundary design as causal for flow; the backlog is downstream
of that design.

---

## Phase 4 — Project / initiative / feature / milestone as planning object

**PUBLIC EVIDENCE — academic (not software-flow RCTs).** Projectification
(Midler 1995; Packendorff & Lindgren 2014): project as organizing form;
planning/control/visibility; critiques of short-termism and rebureaucratisation.

**PUBLIC EVIDENCE — practitioner.** Cagan (SVPG): feature teams receive
prioritized feature roadmaps; PM becomes output/project facilitation; “Revenge
of the PMO” argues program-centric delivery of roadmaps (opinion, not a
survey).

**PUBLIC EVIDENCE — SAFe official.** Features/epics, PI objectives as
**commitments**, ART planning board of **feature dates and dependencies**.
That is a designed planning representation, not a critique.

**Empirical findings vs criticism.** Empirical DORA does **not** isolate
“epics vs services.” Practitioner criticism of output/milestones is **not**
empirical proof that those objects *create* coupling.

**Label:** projectification and feature-roadmap effects on *product outcomes*
= **practitioner + some academic org theory**. Effects on *DORA metrics* =
**not directly measured**. Synchronization/batch/commitment around PI/features
= **conceptually specified by SAFe**.

---

## Phase 5 — Outcome as planning object ≠ capability

**PUBLIC EVIDENCE.** SVPG: empowered teams measured by **outcomes**, not
roadmap delivery. That changes **who decides** and **what success is**, not
automatically **service graphs**.

**Ask:** Does “achieve outcome Y” vs “build feature X” alter engineering
dependencies?

**OUR INTERPRETATION.** Outcome orientation can **remove unnecessary features**
(smaller graph) and **change discovery authority**. Remaining technical
prerequisites (data, identity, network) typically remain unless architecture
or platform consumption changes. **Do not equate outcome planning with
capability/contract planning.**

**Evidence type:** **CONCEPTUALLY SUPPORTED** (POM) that outcomes change
decision quality; **UNSUPPORTED** that they change coupling independently of
scope/architecture.

---

## Phase 6 — Contract-first / interface-first (central empirical-adjacent evidence)

**PUBLIC EVIDENCE.**

- **Parnas 1972:** interfaces chosen to hide inner workings enable **independent
  development** and shorter development time as a stated goal of modularization.
- **Ian Robinson / Fowler, “Consumer-Driven Contracts” (2006):** SOA benefits
  require services that **evolve independently**; “we build services that share
  **contracts, not types**.” Contracts **enable independence** and can also
  **couple** providers/consumers (hidden schema coupling, versioning, big-bang
  change). CDC pattern: consumers express obligations; providers gain insight.
  **Liabilities documented in the same article** (evolution, validation cost).
- **Pact (docs.pact.io):** consumer tests against a **mock**; produces a
  contract the provider verifies. Explicitly supports developing consumer
  behavior **without the live provider**.
- **DORA loosely coupled teams:** mentions **contract tests and mocks** as
  practices associated with independent testing (capability page).

**Benefits claimed in sources:** parallel consumer work against doubles;
independent evolution **if** contracts are compatible; earlier detection of
breakage (provider verification).

**Failure modes in sources:** breaking schema changes; “big bang” versioning;
consumers coupled to whole schemas; contract/versioning complexity; mocks that
diverge from reality (implied by verification need).

**Label:** **CONCEPTUALLY SUPPORTED** (Parnas, CDC) + **PRACTITIONER GUIDANCE**
(Pact) + **EMPIRICALLY ASSOCIATED** (DORA lists contract tests with loosely
coupled teams) — **not** an RCT of “plan on contracts vs plan on projects.”

This is the **strongest public case** that *some* planning/design objects
(interfaces/contracts) change **when work can begin** relative to “wait for
full implementation.” That object is **architectural**, whether or not a
portfolio tool names it.

---

## Phase 7 — X-as-a-Service

**PUBLIC EVIDENCE (Team Topologies official).** XaaS: consume capabilities via
API/docs/self-service **without** constant coordination (meetings, aligning
release plans). Purpose: avoid **blocking** dependencies. Not all dependencies
removable; aim is **non-blocking** (TT InfoQ remote-working article). XaaS
requires a **real service**; collaboration is used to establish it.

**Does XaaS…**

| Effect | PUBLIC EVIDENCE / INTERPRETATION |
| --- | --- |
| Remove a dependency | TT: **minimize** blocking deps; consumption still depends on the service existing |
| Blocking → non-blocking | **Claimed** when self-service works |
| Hide org routing | **Yes as consumer experience** (no ticket to Network Team for routine use) |
| Change coordination timing | Coordination **up front** to build the service; then low interaction |
| Relocate coordination into service creation/maintenance | **Yes — TT still has platform teams doing that work** |

XaaS changes **what the consumer plans against** (a service, not a project
finish) **only if the service exists**. That is **not** a vocabulary change
on a dependency board.

---

## Phase 8 — Platform engineering

**PUBLIC EVIDENCE.** CNCF TAG App Delivery *Platform Engineering Maturity
Model*: platforms **curate and present common capabilities**; interfaces
maturity from custom processes → standard tooling → **self-service** (little
support from maintainers) → integrated services. Platform engineering is
“planning and providing such computing platforms.”

**Ask:** capability-oriented *planning* vs self-service *architecture*?

**OUR INTERPRETATION.** The documented mechanism is **self-service
architecture + product-like platform ownership**, not a change to
initiative/epic portfolio objects. If product teams still plan “Project N
depends on Network Team,” while *also* having an IDP, **two representations
can coexist**. Where self-service is real, consumers plan against
**provisioning/policy/identity APIs**, which **challenges** the claim that
*portfolio* capability language is the necessary mechanism. **Platform
engineering already produces the consumption effect without requiring a new
planning methodology.**

---

## Phase 9 — Parallel development and minimum upstream artifact

**PUBLIC EVIDENCE.** Parnas: interface/module definition sufficient to develop
separately. CDC/Pact: contract + mock. Feature flags / branch-by-abstraction
(Fowler and CD literature): integrate incomplete behavior behind toggles —
**practitioner**. Independent environments: DORA coupling page (shared
integration environments as a coupling symptom).

**Minimum upstream artifact (synthesis of sources, labeled INTERPRETATION
where not a single quote):**

| Need | Typical minimum in literature |
| --- | --- |
| Compile/call a module | Interface / API (Parnas) |
| Test consumer in isolation | Contract + test double (Pact/DORA) |
| Runtime in production | Implemented, compatible provider **or** virtualization — **implementation still required for true runtime** |
| Authority to ship | Decision/policy (DORA: external CAB as delay) — **not** an API |
| Shared scarce capacity | Scheduling (inherent) |

**Do project plans commonly mistake “implementation complete” for “enough
contract/authority”?**

**PUBLIC EVIDENCE located is primarily conceptual/practitioner guidance rather
than empirical.** SAFe planning boards **do** string **feature completion
dates** as dependencies (official PI Planning). That is **compatible with**
completion-based planning. It does **not** prove organizations *cannot* also
plan interface milestones. **INFERENCE**, not measured prevalence.

---

## Phase 10 — Dependency semantics

The word “dependency” in public sources is **rarely disaggregated** into the
twelve types listed in the brief. SAFe visualizes **feature/team**
dependencies. DORA mixes **architectural** (coordinated deploys) and
**process** (approvals, handoffs). TT distinguishes **blocking vs
non-blocking**. PMI-style PM distinguishes finish-to-start vs other logic
**in schedules**, which is **scheduling semantics**, not architecture vs
authority.

**If existing planning already distinguishes them:** partially — **PM
precedence types** and **TT blocking/non-blocking** exist. **Fine-grained
authority vs interface vs runtime** is **not** standard on ART boards.
**Record against Hypothesis A:** some planning systems already have
dependency *types*; software sources still **collapse** technical and org
wait.

---

## Phase 11 — Completion dependency vs contract dependency

**Completion:** “cannot begin until they finish.” **Contract:** “can proceed
once expectations/interface/constraints/assumptions are explicit enough.”

**Prior art (do not claim originality):** Parnas independent development;
CDC/Pact; concurrent/set-based engineering (constraints/feasibility before
point commitment); modular architecture; API-first (practitioner).

**Demonstrated consequences:** **CONCEPTUALLY SUPPORTED** that contract-level
sufficiency enables **parallel development**. **Not demonstrated** as a
portfolio-planning A/B test. Runtime and regulatory **completion**
dependencies remain (you cannot observe production behavior of an unimplemented
control by mocking it in all cases).

---

## Phase 12 — Concurrent engineering prior art

**PUBLIC EVIDENCE.** Concurrent / simultaneous engineering: overlapping
subsystem development. **Set-based concurrent engineering** (Ward, Sobek,
Liker; Toyota studies; Sloan 1999): communicate **sets** of feasible designs;
integrate by **intersection** of constraints; delay point commitment. Survey
of auto suppliers (Liker et al., IEEE TEM 1996) associated set-based
communication with early supplier involvement and subsystem interdependence.

This is **substantial older prior art**: stable (or set-valued) **interfaces
and constraints** allow parallel subsystem work. Software “capability
planning” that means “agree the interface/constraints first” **rediscovers
this**. Software “capability” as a vague noun **does not**.

---

## Phase 13 — SAFe / PI Planning as a hard test

**PUBLIC EVIDENCE (official).** Cadenced ART alignment; identify dependencies;
committed objectives; planning board of dates and dependencies; flow metrics
including flow efficiency; stated Lean idea that the future cannot be fully
predetermined **and** a synchronized committed plan.

**Does SAFe synchronize because scale inherently requires it, or to compensate
for coupling?** **Both readings fit the text.** Official benefits: alignment,
capacity, visible dependencies. Official design **assumes** many-team feature
dependencies are first-class. It does **not** claim those dependencies are
all architecturally unnecessary. DORA would treat **unnecessary** deploy
coupling as a performance problem **whether or not** SAFe visualizes it.

**Could contract-oriented representation reduce synchronization while remaining
compatible with SAFe?** **ANALYSIS ONLY, not a recommendation.** SAFe already
has architecture, enablers, and APIs. Representing some strings as **interface
milestones** rather than **team feature finish** is **not forbidden** by the
framework text fetched. Whether that **reduces** PI coupling is **UNSUPPORTED
empirically**. Do not argue SAFe should change.

---

## Phase 14 — Coordination: symptom vs irreducible

For coordination forms in the sources:

| Form | If planning object became contract/capability |
| --- | --- |
| Fine-grained multi-team release orchestration | **Reduce** if architecture decouples (DORA) — **architecture**, not labels |
| CAB / external approval | **Reduce** if shifted to peer/automation (DORA 2019) — **governance process** |
| PI dependency stringing | **Preserve or relabel** unless dependencies become non-blocking |
| Portfolio/investment sequencing | **Preserve** (scarce capital) |
| Novel joint design | **Preserve** (TT collaboration mode) |
| Building a platform service | **Move earlier / concentrate** (XaaS creation) |
| Consumer ticket-per-request | **Eliminate for routine** if self-service exists |

**Moving coordination is not eliminating it.**

---

## Phase 15 — Coordination displacement / amortization

**Analytical terms for this study only.**

**PUBLIC EVIDENCE adjacent:** TT XaaS and CNCF PE self-service: many consumers
stop coordinating **per request**; platform/security **encode once**. That is
**amortization** (and **displacement** onto platform maintainers), not
**elimination**. TT: if XaaS stops fitting users, **collaboration** returns.

No located source uses these three words as a taxonomy; the **effect** is
described in TT/PE.

---

## Phase 16 — Stable “what,” changing “how” (collision with modularity)

**EXISTING THEORY** (corpus): consumers should depend more on **what the
engineering system can do** than on **how it is realized**.

**PUBLIC PRIOR ART.** Parnas information hiding; abstract interfaces; SOA
contracts (Fowler/Robinson); APIs; platform capabilities (CNCF); systems
engineering ICDs (interface control). **Applying this to organizational
planning** beyond standard modularity: **the collision is severe.** If
“capability planning” means “depend on hidden-implementation interfaces,”
**Parnas + SOA + PE + XaaS already state it.** Distinctiveness requires a
remainder (e.g. **authority/governance as first-class contracts**, not only
APIs). That remainder is **not empirically validated** here.

---

## Phase 17 — Learning and replanning

**PUBLIC EVIDENCE.** Agile Manifesto: responding to change over following a
plan. Rolling-wave / progressive elaboration (PMI). POM discovery. Lean:
delay commitment. Set-based CE: delay point decisions. SAFe: PI commitments
**and** inspect-and-adapt.

**Would contracts absorb learning better?** **Both possibilities in sources.**
CDC: contracts **focus evolution** on consumer obligations **and** create
**versioning rigidity** if badly designed. PI/project milestones can freeze
dates. **Contracts can become rigid commitments** (Robinson: burdened with
services; big-bang schemas). **UNSUPPORTED** that capability-named plans
adapt better than outcome-named or API-named plans.

---

## Phase 18 — Failure modes (do not defend)

Analogous **PUBLIC EVIDENCE / well-documented analogues:**

| Failure | Analogue |
| --- | --- |
| Vague capability nouns | Enterprise architecture capability maps as unused documentation (practitioner EA criticism; **not** a clean empirical software-flow study) |
| Premature contracts | Parnas: over-specified interfaces restrict implementations; Robinson: schema coupling |
| Frozen bad abstractions | Information hiding of the *wrong* secret |
| Unclear ownership | Conway: if communication doesn’t match modules |
| Hidden real dependencies | Mocks vs production drift (reason Pact verifies providers) |
| New silo | Component/platform teams that become ticket queues (TT: failed XaaS / blocking platform) |
| More coordination via negotiation | CDC implementation cost; collaboration cheaper than bad contract (TT: collaboration is expensive but used to *create* XaaS) |
| Novel work forced behind interfaces | TT: collaboration mode for discovery; DORA does not claim all work is independently deployable on day one |

**These are reasons not to treat capability-as-planning-object as free.**

---

## Phase 19 — Relabeling test

Transformation: “Team B must complete networking project” → “We require network
connectivity capability.”

**If nothing changes except vocabulary, capability representation failed.**

Material change requires at least one of: when work can begin; information
required; completion meaning; who coordinates; amortized vs repeated
coordination; independent evolution; reuse; how deps are tested; authority;
failure observation; learning.

**PUBLIC EVIDENCE of material change** exists for **XaaS/self-service APIs,
contract tests, independent deploy** — not for the **sentence rewrite**.
**Relabeling without those artifacts fails the test.**

---

## Phase 20 — Causal matrix (examples from public sources)

Causes may be multiple. Strength = evidence that *this kind of dependency
exists and has discussed causes*, not that one cause is unique.

| Observed dependency | Tech | Arch | Org | Gov | Plan | Typical representation | Contract/iface change it? | Arch change it? | TT change it? | POM change it? | Capability language change it? | Strength |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Coordinated multi-service release | Y | Y | maybe | | dates | release train / shared env | Partial (compat) | **Yes** (DORA) | Partial | No | Relabel only | Emp. assoc. (DORA) |
| Wait for another team’s feature | | Y | Y | | Y | ART string / finish-to-start | If iface exists | If decouple | If XaaS | If scope drops | No unless consumption changes | SAFe spec + TT |
| External CAB | | | Y | **Y** | Y | approval gate | No | No | No | No | No | Emp. assoc. (DORA 2019) |
| Consumer waits for platform ticket | | | Y | | ticket | request queue | Yes if API | IDP | **XaaS** | No | Only if = platform cap. | TT + CNCF PE |
| Schema/provider change breaks consumers | Y | Y | | | version | provider contract | **CDC/versioning** | Modularize | | | No extra | Fowler/Robinson |
| Specialist SoD / sign-off | | | Y | **Y** | checkpoint | control gate | Policy-as-code *if* settled | Partial | Enabling/XaaS | No | Authority contract? unproven | Conceptual |
| Scarce expert capacity | | | Y | | queue | resource leveling | No | No | Load mgmt | No | No | Inherent |
| Outcome unknown / discovery | | | | | roadmap freeze | feature commitment | No | No | Collab | **Yes** (POM) | Not equivalent | POM |

---

## Phase 21 — Counterfactual (architecture held fixed)

**PLAN A — team/project oriented.** Intent → initiatives → team deliverables →
cross-team dependencies → program coordination → implementations → outcome.

**PLAN B — capability/contract oriented.** Intent → required abilities →
contracts/constraints/authority → realizations → composition → outcome.

**Constraints:** same architecture, people, teams, Product org, governance,
specialists, regulation, capacity.

**Does Plan B alone change anything?**

**OUR INTERPRETATION.** If architecture is tightly coupled, Plan B **cannot
create** independent deploy/test. It **can** change **when coding starts**
*only if* teams actually produce and honor **new interface artifacts** — which
is **already an architecture/design change**, violating “same architecture”
unless those interfaces already existed unused. If interfaces already exist,
Plan B is **using them as the planning object**; Plan A might **ignore them**
and still string finish-to-start. That is a **representation/behavior**
difference **conditional on unused decoupling**.

**Second comparison (architecture allowed to change).** Decoupling + XaaS +
contract tests: **large** expected effect (DORA/TT). That effect is
**architecture + interaction mode**, even if plans then mention services.

**Separation:** **PLANNING EFFECT** (using existing contracts as the
prerequisite instead of team-finish) is **small-to-moderate and conditional**.
**ARCHITECTURE EFFECT** is **large** in the DORA evidence base.

---

## Phase 22 — Reverse counterfactual

**Loose coupling + impose project/team-centric planning.**

Could flow degrade? **PUBLIC EVIDENCE adjacent:** DORA 2019 **CAB** is a
planning/governance overlay associated with worse performance **even as a
process**, not as architecture. SAFe **cadence and PI commitments** add
synchronization **by design**; if teams were already independently deployable,
a **hard** PI “nothing ships off-cadence” rule could add wait — **INFERENCE**
from framework mechanics, **not** a measured SAFe-on-DORA-elites study.
**Partial yes:** process/planning **can** add gates. **Not proven** that
*feature epics vs service epics* is the damaging part vs **approvals and
forced sync**.

**Tight coupling + impose capability-oriented planning (labels/contracts on
paper).**

Does flow improve? **If contracts are not implemented and testable, NO**
(relabeling test). **Limit: capability planning cannot substitute for
decoupling.**

This is one of the strongest tests: **architecture bounds the planning
effect from above.**

---

## Phase 23 — Feedback loop

Proposed loop: arch/ownership coupling → cross-team deps → project
coordination → synchronized planning → org commitments → less independent
change → pressure to keep boundaries → more coupling.

| Arrow | Public evidence | Inference | Contrary | Conf. |
| --- | --- | --- | --- | --- |
| Coupling → deps | DORA, TT | Direct | Necessary deps remain | High |
| Deps → project coordination | SAFe designed response; PMO tradition | Common | Some orgs coordinate via architecture guilds not PMO | Med |
| Coordination → synchronized planning | PI Planning | SAFe-specific | Kanban/flow orgs | Med |
| Sync planning → commitments | PI objectives | | Inspect-and-adapt exists | Med |
| Commitments → less independent change | Agile: plan vs change; DORA CAB | Over-commitment | Loose teams still deploy (DORA) | Low–med |
| Less independence → preserve boundaries | Conway bidirectional | Plausible | Inverse Conway deliberately changes boundaries | Low |
| Preserve → more coupling | Conway | Speculative as *loop* | Orgs do re-architect | Low |

**Loop as a whole: C / speculative.** Individual early arrows supported;
closing arrows **INFERENCE**.

---

## Phase 24 — What existing practice already solves

| Practice | Already covers |
| --- | --- |
| DORA | Architecture + independent delivery + wait/handoff/approvals |
| Team Topologies | Boundaries + blocking vs XaaS |
| POM | Outcomes + empowered teams; **not** specialist-platform coupling |
| Platform engineering | Self-service **capabilities** as products |
| API/contract-first | Parallel development + evolution rules |
| Lean | Queues, flow, local optimization |
| SAFe | Cross-team sync + value-stream/ART planning |
| Systems engineering / SBCE | Interfaces/constraints + concurrent subsystems |

**What remains after that map?** Not “capability reasoning” as a missing
physics. Remainder is at most: **(1)** using **completion vs contract**
explicitly in **portfolio/program** representations when architecture already
allows it; **(2)** **authority/governance** as contracts, which PE
policy-as-code partially covers; **(3)** specialist domains that are neither
stream products nor IDP APIs yet. **(1)** is a **narrow planning** point.
**(2)–(3)** are **not uniquely a planning-object theory**.

---

## Phase 25 — Strength labels (major conclusions)

| Conclusion | Label |
| --- | --- |
| Independent architecture/teams associated with better delivery performance | **EMPIRICALLY SUPPORTED** (survey, correlational) |
| Contract/interface enables parallel *development* vs waiting for full implementation | **CONCEPTUALLY SUPPORTED** (Parnas, CDC); **PRACTITIONER GUIDANCE** (Pact); DORA associates contract tests with coupling capability |
| XaaS/self-service changes consumer planning target and amortizes coordination | **PRACTITIONER GUIDANCE** (TT, CNCF PE) |
| Outcome planning ≠ engineering decoupling | **CONCEPTUALLY SUPPORTED** (POM scope) |
| Project/feature objects *cause* coupling | **UNSUPPORTED** as independent cause |
| Capability *vocabulary* changes flow | **UNSUPPORTED** (fails relabeling) |
| Planning object independently as important as architecture | **UNSUPPORTED** |
| CAB/process gates affect performance | **EMPIRICALLY SUPPORTED** (association) — this is **process/governance**, overlapping planning |
| Reinforcing loop | **INFERENCE** |
| Plan B with frozen architecture beats Plan A | **INFERENCE**, conditional on unused interfaces |

---

## Phase 26 — Verdicts

**Verdict 1 — Planning causality: B**  
Planning representation can affect flow (especially **completion vs
contract**, **forced cadence**, **external approvals**), but **architecture
and organizational coupling are stronger** in the public evidence. **C is
close** for *portfolio ontology* specifically.

**Verdict 2 — Contract / interface effect: B**  
Contracts/interfaces enable materially more **independent and parallel
development** under identifiable conditions (stable/hidden-implementation
interfaces, verification of doubles). They **do not remove** runtime,
capacity, or unset governance coupling. **C is close** if one treats all
benefits as “just architecture” — they *are* architectural artifacts that
planning may **use or ignore**.

**Verdict 3 — Capability as planning object: C**  
As a **named planning object**, it **mostly relabels** service / interface /
platform-capability / modularity practice. **B** only in the narrow sense
that **changing dependency semantics to consumable contracts** is useful —
that is **not unique to the word capability**.

**Verdict 4 — Architecture vs planning: B**  
**Architecture dominates** the dependency structure that DORA measures.
Planning/governance can **reinforce or add gates** (CAB, PI commitments,
finish-to-start strings). Not **A**. Not fully **C** because process is not
zero.

**Verdict 5 — Reinforcing loop: C**  
Early arrows supported; the **loop as a whole is speculative**.

**Verdict 6 — Distinctiveness: C**  
Architecture, Team Topologies, POM, platform engineering, Lean, and
contract-first **already explain** the result. Distinctive remainder is thin:
**don’t plan finish-to-start when a sufficient contract already exists.**

**C is an acceptable result.**

---

## Phase 27 — Kill / narrow / keep

**Kill criteria vs evidence**

| Kill if… | Status |
| --- | --- |
| Architecture explains nearly all observed *delivery-performance* effects | **Mostly yes** (DORA) |
| Planning representation never changes behavior | **No** — CAB, cadence, completion gates can |
| Capability language only renames service/interface deps | **Yes for typical relabeling** |
| POM + TT already provide equivalent reasoning | **Mostly yes** (outcomes + XaaS) |
| No evidence of any independent planning/process effect | **False** (DORA CAB; SAFe designed sync) |

**Narrow if…** planning matters when it changes contracts/interfaces;
mainly reinforces architecture; benefits for repeatable/stable work; novel
work still needs collaboration. **These are supported.**

**Keep investigating if…** representation changes when teams can begin
**without** architecture change. **Only weakly supported** (using *already
available* contracts). Enabling parallelism **without** architecture change
in a **coupled** system: **not supported**.

**Decision: NARROW the planning hypothesis.** Do not keep the strong form
(planning object is a primary independent cause; capability roadmaps as such
improve flow). Do not fully kill: **completion-based planning can serialize
work that a sufficient contract would allow to overlap**, and
**process/governance planning can add wait independent of architecture.**

---

## Hypotheses A / B / C (arrows)

**Hypothesis A (planning creates coupling).** **Partially supported** only
for **process gates and finish-to-start representations** that ignore
existing interfaces. **Not supported** as the main creator of technical
coupling.

**Hypothesis B (coupling creates the planning model).** **Better supported**
as the primary direction (DORA, TT, SAFe as a *response* to many-team
features). Planning **makes dependencies visible** (SAFe) more than it
invents them.

**Hypothesis C (reinforcing loop).** **Not accepted as a whole** (Phase 23).
Do not assume C because it sounds sophisticated.

---

## Final synthesis

1. **Does what we plan around actually matter?** **Sometimes, weakly:**
   whether the prerequisite is **team-finish** or **sufficient
   contract/authority**, and whether **process gates** serialize. **Not**
   as much as architecture.
2. **Mostly architecture expressed through planning?** **Yes** as the
   dominant story (Hypothesis B).
3. **Can stable contracts/interfaces change sequencing?** **Yes for
   development overlap** (Parnas, CDC, Pact, SBCE). **Not** for all
   runtime/governance/capacity sequencing.
4. **Does that require changing architecture?** **Usually yes** to get
   DORA-scale effects. **No** only when interfaces **already exist** and
   plans wrongly wait on completion.
5. **Can planning independently create unnecessary serialization?**
   **Plausibly yes** (finish-to-start, CAB, rigid PI ship windows).
   **Empirically stronger for approvals than for “epic vs capability.”**
6. **Does capability language add beyond service/API/interface thinking?**
   **Not in the public evidence**, except as a synonym for **consumable
   platform/service capabilities** already in TT/CNCF.
7. **Where capability-oriented planning fails:** relabeling; vague maps;
   premature contracts; mock drift; new silos; novel work forced through
   fake stability; hiding real coupling.
8. **Centralized coordination:** **displaced and amortized** when XaaS/PE
   works; **not disappeared**; **preserved** for portfolio, SoD, novelty,
   capacity.
9. **Feedback loop:** **does not survive as an evidenced whole.**
10. **Evidence most strongly contradicted:** planning-object identity as a
    **primary** cause of system flow; capability nouns as a **material**
    intervention.
11. **Planning contribution still worth pursuing?** **Only the narrow
    claim:** distinguish **completion dependencies** from **contract/
    interface/authority sufficiency**, and do not serialize on the former
    when the latter is already enough. That is **modularity + TT + CDC**,
    applied to plans.
12. **Next:** narrow the hypothesis (below). Not performed here.

---

## Next action

**Narrow the planning hypothesis.**

Not kill (process/completion semantics are not zero). Not theory
incorporation (too weak and already covered by Parnas/TT/PE). Not field
test of an employer. Not interviews until the hypothesis is the narrow
claim above. Not a comparative worked case until that claim is the only
thing being tested.

---

## Sources

- DORA. “Loosely coupled teams.” https://dora.dev/capabilities/loosely-coupled-teams/ (updated 2025-10-20)
- DORA / Puppet. *State of DevOps Report* (2017). https://dora.dev/research/2017/dora-report/2017-state-of-devops-report.pdf
- DORA. *Accelerate State of DevOps Report* (2019). https://dora.dev/research/2019/dora-report/2019-dora-accelerate-state-of-devops-report.pdf
- Conway, M. E. (1968). “How Do Committees Invent?” *Datamation*. http://www.melconway.com/Home/Committees_Paper.html
- Parnas, D. L. (1972). “On the Criteria To Be Used in Decomposing Systems into Modules.” *CACM* 15(12). https://doi.org/10.1145/361598.361623
- Robinson, I. / Fowler, M. (2006). “Consumer-Driven Contracts.” https://martinfowler.com/articles/consumerDrivenContracts.html
- Pact documentation. https://docs.pact.io/
- Team Topologies. Key concepts; X-as-a-Service newsletter (Mar 2025). https://teamtopologies.com/key-concepts ; https://teamtopologies.com/news-blogs-newsletters/x-as-a-service
- Scaled Agile. “PI Planning.” https://framework.scaledagile.com/pi-planning
- Cagan, M. SVPG. “Product vs Feature Teams”; “Revenge of the PMO.” https://www.svpg.com/
- CNCF TAG App Delivery. Platform Engineering Maturity Model. https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/
- Sobek, D. K., Ward, A. C., & Liker, J. K. (1999). “Toyota’s Principles of Set-Based Concurrent Engineering.” *MIT Sloan Management Review*.
- Liker, J. K., Sobek, D. K., Ward, A. C., & Cristiano, J. J. (1996). “Involving suppliers in product development…” *IEEE Transactions on Engineering Management* 43(2).
- Midler, C. (1995). “Projectification of the firm.” *Scandinavian Journal of Management.*
- Packendorff, J. & Lindgren, M. (2014). Projectification consequences. *SAJEMS.*
- Prior study (baseline only): `drafts/research/public-evidence-planning-and-system-flow-study.md`
