# Methodology distinctiveness analysis

*Non-canonical. Adversarial: try to disprove distinctiveness. Not a
naming brief. Does not modify canonical theory. Does not invent method
steps.*

Labels: **EXISTING CORPUS** | **PUBLIC PRIOR ART** | **ANALYSIS**

This study asks whether a **substantially equivalent methodology**
already exists. Component prior art was already established. Component
prior art ≠ methodological identity.

---

## Part 1 — Candidate methodology (do not invent)

### A. Established foundational model (EXISTING CORPUS)

Frozen: problem (specialization as delivery architecture); six
principles; design doctrine (accidental vs intentional friction);
conceptual loop (intent → capability → experience/realization → outcome
→ learning); capability vs realization; organizational independence;
authority ≠ execution ≠ ownership ≠ privilege; composition without
domain takeover; encode repeatable / collaborate on novel; human
realization valid.

Positioning (post-research): **synthesis / cross-domain reasoning
model**, not a new discipline. Method section explicitly **not** the
identity of the project.

### B. Existing application guidance (EXISTING CORPUS)

`docs/12-method/`: pick one painful recurring intent → **trace**
interactions (what it decides, who holds authority, what it waits on) →
**evaluate** value (intentional vs accidental) → **identify** what the
system can already accomplish (three-way test: ability vs experience vs
fulfillment) → **decide** whether/how to encode → **design** experience
and realization (keep designed friction) → **operate** and evolve.

Brownfield eleven-step sketch maps onto that. Anti-patterns are
diagnostic warnings. Operating-model pages are vignettes, not a firm OM.

The method README: not a transformation program; can conclude “leave it
alone”; order is reading order not a gate sequence; **optional**.

### C. Repeatable moves in worked cases (EXISTING CORPUS / prior research)

`drafts/research/cross-case-application-synthesis.md`: cases were
**prompt-shaped**. Load-bearing moves resembled the method plus
wrong-success / composite-seams questions. Verdict there: **not a
shippable unique method**; overlap with PE/DevOps/SRE/TT high.

### D. Still missing (ANALYSIS)

Entry/stopping criteria beyond “one painful intent”; facilitation
scripts; required artifacts; measurement of *this* method’s effect;
independent practitioner validation; exception handling for the method
itself; how to choose among encode / collaborate / refuse / leave-alone
when authorities disagree (open questions: incentives, stewardship).

### Strict status

**Enough for a conceptual / reasoning model: yes.**  
**Enough for early application guidance: yes (`12-method`).**  
**Enough to call a mature or even “emerging named methodology” as the
project’s identity: no.** The corpus **refuses** that identity. Cross-case
research refused “method discovery.”

**ANALYSIS:** treat what follows as an **emerging candidate method
layered on a reasoning model**, not as a completed methodology.

---

## Part 2 — Neutral fingerprint

| Property | Neutral description |
| --- | --- |
| **Unit of reasoning** | The sociotechnical system through which a *class of intended result* becomes an outcome—not a team, queue, or platform as the default unit |
| **Entry** | One recurring, painful intended result someone will own |
| **Object** | The actual path of work (tickets, waits, decisions, people), not the documented process |
| **Core distinctions** | System ability vs how it is fulfilled vs how it is consumed; specialist knowledge vs system ability; necessary vs accidental delay; authority vs doing vs owning vs being allowed |
| **Specialization** | Keep deep domains; stop using the domain as the default *request interface* for routine work |
| **Organization** | Boundaries may be valuable (SoD, law, judgment); they need not be the consumer’s routing map |
| **Expertise** | What someone knows ≠ what the organization can accomplish with it |
| **Human realization** | A named expert can *be* how an ability is fulfilled; that is not an immature stage |
| **Abstraction** | Hide routing from the routine path; keep ownership, authority, provenance findable |
| **Authority** | Who may decide correctness ≠ who performs; invoking an ability does not grant domain power |
| **Composition** | Combining abilities transfers consumer obligation and seam accountability, not contributor-domain power; safe parts ≠ safe whole |
| **Friction** | Judge delay by value to the whole system, not by speed |
| **Encoding** | When work is understood and repeated, consider reusable structure; do not encode guesses |
| **Novel work** | Collaborate; do not fake a stable interface |
| **Outcomes** | Improve the class-of-intent path (flow, risk, quality, learning)—not ticket count or automation % |
| **Learning** | Evidence can change what the system believes; organizations may ignore it |
| **Federation** | No single enterprise graph required; obligations before identical implementations |
| **Application** | Trace → evaluate waits/decisions → name existing abilities → encode or collaborate → redesign consumption/fulfillment → observe |
| **Wrong success** | Green local SLAs, portals, or sprints while the end-to-end intended result is unchanged |

