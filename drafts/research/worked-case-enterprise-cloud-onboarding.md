# Worked case: enterprise cloud onboarding

*Non-canonical research note. Applies the existing body of knowledge to a
realistic enterprise problem. Does not add theory, principles, roles, or
names. Does not edit the canonical corpus or the frozen essay.*

**Question under test.** Does the existing model produce useful, distinct
engineering insight when applied to a mature regulated enterprise that
already has CI/CD, IaC, a platform team, an IDP, scanning, identity,
observability, standards, service ownership, and Team Topologies-inspired
structure — and still takes 4–8 weeks to onboard a production workload?

## 1. Customer / product intent

A product team wants a new customer-facing application in production: a
claim-status API that authenticated customers can call. The customer
outcome is: they can see claim status securely, reliably, and in
compliance with the firm's data-protection obligations.

The product team owns that customer outcome. They do not own identity,
network placement, or the security standard.

## 2. Relevant engineering intent

At a level the product engineer can own: **run this eligible
customer-facing workload in a production environment that satisfies
identity, connectivity, data-class, observability, reliability, and
regulatory obligations.**

They are not trying to "open eight queues." They are trying to cause a
resulting state: the application is live under known constraints.

## 3. The engineering system in scope

The relevant system is the one through which *this class of intent* —
onboard a routine customer-facing production workload — moves toward
outcome. It is not "the whole enterprise." It is not "the platform."

It includes product engineering, cloud/platform, identity, networking,
security, data, observability, SRE, and compliance as *sources of
expertise and authority*, not as sequential stages the consumer must
assemble.

In corpus terms this is already a candidate composite: the same shape as
`LaunchRegulatedAPI` / `DeployApplication`.

## 4. Current path (intent → outcome)

Today the consumer is the integrator.

| Step | What happens | Typical wait |
| --- | --- | --- |
| 1 | Request cloud subscription / account / environment | Days |
| 2 | Request network connectivity (VNet/subnet, peering, NSG) | Days |
| 3 | Request DNS and certificates | Days |
| 4 | Request identity groups, service principals, workload identity | Days |
| 5 | Select and provision data services | Days |
| 6 | Request security review | Days–weeks |
| 7 | Satisfy policy / compliance checks | Days, often overlapping 6 |
| 8 | Integrate observability (agents, dashboards, alerts) | Days |
| 9 | Establish reliability / operational expectations | Days |
| 10 | Production approval | Days |

Each specialist team is competent, has legitimate authority, and mostly
meets its local SLA. Elapsed time is still 4–8 weeks because waits
*stack*, context is re-entered, and incompatible constraints surface late
(identity model vs. network segmentation vs. data class).

The portal already exists. Several of the steps are forms. Most forms
open tickets.

## 5. Where the organization is the delivery interface

For each step: expertise is real; the *interface* is usually the team.

