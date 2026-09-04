# Worked case: security governance under pressure to remove friction

*Non-canonical research note. Applies the existing body of knowledge only.
Does not add theory, principles, roles, or names. Does not edit the
canonical corpus, the frozen essay, or prior research notes.*

**Question under test.** When leadership and product teams want faster
releases, and the attractive proposal is "move security into the platform
and automate approval," does the existing model produce a defensible
design — or does it collapse into either "automate everything" or
"preserve every gate"?

The pressure in this organization is strongly toward *removing* friction.
The doctrine under test is: **remove accidental friction; design
intentional friction.**

## 1. Intent (do not collapse)

Four intents, not one scoreboard.

| Whose intent | What they are trying to cause |
| --- | --- |
| **Customer / product** | A change reaches customers: a claim-status API ships a fix or feature, available, correct enough, trustworthy enough to use. |
| **Engineering (product/platform)** | The change is in production with known operational expectations, without the team assembling eight specialist queues. |
| **Security** | Residual risk for this change is explicit enough to decide; controls that must apply, apply; novel risk is judged, not rubber-stamped. |
| **Regulatory / governance** | Independent evidence that required controls and separation of duties held; the firm can attest, not merely believe. |

**Where they reinforce:** a secure, attested production change *is* the
customer-facing outcome in a regulated firm. Encryption, identity, and
audit are not optional garnish on "go faster."

**Where they legitimately conflict:** delivery latency vs. independent
judgment; product's desire that "pipeline green = done" vs. security's
obligation to refuse an unsafe composition; a compensating control that
is slower but is the only honest residual-risk acceptance. **"Better" is
not "faster."** A security authority may correctly refuse a change that
would cut review time if it would also dissolve independent obligation.

The engineering system is multi-objective. Collapsing these intents into
"reduce security latency" is already a local optimization of the wrong
unit.

## 2. Scope the engineering system

The relevant system is the one through which **a class of production
change** (here: change to a customer-facing regulated workload) becomes
an **accepted production outcome**.

It is not "the product team," "Security," "the platform," or "the
pipeline." Those are contributors and experiences/realizations.

It includes: product implementation, CI/CD and scanning, platform
capabilities, identity and network constraints, security expertise
(encoded and human), compliance evidence, independent authorization
where SoD requires it, production, and evidence that can change what the
system believes.

In corpus terms this is a candidate composite in the same family as
`LaunchRegulatedAPI` / `DeployApplication`, with security contributing
across several leaves rather than appearing only as a stage.

## 3. Current path (representative change)

A product engineer wants to ship a behavior change to the claim-status
API (new field, same trust boundary, same data class).

| Stage | What happens | Shape |
| --- | --- | --- |
| Intent | PR + ticket "need prod" | — |
| Implementation | Code, IaC, pipeline | Automated checks: SAST, dependency scan, some policy-as-code |
| Security interaction | Architecture questionnaire (mostly copy-paste from last release); wait for reviewer assignment (days); meeting if the queue says so; sometimes a threat-model workshop scheduled because the form has a checkbox | Tickets, queue, meeting, human judgment mixed with settled checklist |
| Governance | GRC evidence pack assembled by the engineer; compliance checklist overlapping security's | Duplicated collection |
| Production | CAB / change ticket; four-eyes on prod deploy | Approval, SoD |
| Observation | Scan dashboards, occasional incident; questionnaire answers not fed back into standards | Weak loop |
| Escalation | Release date → manager pings a principal to skip the queue | Exception without evidence design |
| Exception handling | "Approved with conditions" in email; conditions not encoded | Invisible next time |

None of this is *automatically* waste. Assignment wait, copy-paste
questionnaire, and duplicate GRC pack are the first suspects. Independent
prod authorization and a real threat-model on a *new* trust boundary are
not.

## 4. Classify the friction

Delay is not the test. Value to the engineering system is the test.