---

## Parts 3–4 — Search classes and functional equivalents

**PUBLIC PRIOR ART** (primary or official where used):

| Family | What it is | Fingerprint overlap |
| --- | --- | --- |
| **DevOps / CD** | Debois; Humble & Farley *Continuous Delivery* | Flow, feedback, automate delivery; one boundary (dev/ops) |
| **DORA / Accelerate** | dora.dev; Forsgren et al. | Coupling, wait, independent deploy—**metrics/capabilities research**, not a change method for specialist authority |
| **SRE** | Google SRE book | Toil, error budgets, learning; production, not all specialist domains as “abilities” |
| **Platform Engineering** | CNCF PE maturity; platformengineering.org | Self-service *capabilities*, DX; tends toward platform product |
| **Team Topologies** | Skelton & Pais 2019; teamtopologies.com | Teams, interaction modes, XaaS, cognitive load, flow |
| **POM / SVPG** | Cagan / svpg.com | Outcomes, empowered teams; product, not security-as-ability |
| **VSM / Flow Framework** | Kersten *Project to Product*; flowframework.org | Value-stream mapping and Flow Metrics (time, efficiency, load, distribution) |
| **FAST** | Quartel, fastagile.io | Fluid teams around work—**reorg method**, opposite of “keep specialties, change interface” |
| **IBE / 1ES** | Capital One IBE; Microsoft 1ES | Intent/automation; engineering system as product; not human-realized novel assessment as first-class |
| **Golden paths** | Spotify/PE practice | Experience layer; corpus already says portal ≠ system |
| **INCOSE / ISO/IEC/IEEE 15288** | Systems engineering life cycle | Stakeholder needs, architecture, V&V, interfaces, composition |
| **Parnas 1972; CDC** | Information hiding, contracts | Ability vs implementation; parallel development |
| **DoD JCIDS / CBP** | Capabilities-Based Assessment | “Capability” = mission effect / gap / materiel vs DOTMLPF—**portfolio acquisition**, not software-delivery consumer interface |
| **STS (Trist & Bamforth; later STS design)** | Joint optimization | Foundational stance; not a software specialist-routing method |
| **Checkland SSM** | Soft systems | Rich pictures, CATWOE—generic analysis |
| **Beer VSM** | Viable System Model | Recursion, variety, management cybernetics |
| **ToC (Goldratt)** | Constraint | Find/elevate bottleneck—not specialist authority model |
| **Lean / Poppendieck** | Waste, queues, whole | Friction/flow |
| **EA capability maps** | TOGAF-style | Inventory risk (corpus anti-pattern catalog-first) |
| **IAM / SoD / safety engineering** | Authority vs privilege | Strong on authority/execution; weak on delivery-path redesign |
| **DevSecOps / policy-as-code** | Governance in pipeline | Encode settled controls; risk of automating judgment |

**No search found a single named software-delivery methodology** whose
official purpose is: *keep specialist domains, make routine consumption
independent of org routing, treat human fulfillment as a legitimate
realization class, and forbid composite/domain-authority collapse*, with
a documented diagnostic sequence of that shape.