| Step | Expertise | Implicit capability | Experience today | Realization today | Authority | Ownership (as practiced) | Execution | Constraint | Coordination vs collaboration |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 Environment | Cloud landing-zone design | Provide an eligible environment | Portal + ticket | Cloud team applies Terraform / account factory | Cloud / platform | Cloud team queue | Cloud engineers | Mix: residency and isolation are intentional; "which form" is accidental | Almost entirely coordination |
| 2 Connectivity | Network architecture | Provide connectivity for an eligible workload | Ticket / CMDB | Network team + firewall change | Networking | Network queue | Network engineers | Segmentation and blast radius intentional; discovering the right subnet accidental | Coordination; rare novel topology is collaboration |
| 3 DNS / certs | PKI, naming | Provide a name and trust material | Ticket | Network / PKI | Networking / PKI | Same | Same | Public vs internal naming rules intentional | Coordination |
| 4 Identity | IAM, workload identity | Establish workload identity | Ticket + AD/Entra request | Identity team | Identity | Identity queue | Identity engineers | Least privilege, no standing admin: intentional | Coordination for standard app identity; collaboration for novel federation |
| 5 Data | Data classification, storage patterns | Provide storage matching data class | Catalog + tickets | Data + cloud + security | Data (class), security (control) | Split across queues | Mixed | Data-class rules intentional; assembling DBA + network + identity accidental | Coordination for standard SQL; collaboration for new class |
| 6 Security review | Threat modeling, control selection | Assess design / attest controls | Intake + review meeting | Security architects | Security | Security calendar | Architects | Independent assessment of *novel* risk is intentional; re-applying a settled pattern to every similar app is accidental in *shape* | Mostly duplicated interpretation wearing collaboration's clothes |
| 7 Compliance | Regulatory mapping | Attest obligations for this class | Checklist + GRC tool | Compliance + security | Compliance / legal | GRC queue | Analysts | Evidence of control is intentional | Coordination when the mapping is already known |
| 8 Observability | Telemetry design | Observe the service | Ticket / "install our agent" | SRE / observability | Reliability / observability | Observability team | Engineers | Minimum signals for incidents: intentional | Coordination for standard gold signals |
| 9 Reliability | Error budgets, ops | Establish reliability expectations | Runbook template + meeting | SRE | Reliability | SRE | Mixed | On-call and SLO for customer-facing: often intentional | Mix: standard expectations are encodeable; first-of-kind SLO is collaboration |
| 10 Prod approval | Change / SoD | Authorize production | CAB / change ticket | Governance | Independent change authority | Change board | Approvers | Separation of duties for production: intentional | Coordination if rubber-stamp; collaboration if genuine independent judgment |

**Diagnostic (Principle 1):** routine delivery requires the engineer to
know which team owns the next step. Yes. The org chart is the API.

## 6. Capabilities that already exist (including human-realized)

The organization can already satisfy these classes of intent. Most are
implicit, ticket-realized, and still capabilities.

- Provide eligible cloud environment
- Provide connectivity
- Provide DNS and certificates
- Establish workload identity
- Provide storage for a known data class (same shape as
  `ProvideRelationalStorage`)
- Assess / attest security for a *standard* workload pattern
- Assess novel security architecture (same shape as
  `AssessNovelSecurityArchitecture`)
- Observe a service
- Establish reliability expectations
- Authorize production change (human-realized, often should stay that way
  for high-risk)

None of these requires an API to *exist*. A DBA with a ticket is still
`ProvideRelationalStorage`. A security architect on a calendar is still
an assessment capability.

## 7. Major capabilities (no maturity score)

Settled / partially settled / novel is a judgment, not a detector.

### Provide eligible environment

- **Intent class:** a subscription/account/namespace the workload is
  allowed to use.
- **Experience:** portal form → ticket.
- **Realization:** landing-zone Terraform, account factory, humans for
  exceptions.
- **Domain authority:** cloud / platform (placement, tenancy); security
  (guardrails); compliance (residency).
- **Capability owner (as practiced):** cloud team (stewardship is
  implicit, not named as capability ownership).
- **Constraints:** residency, isolation, no public by default.
- **Evidence:** time-to-environment, exception volume, abandoned
  requests. Mostly ticket SLA, not path elapsed time.
- **Knowledge:** **settled** for standard product apps; **novel** for
  new tenancy / sovereignty patterns.

### Provide connectivity

- **Intent class:** reachable, segmented connectivity for that
  environment.
- **Experience:** network request form.
- **Realization:** IPAM, NSG, peering, firewall tickets.
- **Authority:** networking.
- **Owner:** network team.
- **Constraints:** zone model, no east-west free-for-all.
- **Evidence:** change failure, reopen rate, "wrong subnet" rework.
- **Knowledge:** **settled** for standard app tiers; **novel** for
  unusual topologies.

### Establish workload identity

- **Intent class:** non-human identity with least privilege.
- **Experience:** identity ticket.
- **Realization:** Entra/AD, roles, maybe workload identity federation.
- **Authority:** identity.
- **Owner:** identity team.
- **Constraints:** no standing secrets where federation is required.
- **Evidence:** over-privileged principals, secret sprawl, repeat
  requests for the same role set.
- **Knowledge:** **partially settled** — pattern exists; applied by
  hand each time.

### ProvideRelationalStorage (or equivalent data service)