| Friction | Classification | Why |
| --- | --- | --- |
| Repeated questionnaire for the same pattern | **Accidental** (value real, shape wrong) | The control is "confirm S1 still holds." Re-deriving it from a blank form is duplicated interpretation. |
| Waiting nine days for reviewer assignment | **Accidental** | Independent review can be intentional; *discovery and idle queue* are routing. |
| Separation of duties (deployer ≠ authorizer) | **Intentional** | Organizational separation carries governance value. Removing it for speed would dissolve the obligation. |
| Threat-model workshop for a new IdP / new trust boundary | **Intentional** (collaboration) | Novel; encoding would manufacture false certainty. |
| Threat-model workshop checkbox on every standard API change | **Accidental** | Settled pattern treated as novel in realization. |
| Mandatory independent approval for high-risk prod | **Intentional** | Independent authority, evidence, SoD. |
| Duplicated evidence (security form + GRC pack + CAB) | **Accidental** | Same attestation collected three times. Obligation is real; the courier is the consumer. |
| Manual verification of "TLS 1.2+, disk encrypted" already in policy-as-code | **Accidental** | Settled control; human is the scanner. |
| Exception review for a compensating control | **Intentional / contextual** | Ambiguity, consequence, residual risk acceptance — human. |
| Regulatory signoff on a new interpretation of a rule | **Intentional** | Domain (legal/compliance) authority; not a pipeline concern. |
| Ambiguous policy ("no public exposure" vs. partner webhook) | **Contextual** | Needs interpretation; encoding the *wrong* crisp rule is worse than a slow correct one. |
| Escalation to meet the date | **Accidental** (and dangerous) | Exception path exists as heroics, not as designed break-glass with evidence. |

**Most common finding (design doctrine):** the value is real and the
shape is routing — security review as a calendar API for work the
organization already knows how to decide.

## 5. Expertise vs capability

Security expertise currently consumed *through people* includes:
pattern recognition on threat models, interpretation of ambiguous
policy, residual-risk language for executives, exception judgment,
knowing which scan findings matter.

That expertise is not the same as the organization's **capability**.

Implicit capabilities already exist, including when realized by humans:

- **AttestStandardWorkloadControls** — "this change matches pattern S1
  and encoded controls hold." Often realized as an architect reading a
  questionnaire.
- **AssessNovelSecurityArchitecture** — residual risk explicit enough to
  decide. Human-realized; still a capability (corpus worked example).
- **InterpretPolicyException** — compensating control, named acceptance.
- **AuthorizeProductionChange** — independent SoD authorization (may sit
  with change/governance, not "the security team" as a queue).
- **VerifyEncodedControl** — scanning / policy-as-code already *is* this
  capability with a software realization.

Capability ≠ automation. The architect on a calendar is still
`AssessNovelSecurityArchitecture`. The failure is using that realization
for S1.

## 6. Settled vs novel (hostile to simplistic bins)

Repetition is **evidence to examine**, not proof to encode. Security
domain authority decides whether knowledge is representable and safe to
hand to an encoding. A case can become novel again when evidence,
regulation, or assumptions move.

| Work | Tentative reading | Why not a machine label |
| --- | --- | --- |
| Approved encryption configuration | **Settled enough to encode** (already partly in policy-as-code) | Still challengeable if a cipher is broken. |
| Network exposure policy (no public by default) | **Settled** for standard apps | Partner webhook is **contextual** — same words, different risk. |
| Workload identity requirements | **Partially settled** | Pattern exists; applied by ticket. |
| Dependency scanning | **Settled** as a check; **contextual** as "ship with this CVE" | Scan is encodeable; accept-risk is judgment. |
| Standard data-class handling | **Settled** for known classes | New class or new residency rule → novel/interpretive. |
| Novel authentication architecture | **Novel** | Collaboration. |
| Unusual trust boundary | **Novel** | Collaboration. |
| New threat class (e.g. novel supply-chain technique) | **Previously settled, invalidated** | Encoding must be challengeable; living expertise reconnects. |
| Regulatory interpretation | **Inherently contextual / authority-bound** | Not a good candidate for "the platform approved it." |
| Compensating control | **Contextual** | Exception path. |
| Exception to established policy | **Contextual** | Must not be the silent normal. |

If leadership treats "we have seen this questionnaire 40 times" as proof
to automate *approval*, they skip the examination: maybe 38 were S1 and
2 were the new threat class wearing the old form.

## 7. What could be encoded (forms, not a ladder)