**ANALYSIS:** absence of a *name match* is not absence of *practice*.
Principal engineers already mix TT+PE+Lean+SE+IAM.

---

## Part 5 — Nearest-neighbor matrix

Serious neighbors only. Y / P / N / U.

| Fingerprint item | TT | PE | Lean/VSM/Flow | SE/15288 | POM | SRE | JCIDS/CBP |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Unit = system for a class of intent | P (stream/value) | P (platform product) | Y (value stream) | P (system of interest) | P (product) | P (service) | P (mission) |
| Entry = one painful intent | N | N | P (map a stream) | P | P | P (SLO/incident) | P (CBA mission) |
| Trace actual waits/decisions | P | P | Y | P | N | P | N |
| Ability vs fulfillment vs consumption | P (XaaS vs collab) | P (capability vs portal) | N | Y (function vs solution) | N | N | P (capability vs materiel) |
| Human fulfillment first-class | P (enabling/complicated) | N (self-service bias) | N | P (operators) | P (discovery) | P (toil vs judgment) | Y (DOTMLPF non-materiel) |
| Org not required routing | Y (XaaS) | Y | P | N | P | P | N |
| Authority ≠ execution | N | N | N | P | N | P | P (validation vs acquisition) |
| Composition without domain takeover | N | N | N | P (SoI vs enabling systems) | N | N | P (joint vs service) |
| Accidental vs intentional friction | P (blocking deps) | P | Y | P | N | P | N |
| Encode vs novel | P (XaaS after collab) | P | P | P | Y (discovery) | Y (toil) | P |
| Wrong success / local vs system | P | P | Y | P | Y (output vs outcome) | Y (local green) | N |
| Federation without one graph | P | P | P | Y | N | N | Y (joint) |
| Repeatable diagnostic sequence | P (team interactions) | P (maturity) | Y (VSM) | Y (ISO processes) | P | P | Y (CBA) |
| Cross software specialties as same method | P (team types) | P (platform) | P | Y (any system) | N | N | N (military) |

**Meaningful differences (ANALYSIS):**

- **TT:** strongest on teams/interactions; unit is **team**, not
  system-ability; Inverse Conway is a valid *other* lever.
- **PE:** strongest on self-service consumption; weak on “do not
  platformize authority.”
- **Lean/VSM/Flow:** strongest on wait/flow metrics; weak on
  capability/realization/authority split.
- **SE:** strongest on interfaces/composition/V&V; not a method for
  *software org as delivery API* or product/platform category errors.
- **POM:** strongest on outcomes; not specialist-domain delivery.
- **SRE:** strongest on production learning; not identity/network/security
  as first-class *abilities*.
- **JCIDS:** word “capability” is a **false friend**—mission gap
  assessment, not consumer routing.

---

## Part 6 — Subsumption

| Neighbor | If followed competently, same analysis/decisions? | Verdict |
| --- | --- | --- |
| Team Topologies | Often same *interaction* design (XaaS vs collab); may **reorg** when this corpus would **keep teams and change the interface** | **PARTIALLY SUBSUMES** / **COMPLEMENTARY** |
| Platform Engineering | Same when the answer is a paved path; **diverges** when the answer is human realization or refuse-to-automate | **PARTIALLY SUBSUMES** |
| Lean VSM / Flow Framework | Same wait diagnosis; **does not** name ability vs portal vs team | **PARTIALLY SUBSUMES** |
| ISO 15288 / INCOSE | Same composition/interface discipline; **not** the specialist-routing diagnosis | **COMPLEMENTARY** |
| POM | Same outcome/output; **not** the specialist path | **COMPLEMENTARY** |
| SRE | Same toil/encode; **narrower domain** | **COMPLEMENTARY** |
| JCIDS | **ORTHOGONAL** (acquisition vs delivery interface) | **ORTHOGONAL** |
| FAST | **ORTHOGONAL** (dissolve static teams) | **ORTHOGONAL** |
| DevOps | One-boundary subset | **PARTIALLY SUBSUMES** (historically) |