- **Intent class:** eligible persistent storage for a stated data class.
- **Experience:** data catalog + tickets to data, network, identity,
  security.
- **Realization:** mixed manual and IaC.
- **Authority:** data (classification), security (encryption, access),
  infrastructure (engine).
- **Owner:** unclear — three queues.
- **Constraints:** encryption, backup, network placement, data class.
- **Evidence:** exceptions for size/engine; incidents from mis-classed
  data.
- **Knowledge:** **settled** for standard relational; **novel** for new
  engines or unclassified data.

### Assess standard vs novel security

- **Intent class (standard):** confirm this app matches a known pattern
  and controls.
- **Intent class (novel):** residual risk explicit enough to decide.
- **Experience:** one intake for both.
- **Realization:** architect review for almost everything.
- **Authority:** security (does not transfer).
- **Owner:** security (calendar is the bottleneck).
- **Constraints:** independent judgment for novel risk; encoded controls
  for settled patterns.
- **Evidence:** volume of "novel" that repeats; findings that are copy-
  paste of last quarter's standard app.
- **Knowledge:** **standard path settled; treated as novel in
  realization.**

### ObserveService / EstablishReliability

- **Intent class:** gold signals, alerting, SLO/on-call expectations.
- **Experience:** "install our stack" plus a meeting.
- **Realization:** agents, dashboards, SRE templates.
- **Authority:** SRE / observability.
- **Owner:** SRE.
- **Constraints:** minimum production telemetry.
- **Evidence:** incidents with no useful signals; teams that skip the
  meeting and still ship.
- **Knowledge:** **settled** for standard HTTP APIs.

### Authorize production

- **Intent class:** independent authorization to go live.
- **Experience:** change ticket / CAB.
- **Realization:** human approval.
- **Authority:** change / SoD — intentionally independent of the
  delivery team.
- **Owner:** governance.
- **Constraints:** four-eyes, evidence of controls.
- **Evidence:** rubber-stamp rate vs. genuine hold.
- **Knowledge:** the *obligation* is settled; whether this *instance*
  needs live judgment is case-by-case.

## 8. Repeated traversal that can be removed without the forbidden moves

Removable **without** stripping domain authority, weakening regulation,
killing SoD, centralizing all execution, or mandating maximum
self-service:

- **Discovering which team owns the next step** (routing).
- **Re-entering the same context** (app name, data class, environment)
  into five intake forms.
- **Security architect re-applying a settled pattern** to the 80th
  similar customer API (value is real; shape is routing).
- **Network + identity + data each rediscovering** that this is a
  standard tier-2 app in a known landing zone.
- **Portal forms that only open tickets** (new experience, same
  realization chain).

Not removable as "waste": independent production authorization; novel
threat-model work; a data-class ruling that has never been made; a
break-glass path with named authority.

## 9. Encode what is repeatable; collaborate on what is novel

Repetition is a **signal to examine**. Security (or any domain) still
decides whether knowledge is settled enough to encode.

**Could be encoded (forms, not a ladder):**

| Form | Concrete in this case |
| --- | --- |
| Documentation | "Standard customer API: landing zone L2, private ingress, workload identity federation, gold signals." |
| Policy | Data class → allowed stores, encryption, residency. |
| Contract | Eligible environment: what you get, what you must not do, who owns exceptions. |
| Template / declaration | App manifest: name, data class, exposure, SLO class. Git PR as experience. |
| Workflow | Standard path: checks run, evidence attached, production authorization still human. |
| Automation | Provision environment + identity + baseline network *when* declaration matches policy. |

**Should remain specialist collaboration:**

- First use of a new data class or sovereignty region.
- Novel architecture (new trust boundary, unusual third party).
- Exception to segmentation or encryption that policy does not cover.
- Genuine independent production hold (not a rubber stamp).
- Incident-driven redesign of a standard path that is now wrong.

## 10. WHAT vs HOW (five capabilities)