| Form | Plausible use here |
| --- | --- |
| Documentation / standards | S1 customer API: controls, evidence expected, when you are off-contract. |
| Decision table | Data class × exposure → required controls; "if none match → exception." |
| Reusable architecture pattern | Private ingress + workload identity + gold signals. |
| Policy / policy-as-code | Encryption, no 0.0.0.0/0, required labels. |
| Contract | What `AttestStandardWorkloadControls` promises and refuses. |
| Templates / IaC modules | Landing zone + identity that already satisfy S1. |
| Pipeline checks | Mechanical verification; fail closed on S1 requirements. |
| Evidence generation | Pipeline emits the pack GRC/CAB currently make humans assemble. |
| Automated verification | Repeat of settled controls — not residual-risk acceptance. |

Software is not automatically the best encoding. A one-page standard
that architects and pipelines both use can beat a brittle policy engine
nobody can challenge.

## 8. What must remain human — and why the theory can refuse automation

The theory's reasons **not** to automate are already in the doctrine:
judgment, independent authority, novelty, uncertainty, consequence,
challengeability. Encoding a guess gives it the authority of a system.
Abstraction must not manufacture false certainty.

Remain human (or human-authorized):

- **Novelty:** new IdP, new data flow to a third country, new threat
  class.
- **Ambiguity:** policy that does not decide the case.
- **Consequence:** accept residual risk on a customer-data path.
- **Uncertainty:** scan is green, threat intel says the pattern is now
  wrong — living expertise.
- **Regulatory / legal authority:** interpretation and attestation
  obligations that must stay independent of the delivery team.
- **Exceptions:** compensating controls; break-glass with named
  authority and later review.
- **Conflicting constraints:** security vs. availability vs. a
  regulator — composition may refuse or route; it may not average.

This is a defensible "do not automate": not nostalgia, and not "security
is special so never encode." It is: **do not encode what is not settled
enough, and do not let execution of an encoding impersonate domain
authority.**

## 9. Experience vs realization — "put security in the platform"

Three meanings of the same slogan:

**A. Portal / form that still routes everything to Security.**  
New experience, same realization (architect queue). Portal-as-ticket-
router. Review SLA might even worsen (another system). Elapsed time
unchanged. Looks like "platform." Is not encoding.

**B. Encoded security expertise consumed through capabilities the
platform (or Git, or pipeline) realizes.**  
Experience: declaration, PR, pipeline. Realization: policy-as-code, IaC
modules, evidence pack, *plus* exception path to humans. Security
**domain authority** still owns what "correct" means; they do not
personally execute every check. This is the only reading compatible with
the model.

**C. Pipeline green = universal security approval.**  
Experience (checks) collapsed into authority. Execution impersonates
authority. Independent obligation evaporates. Fast, auditable-looking,
and wrong. This is invocation-as-authority on a firm-wide scale.