**No FULLY or MOSTLY SUBSUMES** by a **single** named method.

---

## Part 7 — Combination test

**Smallest realistic reproduction stack:**

**Team Topologies** (blocking vs XaaS, don’t confuse team types)  
**+ Platform Engineering** (self-service capabilities, golden paths)  
**+ Lean/VSM** (trace waits, local vs global)  
**+ systems engineering / Parnas** (interfaces, composition, hiding how)  
**+ POM** (outcomes not output)  
**+ SRE/DevSecOps + IAM/SoD** (toil vs judgment; authority vs privilege)

**How much work remains? C, with B nearby.**

A competent principal engineer **already** combines these. They would
often reach **the same interventions**. What the stack does **not** hand
them as one procedure: the **three-way test** (ability / consumption /
fulfillment), **explicit** “human fulfillment is not immature,”
**composite owns seams not domains**, and **evaluate each wait as
decision vs routing** in one pass across security/identity/network *and*
platform.

That is **integration logic**, not new physics. It is **more than
repackaging slogans** (not A) and **less than a major gap** (not D).
Between B and C: **C** for *decisions*; **B** for *having a single
diagnostic script*. This study scores **C** on Verdict 5 because the
question is whether combination **reproduces the methodology’s results**,
and synthesis-value already found **same designs**.

---

## Part 8 — Relationship novelty

| Relationship | Prior art | Implied? | Decision change? |
| --- | --- | --- | --- |
| specialization ↔ system ability | TT/PE partial | Y | Y if stop team-rename |
| ability ↔ fulfillment | Parnas, SE | Y | Y if swap DBA/Terraform |
| consumption ↔ fulfillment | PE “portal wraps tickets” | Y | Y |
| organization ↔ consumption | TT XaaS, Conway | Y | Y |
| authority ↔ execution | IAM, SoD, safety | Y | Y for agents/tools |
| ownership ↔ routing | TT; “discoverable ownership” is a crisp phrase | P | Y |
| composition ↔ authority | SE + IAM rarely **joint** in software methods | P | Y if platform absorbs Security |
| repeatability ↔ encoding | Lean, SRE toil, Principle 4 neighbors | Y | Y |
| novelty ↔ collaboration | TT collaboration mode; POM discovery | Y | Y |
| local ↔ system outcome | Lean, POM, DORA | Y | Y |
| intent ↔ constraints | POM, SE requirements | Y | Y |
| learning ↔ evolution | DevOps, SRE | Y | weak extra |

**ANALYSIS:** almost all **implied** in the stack. **Joint explicitness**
in software-delivery methods is the remainder—not an original ontology.

---

## Part 9 — Application sequence

Corpus support for the listed sequence: **yes** as `12-method` +
brownfield + identifying-capabilities three-way test. **Not** a gated
lifecycle (corpus says so).

**Existing methods with similar sequences:** Lean VSM (map, identify
waste, improve); SSM (express situation, analyze, take action); ISO
15288 (tailored processes); TT (assess interactions, change modes);
brownfield PE (pick a path, pave it).

**Generic:** scope, observe as-is, classify, intervene, learn.

**Distinctive combination of questions** (not unique steps): three-way
test + authority/wait fields + encode-vs-novel + composite seams in
**one** pass.

**Missing for a real methodology:** see Part 21.

---

## Part 10 — Decision rules