| Capability | Consumer depends on today | Possible stable *what* | *How* stays free to evolve |
| --- | --- | --- | --- |
| Environment | Cloud team's account factory process | Eligible environment of class L2 | Swap account factory, hyperscaler, or namespace model |
| Connectivity | Network ticket + chosen subnet | Connectivity that meets zone policy | Change firewall vendor, mesh, or peering design |
| Workload identity | Identity team's Entra request | Workload identity with stated privilege class | Move from client secrets to federation without re-teaching the org |
| Relational storage | DBA + network + identity tickets | Eligible relational persistence for data class PII-lite | Move engine or managed service |
| Standard security attest | Architect calendar | Attestation that the workload matches pattern S1 | Replace checklist review with policy-as-code + sample audit; keep humans for S1-miss |

## 11. Experience vs realization (superficial improvement)

The IDP already offers "Request environment," "Request network," "Request
identity." Each opens the same queue. **Experience changed; realization
and routing did not.** Elapsed time would not move. That is the portal-
as-ticket-router anti-pattern.

A useful experience change is one that binds to a *different
realization*: declaration in Git evaluated against encoded policy, with
tickets only on exception. A form that is still a courier to eight teams
is cosmetics.

AI in the portal that fills the eight forms faster is the same trap:
better experience over the same organizational supply chain.

## 12. Composite capability

**Composite:** `OnboardRoutineCustomerWorkload` (same idea as
`LaunchRegulatedAPI` / `DeployApplication`).

- **Intent it satisfies:** eligible customer-facing workload live under
  known constraints.
- **Composite ownership / coherence:** *not currently named.* Product
  owns the customer outcome; no one owns the seams. This is the
  "unowned composite" condition from the path-accountability analysis:
  locally fine, globally slow. The theory says someone must own the
  composite's coherence and seams **without** owning networking,
  security, or identity. The case does not invent who; it notes the
  gap. Platform is a *candidate* steward, not a required one.