Leadership's proposal is ambiguous among A, B, and C. Product's
interpretation ("if the pipeline passes, Security shouldn't be
involved") is **C**. Security's pushback is partly against C, and will
be misread as against B unless the distinctions are explicit.

## 10. Authority (implementation location must not redefine it)

| Role | In this case |
| --- | --- |
| **Domain authority** | Security (and legal/compliance where the obligation is theirs) determines what correct means for controls, residual risk language, and what S1 includes. |
| **Capability ownership** | Stewardship of `AttestStandardWorkloadControls`, `AssessNovelSecurityArchitecture`, encoded policies — fitness, decay, evolution. May be security, or security + platform as realization partners. Ownership is not a security *boundary*. |
| **Execution** | Pipeline, platform, product engineer, or AI agent *performs* checks and deploys. |
| **Outcome ownership** | Product owns the customer-facing result; they do not own "what secure means." |

**Authority does not imply execution.** Security can own the standard
without clicking every pipeline.

**Execution does not imply authority.** If the platform executes an
encoded control, Security retains domain authority: they can change the
encoding, refuse compositions that don't meet it, and require human
paths for off-contract work. The platform has not been granted the right
to redefine the control.

**Product invoking the capability** gets privilege to *use* the settled
path, not authority to waive S1 or to accept residual risk on novel
work.

**An AI agent invoking it** gets whatever privilege it was granted —
not domain authority, not the right to grant itself exceptions, not
"the model thought it was fine." Invoking a capability does not expand
authority (Principle 5; invocation-as-authority anti-pattern).

## 11. Separation of duties

SoD is a first-class intentional boundary: **organizational separation
itself carries governance value.**

Compatible with the model:

- **Distributed execution, independent approval.** Product/platform/AI
  *executes* deploy when encoded checks pass *and* an independent
  authorizer (change authority, not the committer) still attests for
  production classes that require it. The authorizer's experience can be
  a short evidence pack the path produced — not a nine-day assignment
  queue.
- **Security encodes S1; does not approve its own product's exception.**
  Exception to policy is a different capability, different authority
  path.
- **Scanner in the pipeline is execution.** Accepting a critical CVE
  ship is not something the pipeline is allowed to "decide" unless a
  named authority records residual risk.

When separation does **not** need to be the delivery API: routing every
S1 change through the security team's calendar *because they sit in
another org box*, even though the independent obligation is already
satisfied by encoded verification + a change authority that is not the
author.

Principle 3: organizational structure participates where separation
carries engineering or governance value — SoD, independent security
refusal — and should not be the interface for "which queue for TLS."

## 12. Composition

**Composite:** `ShipRegulatedProductionChange` (or reuse
`LaunchRegulatedAPI` for first onboard; here the recurring class is
*change*).

- **Intent:** change accepted in production under applicable controls
  and independent obligations.
- **Contributors:** implement/build, verify encoded controls, attest S1
  or assess novel architecture, identity/network/data constraints,
  observe, authorize production.
- **Coherence / seams:** S1 attest vs. actual IaC (drift); scan pass vs.
  accepted CVE; evidence pack vs. what CAB thinks it needs; exception
  recorded vs. next change assuming S1.
- **Independent authorities:** security, compliance/legal, change/SoD
  — **do not transfer** to the composite owner (often platform or a
  named steward of the path).
- **Constraints coexist:** composite inherits the strictest applicable
  restriction; does not average "security said no, product said ship."
- **Refuse:** public exposure off-contract; unclassified data; novel
  trust boundary without assessment; deploy without required evidence.
- **Exception route:** compensating control, residual-risk acceptance —
  human, named, logged, reviewable.

**The whole can be accountable for its composition without owning the
parts.** Platform (if it owns the composite) owns seams and "did we
promise more than contributors allow." It does not acquire security
domain authority.

If nobody owns the composite, local review SLAs can go green while the
path is still a questionnaire plus a CAB that does not know what S1
means this quarter.

## 13. Failure: automate too much (local success, system failure)

Leadership gets what it asked: **security review latency collapses.**
Questionnaire gone. Pipeline is the approval.

What actually happened: **C**, plus stale S1.

- Contextual judgment disappeared: partner webhook classified as S1
  because the form is gone and the check is "has encryption."
- Exceptions became invisible: engineers force-green or use a shared
  override token; no named residual-risk record.
- Encoded assumptions went stale: a new attack technique lands; the
  pattern is still "approved"; no living review of S1.
- Authority confused: auditors ask who accepted residual risk; "the
  pipeline" is not an authority.
- Passing a check mistaken for being secure: coverage metrics 95%;
  incident is an off-contract data flow nobody assessed.

**Wrong success:** review SLA, deployment frequency, automated-control
coverage all up. The engineering system converted intent to outcome
*faster* and *less correctly*. Observation that only watches latency
congratulates the failure.

## 14. Failure: automate too little

Security keeps human review for settled, repetitive S1 (TLS, disk
encrypt, standard identity).

- Specialists spend the year re-applying known rules.
- Product waits; dates drive escalation; heroics become the real
  exception path.
- Novel work (new threat class, new architecture) gets the leftover
  calendar — the opposite of "make exceptional work exceptional again."
- Governance *is* calendar latency; independent judgment is diluted by
  boredom and queue pressure (rubber stamps that look like SoD).

The theory does **not** advocate preserving every existing boundary.
It advocates examining repetition, encoding what is settled *with
authority still able to challenge it*, and spending humans on novel,
ambiguous, and high-consequence work. Keeping the calendar for S1 is
not "preserving security"; it is a bad realization of a real capability.

## 15. Intentional friction vs. accidental delay around it

| Keep (value) | Strip if it is only surrounding delay |
| --- | --- |
| Independent approval for high-risk prod (SoD, evidence) | Nine-day reviewer assignment; "find the right security team" |
| High-consequence exception review (named residual risk) | Blank questionnaire that hides the exception in a comment field |
| Novel threat-model judgment | Mandatory workshop on every field-add to an S1 API |
| Regulatory interpretation | Product engineer as courier between Legal and Security with two packs |
| Explicit acceptance of residual risk | Email "LGTM" with no provenance |

Independent approval may be intentional. Waiting nine days for
assignment is not. Design the former; remove the latter.

## 16. Abstract routing, not accountability

**Improved routine path:** product engineer does not need "which
security team handles S1." They declare the change class, the path
applies encoded controls, evidence is produced, independent prod
authorization consumes that evidence.

**Still discoverable:**

- Who owns `AttestStandardWorkloadControls` and the encoded S1 policy.
- Who holds security domain authority (and that they can refuse).
- Why a control exists (link to obligation / threat, not tribal lore).
- What evidence this change produced.
- How to challenge the encoding (not "open a ticket to skip").
- How to request an exception (designed path).
- Who made a high-consequence decision (named, not "the platform").

Routing abstracted; provenance and authority not opacity.

## 17. Learning: encoding becomes wrong

**Event:** a newly practical attack technique invalidates the approved
S1 ingress pattern (e.g. a class of token replay the pattern assumed
away).

| Step | What the model says |
| --- | --- |
| Evidence | Incident, threat intel, research — may originate *outside* the loop. |
| Learning | Evidence capable of changing what the system believes; does not auto-mandate. |
| Domain judgment | Security authority decides S1 is no longer settled. |
| Changed encoding | Pattern deprecated; policy tightened; pipeline checks updated; docs say S1-old is off-contract. |
| Affected capabilities / composites | `AttestStandardWorkloadControls`, `ShipRegulatedProductionChange` — contracts narrow or refuse until consumers migrate. |
| Consumer experience | Standard path now fails or routes to `AssessNovelSecurityArchitecture` / exception; engineers are told *why*, not only "denied." |

Encoded expertise remains **challengeable**. Encoded expertise without
living expertise becomes legacy — here, a fast path that is a known-bad
pattern. Specialists' job after encoding is not to vanish; it is to tend
and invalidate.

## 18. AI stress test (not the thesis)

An agent requests infrastructure, identity, network exposure, and
production deploy via the same capabilities.

**What changes:** scale and speed of *execution*; the org-navigation tax
becomes incompressible (the agent will not learn Slack). Machine
consumability increases **productive** leverage (settled path, every
time) and **adversarial** leverage (a privileged agent is a high-rate
executor of whatever the encodings allow — including stale S1 and
unlogged overrides).

**What does not change:** domain authority, SoD, residual-risk
acceptance, the need for exception as a designed path. Privilege ≠
authority.

**"The more execution is delegated, the more explicit uncertainty,
consequence, authority, and recovery must become."** Agent-driven
deploys make C catastrophic: green checks at machine speed with no
named authority. They also make B more valuable: the same contracts
humans use, with explicit refuse/exception. AI does not create the need
for the model; it raises the cost of A and C.

## 19. Incentives (observable, unsolved)

**Security bears cost, others capture benefit:** engineers spend a
quarter writing S1 policy, decision tables, evidence emission, exception
workflow. Review-count and "engagement" metrics fall. Product and
platform get latency and fewer questionnaires. Security looks locally
worse on the dashboard that funded them.

**Product bears cost, security/risk capture benefit:** a team delays a
release to refactor onto workload identity and private ingress, or
accepts slower delivery for a compensating control. Feature output dips;
residual risk and audit posture improve. Product's OKR does not pay that
bill.

The theory does not fund either trade. It makes them visible as
locally-worse / systemically-better (or systemically-*required*)
questions, with security still able to refuse a "faster" encoding that
is actually C.

## 20. Plausible improved state (minimum mechanisms)

Not "build a security platform" as the definition.

1. **Split the capability:** S1 attest vs. novel assessment vs.
   exception — different experiences, same domain authority.
2. **Handbook + decision table** for S1 and "you are off-contract if…"
3. **Git declaration / PR** as routine experience; pipeline +
   policy-as-code + IaC modules as realization for mechanical controls.
4. **Evidence pack emitted by the path** for GRC/CAB — one collection.
5. **Independent production authorization** remains; consumes the pack;
   assignment queue designed down (staffing/experience), not deleted as
   an obligation.
6. **Exception / residual-risk path** with named authority, logging,
   later review — replaces date-driven Slack heroics.
7. **Living review of S1** as an operating concern (threat intel,
   incidents) — not a one-time encoding project.
8. **Portal optional.** If present, it starts S1 or opens exception; it
   does not clone the architect queue.

AI may consume the same contracts. It does not approve exceptions.

## 21. Before vs after (no fake numbers)

| Dimension | Before | After (B, not C) |
| --- | --- | --- |
| Delivery latency | Dominated by queue + copy-paste + duplicate packs | Routine: checks + independent auth; novel/exception: still slow *on purpose* |
| Accidental coordination | Questionnaire, assignment hunt, three evidence packs | Reduced |
| Intentional collaboration | Diluted across every change | Concentrated on novel, exception, interpretation |
| Specialist utilization | Settled rules on the calendar | Pressure toward novel — *if* incentives allow encoding |
| Authority clarity | "Security is the queue" | Authority discoverable; execution distributed |
| Security judgment | Starved and/or rubber-stamped | Available for work that needs it |
| SoD | Present as CAB theater + delay | Present as independent auth on evidence |
| Cognitive load | Learn which team and which form | Learn contract and off-contract path |
| Observability | Review SLA, scan dashboards | Exception volume, S1 invalidation events, path elapsed time, seam drift |
| Exception visibility | Email / Slack | Designed path or it didn't happen |
| Adaptability | Changing a rule means retraining reviewers | Encoding change + communication; consumers depend on *what* |
| Stewardship burden | Hidden in the queue | Explicit on encodings + composite seams |

## 22. Distinctiveness (hostile)

**A. DevSecOps** would say: shift left, automate in CI, security as
code, everyone is responsible for security, don't bolt on at the end.
Would push scanning, policy-as-code, pipeline gates. **Risk:** "everyone
responsible" blurs authority; pipeline green = done (this case's C);
under-specifies SoD and independent refusal.

**B. Strong Platform Engineering** would say: golden path with
guardrails, paved road, reduce cognitive load, security capabilities on
the IDP. **Risk:** A (portal) or C (platform *is* approval); developer
as customer over regulatory obligation.

**C. Team Topologies** would say: complicated-subsystem or platform
interaction; X-as-a-Service for standard security; collaboration for
novel; don't make stream-aligned teams wait on a ticket if XaaS is the
mode. **Useful on interaction mode.** Thinner on encoding vs authority
vs SoD, and on "check execution ≠ authority."

**D. SRE** would say: error budgets, toil, reliability as engineering;
maybe "security toil" analog. **Useful** on not spending experts on
repetition. **Does not** by itself preserve independent security
obligation against delivery pressure.

**E. Zero Trust / policy-as-code** would say: never trust the network,
explicit policy, continuous verification, PEP/PDP. **Strong overlap**
with encoding settled controls and mechanical verification. **Does not**
by itself tell you when a PDP decision is the wrong layer for residual
risk, or that a human assessment is still a capability.

**F. What this body of knowledge caused us to notice or preserve
differently:**

- The slogan "put security in the platform" **must be disambiguated**
  (A/B/C). That disambiguation is the experience/realization +
  authority/execution split. DevSecOps and PE can reach B, but they
  often *ship A or C* under B's name.
- **Intentional vs accidental friction** is the tool that resists the
  org's pressure to delete SoD and novel judgment *because they are
  slow*.
- **Settled vs novel as examination, not a detector** blocks "40
  questionnaires ⇒ automate approval."
- **Composite refuses / does not override** security — "globally faster"
  is not a license.
- **Invocation ≠ authority** (human, platform, or agent).
- **Learning / challengeable encoding** against the success story of
  frozen S1.
- **Wrong-success metrics** (next section) as first-class.

Would mature DevSecOps + policy-as-code + PE + TT **reach the same
design if done well?** Often **yes on mechanisms** (policy, pipelines,
exception CAB, threat modeling for novel). The distinctiveness is
**stronger on diagnosis and refusal** under political pressure to
flatten security into the pipeline. That is a real difference in *this*
case; it is still mostly guardrails on prior-art mechanisms, not a new
control plane.

## 23. Wrong success (five metrics)

| Metric that can improve | System failure it can hide |
| --- | --- |
| **Review SLA / time-to-approve** | Approvals became rubber stamps or pipeline-as-authority (C); judgment gone. |
| **Deployment frequency** | Faster shipment of off-contract risk; exceptions invisible. |
| **Portal adoption** | Experience A; same architect queue; credibility burn. |
| **Automated-control coverage %** | Coverage of *settled checks*; novel paths and stale S1 unmeasured; "95% secure." |
| **Ticket volume** | Work moved to Slack/overrides; exception path unofficial; SoD theater. |

**Better evidence of intent-to-outcome (signals, not a score):** elapsed
time *including* informal channels; exception volume and whether they
are named residual-risk records; rate of S1 invalidation / encoding
changes from intel and incidents; independent-authority refusals (not
treated as defects); incidents and near-misses attributed to
composition seams vs. missing novelty review; whether novel work still
gets specialist time; audit findings on "who accepted this risk."

Judge conversion of intent to outcome **while preserving** expertise,
authority, judgment, accountability, constraints, and learning — not
review latency alone.

## 24. Theory utility

| Assessment | Where |
| --- | --- |
| **Genuinely useful** | A vs B vs C on "platformize security"; SoD as intentional organizational participation; execution ≠ authority for pipelines and agents; accidental delay around independent approval |
| **Protective against a bad design** | C as the leadership-attractive failure; "automate too little" as the security-attractive failure; both named without a new principle |
| **Redundant with prior art** | Policy-as-code, shift-left scanning, threat modeling, compensating controls, four-eyes — the improved state *is* those, arranged |
| **Awkward** | Saying "capability" in a GRC conversation; composite owner who is not "Head of Security" and not "override Security" |
| **Under-specified** | How security *judges* S1 vs novel in practice; who funds the encoding quarter; how independent CAB actually consumes an evidence pack (org design) |
| **Unnecessary** | Full enterprise capability graph before splitting S1 from novel |

## Verdict

**B. The theory provides meaningful guardrails and system-level
reasoning but mostly composes mechanisms available in existing
practices.**

**Evidence.** The pressure case is where the doctrine is *most* load-
bearing: the org wants friction gone; the wrong completions are A and C;
the wrong preservation is "never encode." Distinctions (experience vs
realization, authority vs execution, accidental vs intentional,
settled-as-examination, composite cannot override security, challengeable
encoding, wrong-success metrics) **change the diagnosis of the proposal**
and **justify refusing C** without refusing encoding.

The **therapy** is still DevSecOps/policy-as-code/PE/TT/SRE mechanisms
plus an independent approval path. A superb DevSecOps program already
aims at B. This body of knowledge is not required to *invent* that
program. It is useful to **keep that program from becoming A or C under
executive latency pressure**, and to **keep Security from defending
every queue as if it were SoD.**

Not **A**: no new security engineering artifact appeared that those
communities lack. Not **C** as primary: in this scenario the checklist
is not generic "be more systemic" — it specifically blocks the slogan's
dangerous reading. Not **D**: DevSecOps-as-slogan plus IDP commonly
*is* A or C; the case shows why.

Lower than A is the honest result: **guardrails and composition, not a
distinct implementation layer.** That is useful evidence, not a failure
of the exercise.

## Recurring language (observations only)

- accidental delay around intentional approval
- pipeline green = authority (C)
- S1 vs novel vs exception
- execution is not authority
- named residual risk
- challengeable encoding
- wrong-success SLA