| Rule (corpus) | Classification |
| --- | --- |
| Encode repeatable; collaborate on novel | **KNOWN IDEA / DIFFERENT EXPRESSION** (Lean, SRE toil, TT collab→XaaS, POM discovery) |
| Abstract routing, not accountability | **SYNTHESIZED RULE** (TT XaaS + SoD; phrase is local) |
| Authority ⇏ execution; execution ⇏ authority | **COMMON PRACTICE** (IAM/safety) applied to delivery/composition |
| Depend on abilities more than current fulfillment | **KNOWN** (Parnas/SE) |
| Remove accidental friction; design intentional | **KNOWN** (Lean + security “controls aren’t waste”) |
| Optimize the engineering system; don’t centralize realization unnecessarily | **SYNTHESIZED** (Lean whole + federation/STS) |
| Human realization is valid | **KNOWN** in STS/JCIDS non-materiel / enabling teams; **under-emphasized in PE** |
| Invocation ≠ authority | **COMMON** IAM; **SYNTHESIZED** as anti-pattern for agents |
| Ticket/automation % ≠ success | **KNOWN** (Goodhart, Lean, POM) |
| Composite ≠ own the parts | **KNOWN** in SE/federalism; **SYNTHESIZED** for platform/security |

No **POTENTIALLY DISTINCTIVE** rule survived translation except as
**packaging of several known rules into one checklist**.

---

## Part 11 — Category errors

| Error | Already prevented by | Integrated prevention |
| --- | --- | --- |
| team = ability | TT (partial), Inverse Conway | **Stronger** via naming test |
| platform = ability | Honest PE | Corpus explicit |
| portal = system | Lean, PE war stories | Experience vs realization |
| automation = expertise | SRE toil | Principle 4 |
| invocation = authority | IAM | Named anti-pattern |
| ownership = routing | XaaS | Discoverable vs required |
| local = system | Lean, POM, DORA | Principle 2 |
| repeated = automate | SRE/Lean | Decide-what-to-encode |
| composite = domain takeover | SoD, SE | Composition tables |
| contract = truth | CDC liabilities; “lying contract” | Conceptual model |

Existing methods **each** catch **some**. The **integrated list** is the
practical contribution—**category-error prevention as a bundle**.

---

## Part 12 — Domain transfer

**EXISTING CORPUS** applies the same structure to platform, infra,
security, network, identity, data, SRE, product.

**Neighbors:** SE and STS transfer to any domain by design. TT team types
transfer. PE is platform-centric. POM is product-centric.

Cross-domain reach is **useful, not distinctive** (SE already has it).

---

## Part 13 — Human-expertise combination

Sought: human fulfillment legitimate + encoded fulfillment + specialist
judgment + abstract routine routing + explicit domain authority +
escalate novel/high-consequence.

**PUBLIC PRIOR ART:** STS (human work as system); JCIDS DOTMLPF
(non-materiel); TT enabling + complicated-subsystem + collaboration;
SRE (error budget, toil); safety (human in the loop); PE (weaker on
human-as-realization).

**The combination is established in pieces.** Simultaneous **first-class
status in a software-delivery diagnostic** is **less common in PE-centric
methods**, not unknown.

---

## Part 14 — Authority

**PUBLIC PRIOR ART:** RACI/DACI (weaker); IAM (privilege vs role);
nuclear/aviation safety (authority to stop work); ISO 15288
responsibility; military command vs execution; composition.md’s split is
**aligned with** those, not original.

---

## Part 15 — Composition

**PUBLIC PRIOR ART:** emergence (systems theory); interface control;
safety of composition; SoD. Corpus tables are a **clear software
rendering**. **Mostly standard SE thinking.**

---

## Part 16 — Different words, same thing

| Claimed difference | Survives translation? |
| --- | --- |
| “Capability not team” | **No**—TT/Inverse Conway/PE |
| “Experience vs realization” | **Mostly no**—portal vs path |
| “Organizational independence” | **Mostly no**—XaaS + paved path |
| “Engineering system unit” | **Partial**—Lean value stream + 1ES “engineering system”; corpus **scopes to a class of intent / composite seams** more tightly than “the platform” |
| “Human realization valid” | **Partial**—against PE maturity ladders; yes in STS/SRE |
| “Composite seams without domain takeover” | **Partial**—SE + SoD; rarely one software method |

**Ruthless result:** most differences **disappear**. Remainder is
**scoping unit + bundled diagnostic**, not new kinds.