- **Seams that matter:** environment ↔ connectivity (wrong subnet);
  identity ↔ network (can't reach IdP); data class ↔ storage ↔
  security (late conflict); standard-security attest ↔ production
  authorization (duplicate evidence).
- **Independent domain authorities:** security, identity, networking,
  data, compliance, change/SoD. Composition must not expand them.
- **Refuse or exception:** public exposure not in contract; unclassified
  data; novel IdP; production without required signals; any contributor
  constraint that cannot coexist — refuse or route to human judgment.
  Never promise the union.

## 13. Abstract routing, not accountability

**Off the routine execution path:**

- Which Slack channel owns Kubernetes.
- Which ticket queue is SEC-103 vs NET-40.
- The sequence of teams the last person happened to visit.

**Remain discoverable:**

- Who has domain authority for identity, security, network, data.
- Who owns each contributing capability and the composite.
- Provenance of the encoded policy (who last validated it).
- Operational responsibility when the workload breaks.
- Audit trail for production authorization.

Ownership should be findable without being the thing you navigate to get
work done.

## 14. Intentional friction that must remain

- Separation of duties on production authorization.
- Independent security authority to **refuse** an unsafe composition
  even if it would cut weeks.
- Human judgment on novel threat models and uncoded data classes.
- Exception handling with named authority, logging, later review.
- Regulatory evidence that controls actually applied.

Delay from these is not automatically waste. Rubber-stamp CAB that adds
three days and no judgment is friction whose *value* is no longer
intentional even if the *obligation* is.

## 15. Observation / learning

| Signal | Reveals | Should reach |
| --- | --- | --- |
| Elapsed 4–8 weeks while each SLA is green | Local success, system failure | Outcome owner + whoever owns the composite (if named) |
| Same security findings copied across standard APIs | Incorrectly treating settled work as novel | Security domain authority + capability owner |
| Exception path used weekly for "standard SQL" | Encoding too narrow or stale | Data + security + composite owner |
| Abandonment: engineers sidestep portal into chat | Experience is a router; routing still the interface | Capability owners of those forms |
| Late constraint clash (identity vs network) | Seam failure | Composite owner with attribution to contributors |
| Policy that forbids a pattern now required by regulation | Stale encoding | Domain authority, then capability owner |
| Cost of landing-zone tickets vs. one-time encoding | Stewardship investment signal | Planning / whoever funds the composite |

Learning informs; it does not compel. Security can see the copy-paste
reviews and still keep the calendar if incentives reward review count.

## 16. Incentive compatibility (expose, do not solve)

**The trade:** Platform (or cloud) spends a quarter encoding
`OnboardRoutineCustomerWorkload` — declaration, policy checks, stitching
settled identity/network/environment paths, exception routing. During
that quarter their request-completion SLA and backlog get worse. After,
product teams wait less, specialists stop re-deriving S1, security
calendar opens for novel work.

- **Cost bearer:** the stewarding team (capacity, worse local metrics,
  standing maintenance).
- **Benefit:** product teams (latency), specialists (less settled
  repetition), the firm (faster routine delivery).
- **Security variant:** encoding S1 controls reduces review volume
  (hurts a "reviews completed" metric) and improves system latency.

The theory does not allocate budget. It makes the misalignment visible:
locally rational A vs. systemically attractive B. Domain authority may
still refuse B if B weakens an independent obligation. Faster is not
automatically better.

## 17. Plausible improved state (not "build one platform")

Minimum mechanisms, mixed:

1. **Name the composite and its seams** in a short handbook page. Owner
   of coherence is an explicit responsibility (existing specialist
   capacity, not a new department).
2. **One declaration** (Git) for routine cases: app, data class,
   exposure class, SLO class. That is experience.
3. **Encode S1** as policy + checklist + automated guardrails where
   mechanical; **keep** architect collaboration for non-S1.
4. **Environment + identity + baseline connectivity** realized by
   existing IaC, invoked from the declaration when policy matches —
   realization change, not a new product org.
5. **Storage** via `ProvideRelationalStorage`-style contract: one
   request that already includes network and identity constraints.
6. **Observability/reliability** as composed defaults on the standard
   path, not a separate scavenger hunt.
7. **Production authorization** remains human and independent; evidence
   pack is assembled *by the path*, not by the engineer walking GRC.
8. **Exception path** explicit: novel data class, public exposure,
   non-S1 architecture → collaboration, not a hidden Slack hero.

Portal optional. If it stays, it submits the declaration or opens the
exception path — it does not clone eight tickets.

AI optional: an agent may *consume* the same declaration and policies.
It does not replace domain authority.

## 18. Before / after (no fake precision)

| Dimension | Before | After (if composite is owned and settled knowledge encoded) |
| --- | --- | --- |
| Traversal | Engineer walks ~10 org interfaces | Routine: one declaration + independent prod authorization; exceptions: named collaboration |
| Coordination | Dominant | Reduced for settled cases; preserved for novel |
| Cognitive load | Learn the org | Learn the contract and when you're off-contract |
| Intentional friction | Mixed with accidental routing | SoD, novel review, real holds remain |
| Authority clarity | Buried in queues | Discoverable; not used as the API |
| Outcome latency | 4–8 weeks stated | Not quantified here; *shape* of wait changes (exceptions and genuine holds, not discovery) |
| Specialist utilization | Settled work on the calendar | Pressure to move judgment to novel — *if* incentives allow |
| Adaptability | Realization change = re-teach the company | *What* stable; *how* can move |
| Observability | Local SLAs green | Path elapsed time, exception volume, seam attribution become visible |
| Stewardship burden | Hidden in eight queues | Explicit on the composite; **higher and concentrated** — the cost side of §16 |

## 19. Distinctiveness test

**A. Strong Platform Engineering** would recommend: better golden path,
IDP as product, self-service, paved road, reduce cognitive load, treat
developers as customers. Likely more portal, more automation, maybe one
"onboarding" workflow. Risk: portal-as-router; platform as the
definition; "developer satisfaction" as the purpose.

**B. Team Topologies** would add: interaction modes (X-as-a-Service vs
collaboration vs facilitating), cognitive load on the stream-aligned
team, platform as a team type, maybe enabling team for the transition.
Would *not* by itself name capability vs realization vs experience, or
tell you a human security assessment is still a capability. Complementary
on *teams*; thinner on *what the consumer depends on*.

**C. DevOps / SRE** would add: you build it you run it, toil reduction,
error budgets, SLOs, automate the toil, production ownership. Would
attack some handoffs (esp. ops). Would not, by itself, stop security /
network / identity remaining ticket APIs, and can collide with
specialized controls that still must be requested.

**D. What this body of knowledge caused us to notice or design
differently:**

- The IDP and Team Topologies structure **do not contradict** the
  failure; they can coexist with org-as-API.
- Distinguishing **capability / experience / realization** makes the
  portal diagnosis mechanical: new UX, same routing.
- Treating **human security review as a capability** prevents the false
  conclusion "we failed because we didn't automate security."
- **Composite ownership of seams without domain takeover** names the
  missing accountability ("no one owns the traversal") without a
  reorg or a Convergence team.
- **Intentional vs accidental friction** keeps SoD and novel review
  instead of "eliminate all gates."
- **Encode vs collaborate** splits the security calendar into S1 vs
  novel instead of "security is the bottleneck" or "automate all
  reviews."
- **Abstract routing, not accountability** is a design rule Platform
  language often blurs (hide the platform team *and* the authority).
- **Incentive compatibility** predicts why the locally rational platform
  team stays on ticket SLA — a gap Platform/TT/DevOps analyses often
  leave as "get leadership buy-in."

**E. If D is weak:** it is not empty. It is also not a new *mechanism*
unknown to good platform and SRE work. The distinctiveness is a **lens
and a set of distinctions** that stop several failure modes this
scenario already exhibits (portal cosmetics, local SLA theater, treating
all review as waste, unowned path). Without those distinctions, a strong
platform program could still "succeed" on adoption while leaving 4–8
weeks intact.

## 20. Where the theory was useful, obvious, redundant, awkward, thin

| Assessment | Where |
| --- | --- |
| **Genuinely useful** | Experience vs realization on the portal; composite seams vs domain authority; settled-vs-novel on security; org-as-API despite mature tooling; incentive misalignment on encoding the path |
| **Obvious** | "Don't make people file ten tickets" — any staff engineer already feels this; the model *names* it rather than discovering it |
| **Redundant with prior art** | Golden path, paved road, X-as-a-Service, toil reduction, IaC, policy-as-code — the *improved state* uses all of these |
| **Awkward to apply** | Naming a composite owner without slipping into "platform team owns everything"; "capability" as a word in a room that hears IDP catalog |
| **Under-specified** | Who acquires composite stewardship; how to fund B over A; how security *judges* S1 vs novel in practice (corpus: domain authority decides, no method) |
| **Unnecessary** | Full capability graph, formal contracts for every leaf, modeling every cloud primitive |

## Verdict

**B. The theory is useful mainly as a synthesis/checklist of existing
practices.**

**Evidence from the case.** The improved state is something a strong
platform + SRE + security-engineering program could build: declaration,
policy, IaC, exception path, independent prod approval. Team Topologies
already wants X-as-a-Service for settled platform interaction and
collaboration for the rest. Nothing in §17 requires a new kind of
software.

What the body of knowledge **did** was prevent several *wrong* designs
this organization is already running: treating the portal as progress;
optimizing team SLAs; collapsing security into "automate or bottleneck";
leaving the path unowned; calling every gate waste. Those distinctions
are load-bearing in *this* scenario. They are still mostly **reframing
and composition of prior art**, not a different engineering artifact.

It is **not D**: a PE/DevOps/TT/SRE analysis that skipped experience vs
realization, composite seams, and incentive compatibility would likely
recommend more IDP and more automation and could miss why 4–8 weeks
survives. It is **not A**: the case did not force a design that those
communities could not reach. It is **not C** as the primary verdict
because the checklist is *specific enough to change the diagnosis* (the
portal, the security calendar, the unowned composite) even if the
prescription overlaps. B fits: **materially better diagnosis and
guardrails; overlapping therapy.**

If later field use showed teams consistently *only* getting the diagnosis
right after this lens, and not from PE/TT alone, the verdict could move
toward A. This single case does not demonstrate that.

## Recurring language (observations only)

- unowned composite / seams
- portal as ticket router
- settled treated as novel
- local SLA, system latency
- declaration vs eight queues
- S1 vs novel
- cost on the steward, benefit on everyone else