---

## Part 17 — Historical precedent

This is largely **STS joint optimization + Lean whole-system + Parnas
hiding + Conway** applied to **post-DevOps specialist software orgs**.
Cybernetics (Beer) and ToC are **adjacent**, not identical.

**Say so:** an application of older established methods to modern
multi-specialty software delivery, with PE/TT vocabulary in the
neighborhood.

---

## Part 18 — Uniqueness standard (levels)

| Level | Evidence |
| --- | --- |
| Original components | **No** |
| Original relationships | **No** as physics; **maybe** as a **named bundle** |
| Original application method | **No** as unique sequence; **thin** as combined questions |
| Original domain transfer | **No** (SE) |
| Original vocabulary | **Irrelevant** to this study |
| Original synthesis | **Modest**—integration of known rules for specialist-delivery joins |

---

## Part 19 — Legal / scholarly (not legal advice)

- **Conceptual distinctiveness:** modest synthesis, not a new kind.
- **Scholarly novelty:** unlikely for components; a paper on the
  **bundle** would need empirical method tests, which do not exist.
- **Trademark/name:** out of scope; unique name ≠ unique method.
- **Copyright:** expression of the docs, not the ideas.
- **Patentability:** not analyzed; ideas listed are generally known.

---

## Part 20 — Falsifiers

**“This methodology already exists” if:**

- One official method reproduces the fingerprint (not found).
- **Or** a normal combination of TT+PE+Lean+SE+IAM produces the same
  analyses and decisions (**largely yes**—this is the strongest
  falsifier).
- Translation into neutral language removes differences (**mostly yes**).
- Remaining differences are slogans (**risk: yes**).

**“Meaningfully distinct though components have prior art” if:**

- Practitioners using the stack **without** the bundle **repeatably**
  ship portal-as-system, team-as-ability, or platform-as-Security.
- Independent cases show the **three-way test + authority/wait + human
  realization** changing a decision the stack missed.
- That evidence is **not in hand** (paper cases were prompt-shaped).

---

## Part 21 — Gaps (do not fill)

Before “mature methodology”: independent field validation; entry and
stop rules; artifact set (optional, proportional); facilitation;
measurement of *method* effect vs DORA/flow metrics; handling
authority conflict; practitioner inter-rater reliability of
intentional/accidental classification; IR vs design-time (cross-case).

---

## Part 22 — Verdicts

**1 — Existing equivalent: B**  
Strong neighbors; **none** substantially equivalent **as one named
method**. **C is close** if “equivalent” means the **combination**.

**2 — Component novelty: C** (D close)  
Components mostly have prior art.

**3 — Relationship distinctiveness: C** (B close)  
Mostly restates systems/Lean/TT/PE/IAM; **combination** of relationships
is the only remaining claim.

**4 — Application-method distinctiveness: C**  
Trace/evaluate/encode is conventional systems/Lean analysis with a
distinctive **question set**, not a new sequence. **D** if we take the
corpus literally that there is **no** method identity yet.

**5 — Combination test: C**  
A normal combination of established practices **mostly reproduces
results**. Integration of the diagnostic **script** is non-zero (**B**
for packaging).

**6 — Cross-domain distinctiveness: C**  
Breadth useful; SE/STS already broad.

**7 — Methodology status: C**  
**Reasoning model with early application guidance.** Not mature. Calling
it an “emerging methodology” **overstates** relative to the corpus’s own
disclaimer and unvalidated sequence.

**8 — Uniqueness claim: C**  
Only **synthesis/packaging** distinctiveness is supportable today.
**Not B** until field evidence shows the bundle changes decisions the
stack misses.

---

## Part 23 — Kill test

**Does this methodology already exist?**

**FUNCTIONALLY MOSTLY.**

No single branded method is a drop-in equivalent. A competent
practitioner combining Team Topologies, Platform Engineering, Lean value-
stream mapping, systems engineering / information hiding, product
outcome thinking, and standard authority/SoD practice will typically
reach the **same class of designs**: pave routine paths, keep novel
collaboration, do not treat portals as the system, do not absorb Security
into a platform “yes,” measure waits not vanity automation.

What does **not** already exist as one **official** procedure is a short
diagnostic that **forces** the three-way ability/consumption/fulfillment
test, treats **human fulfillment as non-immature**, and checks
**composite seams vs domain authority** on every specialist hop in
software delivery. That is a **narrow packaging remainder**, not a new
methodology species. If that remainder does not change decisions versus
the stack, distinctiveness **collapses to vocabulary**.

*(Under 500 words.)*

---

## Part 24 — Uniqueness statements

**SUPPORTED today:**

The work differs from Team Topologies, Platform Engineering, Lean/VSM,
and systems engineering **taken separately** by **holding in one
diagnostic** (optional `12-method`): system-ability vs consumption vs
fulfillment (including human fulfillment), org routing vs designed
control, and composite accountability without domain takeover—aimed at
**joins among software specialties**. It does not claim original
components. It is a **reasoning model with early application guidance**,
not a validated methodology.

**NOT SUPPORTED:**

“This is the first methodology to treat delivery as a system / to use
capabilities / to preserve specialization / to embed governance / to
compose subsystems / to distinguish automation from judgment / to apply
systems thinking to software.”  
“No existing approach can analyze or change engineering systems this
way.”  
“The methodology is unique because the words are unique.”

---

## Part 25 — Next action

**Narrow the methodology to the surviving distinctive contribution.**

Not stop (no single equivalent). Not “explicitly build on one” as the
only parent (several). Not continue expanding a methodology identity the
corpus already refuses. Not practitioner/field validation **first** while
the claim is still wider than the remainder (validation later, on the
**narrow bundle**). Not deeper historical search as the blocker
(history already shows STS/Lean/Parnas).

Narrowing means: treat **category-error prevention + three-way test +
authority/wait evaluation** as the method-like core; do **not** grow
gates, artifacts, or a named methodology until that core is shown to
change decisions the TT+PE+Lean+SE stack misses.

**Not performed here.**

---

## Sources (minimum)

**EXISTING CORPUS:** principles; design doctrine; `12-method/*`;
brownfield; composition; organizational independence; how-to-critique;
prior-art.md; `drafts/research/synthesis-value-analysis.md`;
`cross-case-application-synthesis.md`.

**PUBLIC PRIOR ART:** Conway 1968; Trist & Bamforth 1951; Parnas 1972
CACM; Humble & Farley 2010; DORA/Accelerate; Google SRE 2016; Skelton &
Pais 2019 / teamtopologies.com; CNCF PE maturity; Kersten *Project to
Product* / flowframework.org; Cagan/SVPG; ISO/IEC/IEEE 15288 / INCOSE;
JCIDS/CBA (DoD); FAST (fastagile.io); Checkland SSM; Goldratt ToC; Beer
VSM; Poppendieck Lean Software Development.

---

## Report checklist (for the assistant)

1. Functional equivalent: **no single method; combination mostly yes**  
2. Verdicts: B, C, C, C, C, C, C, C  
3. Nearest: **Team Topologies** (org/flow) with **PE** and **Lean/VSM**  
4. Combination: **TT + PE + Lean/VSM + SE/Parnas + POM + IAM/SoD/SRE**  
5. Smallest difference: **bundled diagnostic** (three-way test, human
   realization, composite/authority, wait=decision vs routing)  
6. Against: combination reproduces designs; translation kills most diffs  
7. For: PE-only/TT-only/reorg-only false solutions; joint category errors  
8. Maturity: **reasoning model + early guidance**  
9. Missing: validation, stop rules, conflict handling, method metrics  
10. Supported statement: Part 24  
11. Prohibited: Part 24  
12. Next: **narrow to surviving distinctive contribution**
