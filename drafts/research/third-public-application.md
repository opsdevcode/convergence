# Third public application of the initial method

*GitHub October 21, 2018 incident. Method unchanged. Not proof of
Convergence. Not employer-specific. Not a fourth-case prelude.*

**Case type:** single organization, first-party post-incident analysis of
**one production incident**.

**Trace evidence classification: A — actual instance trace** (this
incident’s timeline). Not three recurring flows; not an architecture
diagram. Sequence, times, and decisions are first-party.

---

## Intent / outcome

- **Affected party:** GitHub.com users and ecosystem partners (webhooks,
  Pages). GitHub as operator of the platform.
- **Class of intent:** keep **GitHub metadata services** (issues, PRs,
  auth, background jobs, webhooks, Pages — not raw Git object storage)
  in an acceptable operating state: **available, reasonably consistent,
  and data-integrity-preserving** when a short **internal network
  partition** occurs.
- **Outcome that counts:** customers can use the platform without
  stale/inconsistent metadata; no silent data loss; recovery does not
  invent writes.
- **Why this method applies:** multiple systems (network, Orchestrator,
  MySQL clusters, application tier, backups, webhooks/Pages) contributed;
  **local success ≠ end-to-end success**; documented corrective work.
- **Who owns this analysis:** this research pass.

**Boundary.** This incident class: partition → automated cross-region
MySQL primary promotion → split-brain-ish write sets → degraded GitHub
metadata path. Not GitHub’s entire SRE program.

**Exclusions.** Git protocol/object storage internals (except as
unaffected); later GitHub outages; Orchestrator as a general product
tutorial.

---

## Why this case (evidence quality)

Selected for a **timestamped first-party sequence**, explicit
Orchestrator-vs-application mismatch, composition failure, and
named follow-ups. Not selected for brand.

---

## Primary source

GitHub Engineering, “October 21 post-incident analysis” (2018-10-30,
updated 2021-12-19).
<https://github.blog/news-insights/company-news/oct21-post-incident-analysis/>

Secondary: none required for the trace. Orchestrator OSS docs are
**not** used as evidence of what GitHub configured that day.

---

## Current trace (the incident)

**Instance:** 2018-10-21 22:52 UTC through 2018-10-22 23:03 UTC.
**[documented]**

| Time (UTC) | What changed | Dependences | Information | Human judgment | Routing | Dependency type |
| --- | --- | --- | --- | --- | --- | --- |
| 22:52 | 43s loss of connectivity East hub ↔ primary East DC during optical maintenance | Physical/logical network | Maintenance in progress | Ops performing planned work | N/A | **Technical** |
| 22:52 | Orchestrator Raft: East-primary Orchestrator deselected; West + East-cloud Orchestrator quorum; **failover writes to West**; West topologies organized | Orchestrator config + Raft | Partition looks like master failure | **Encoded** auto-failover | None | **Technical** + encoded control |
| After restore | App tier **immediately** writes to new West primaries | App uses Orchestrator/discovery | Topology now West | None at this step | None | **Technical** |
| Same window | East DBs hold **seconds of writes** not on West (cross-continent lag) | Replication lag | Not yet a customer narrative | — | — | **Technical** |
| 22:54 | Internal monitoring: numerous faults | Alerts | High volume | Triage | On-call | **Informational** + **capacity** (alert flood) |
| 23:02 | First responders: topologies unexpected; Orchestrator API shows **West-only** replica set | Orchestrator API | Topology ≠ expected East primary | Yes | IR | **Informational** |
| 23:07–23:11 | Lock deploy tooling; status **yellow**; auto-escalate; coordinator joins | Status + IR process | Site impact | Yes | **Intentional** IR | **Governance** (change freeze) |
| 23:13 | Status **red**; DB engineering paged; cannot safely fail back (West has ~40 min of new writes; East has unreplicated seconds) | Data integrity policy | Both sites have unique writes | **Yes — integrity over shorter TTR** | Page DB team | **Governance** + **technical** |
| 23:19 | Pause webhook delivery and Pages builds (jobs that write metadata) | Integrity vs usability | Jobs would worsen inconsistency | Yes | IR decision | **Intentional constraint** |
| 00:05 Oct 22 | Plan: restore from backups, sync, stable topology, then queue | Backup in remote blob store | Restore duration **known from daily tests**; never needed **full cluster** rebuild | Yes | — | **Technical** + **capacity** (transfer hours) |
| 00:41 | Backups started; parallel work to speed transfer | Remote storage throughput | Progress telemetry | Yes | Multi-team | **Technical** |
| 06:51 | Some East clusters restored, replicating from West; cross-country write latency; ETA **linear** interpolation ~2h | Replication telemetry | Incomplete | Yes (estimate) | Public status | **Informational** |
| 07:46 | Public blog delayed because **Pages builds paused** (they use Pages internally) | Pages | Communication blocked by own mitigation | Yes | — | **Composition** of comms + Pages |
| 11:12 | Primaries back East; site more responsive; **dozens of read replicas hours behind** → inconsistent reads; catch-up is **power decay**, not linear; EU/US morning write load | Read replica pool | Users see mixed freshness | — | — | **Technical** |
| 13:15 | Peak traffic; lag **increasing**; provision extra East-cloud read replicas to drain load | Capacity | Replication not catching up | Yes | — | **Capacity** |
| 16:24 | Replicas in sync; fail back to original topology; **stay red** while processing backlog | Integrity | Backlog remains | Yes | — | **Intentional** (status vs “fast green”) |
| 16:45 | Re-enable hooks/Pages; 5M+ hooks, 80k Pages; ~200k webhooks **dropped** (internal TTL); pause; raise TTL | TTL encoding | Silent drop | Yes | — | Encoded knowledge **wrong under backlog** |
| 23:03 | Backlog processed; status green | — | Confirmed | Yes | — | — |

**Unknown:** exact Orchestrator settings before the change; names of
clusters; content of the 954 unreplicated writes on the busiest cluster
(count is documented; reconciliation still in progress at publish time).

**Not waste:** investigation, paging DB engineering, integrity hold,
status red during backlog drain.

---

## Meaningful waits / dependencies and WHY

| Wait | Why |
| --- | --- |
| 43s partition | Technical (maintenance) |
| Orchestrator failover | Encoded response to apparent master failure — **worked as configured** |
| Cannot fail back | Technical + **intentional** data integrity |
| Hours of restore | Technical + capacity (off-site backups); tested daily but not at “all clusters” scale |
| Cross-country writes | Application **cannot** meet latency with West primary + East apps |
| Read replica lag | Technical; load vs catch-up |
| Webhook TTL drops | Encoded TTL vs novel backlog size |
| Public ETA miss | Informational / incomplete model (linear vs power decay + diurnal load) |

---

## Diagnostics used

**Always**

- Intent/outcome: metadata path available, consistent enough, integrity
  first.
- Waits/WHY: above.
- Accidental vs intentional: 43s partition accidental relative to
  customer intent; integrity hold and webhook pause **intentional**;
  Orchestrator cross-region promote was **configured** but **emergent**
  relative to app expectations (“hadn’t previously seen a partition of
  this magnitude”).
- **Experience vs realization:** **used, moderate value.** Status
  yellow/red/green and public ETAs = **experience** of the incident.
  Orchestrator topology, replication, backups = **realization**. Status
  could not show “Pages/webhooks down, Git maybe OK.” That **did**
  change a follow-up (richer status). Operator alerts vs customer
  inconsistency is a similar cut. Not the main diagnosis (composition
  is).
- Wrong-success: below.

**Conditional**

- **Composition: A — central.** Network recovered; Orchestrator produced
  a valid-to-itself topology; app wrote where discovery pointed; MySQL
  clusters locally accepted writes. **Composed customer intent failed**
  (latency, inconsistency, paused jobs). “The whole can be accountable
  for its composition without owning the parts”: app, DB, network,
  Orchestrator need not merge teams; the **composite promise** (HA
  failover that apps can actually serve) was misaligned.
- **Encode vs novel:** auto-failover of in-region leaders = encode
  candidate; this partition + split write sets = **novel** relative to
  prior tests. Daily backup restore encoded; **full multi-cluster
  rebuild from blob** was not the practiced path. Webhook TTL encoded
  and **wrong** under backlog.
- **Capability (light):** `FailOverMysqlMetadataPrimary` existed
  (Orchestrator). It did not equal “GitHub metadata remains customer-
  usable.”
- **Authority vs execution:** Orchestrator **executed** promotion; it
  did not hold authority to redefine the application’s latency/integrity
  contract. Humans later **authorized** fail-forward and integrity
  over TTR.
- **Organizational independence:** N/A as a consumer-of-capability
  portal issue. Unused.

**Unused:** federation.

---

## Reliability / learning test

| Idea | Helped? | vs SRE |
| --- | --- | --- |
| Local ≠ system success | **Yes** — Orchestrator/network/app each “did their job” | Restates SRE; **join** is naming the composite contract |
| Observe seams | **Yes** — topology vs app latency; read replica lag vs primary OK | SRE SLO on **customer path**, not component green |
| Encoded knowledge can go wrong | **Yes** — TTL; linear ETA; Orchestrator config vs app | Same as “models vs reality” |
| Learning can change beliefs | **Yes** — they list config, status, chaos, N+1 | SRE postmortem |
| Learning ≠ action | **UNKNOWN** beyond published “will / accelerated” | Cannot audit GitHub’s later delivery |
| Novel investigation stays collaborative | **Yes** — IR + DB engineering; not automate diagnosis | SRE |
| Repetition ≠ encode | **Yes** — daily backup test ≠ this restore | SRE |

Convergence **restates mature SRE** on most points. Added cut: treat
Orchestrator HA and application serving as **experience/realization and
composition**, not “failover worked / didn’t.”

---

## Documented historical intervention

1. Configure Orchestrator to **prevent promoting primaries across
   regions** (in-region election generally safe; sudden cross-country
   latency was the mismatch).
2. Richer status (components, not only green/yellow/red).
3. Accelerate multi-DC active/active (N+1 facility).
4. More proactive testing of assumptions; chaos/fault injection.
5. Analyze unreplicated binlogs; reconcile writes (some already
   user-retried).
6. Organizational: “tighter ops / faster response insufficient”; validate
   failure scenarios before they hit customers.

---

## Convergence-derived intervention

Given pre-fix evidence only: **smallest** change is align the **encoded
failover realization** with the **composite** application contract
(do not promote a primary the app cannot serve; observe topology vs
latency/consistency). Keep **human** integrity decisions. Encode
“no cross-region primary” **if** that rule is settled. Do **not**
default to more failover automation. Do not invent a path owner.
Observation of the seam (Orchestrator API vs app SLI) before the next
partition. Communication experience (status) is **secondary** to the
composite contract but documented as a real customer harm.

**Do nothing** is unjustified: they said the system behaved as
configured and still failed customers.

---

## Comparison

**Materially similar** to GitHub’s technical item (1) and testing
(4). Status (2) is experience. N+1 (3) is larger than “smallest.”
Competent SRE + HA review produces the same Orchestrator constraint
without Convergence. Convergence’s extra is insisting the **join**
(Orchestrator success vs app/customer outcome) is the unit, not
blaming the 43s network or the DB team.

---

## Documented outcomes

- 24h 11m degraded service; no user data lost; some seconds of writes
  still being reconciled at publish.
- Webhooks/Pages down for most of the window.
- ~200k webhooks dropped on TTL then paused.
- Public repair estimates were wrong.

No claim these “prove” a method.

---

## Prospective observations (if this were a live Convergence pass)

- Cross-region promote actually disabled in Orchestrator.
- Customer-path SLI (write latency, read freshness) vs Orchestrator
  “healthy.”
- Backup restore **at incident scale**, not only daily subset.
- Webhook TTL vs backlog.
- Chaos tests that include **internal partition**, not only node death.
- Whether N+1 shipped — **UNKNOWN** from this post.

---

## Wrong-success

**What could look like success while the engineering system did not
actually improve?**

1. **Orchestrator reports a valid topology** while East apps cannot
   serve West primaries (this incident).
2. **Network “restored in 43 seconds”** treated as incident over.
3. **Primaries back in East** while read replicas are hours behind
   (inconsistent UX; they stayed degraded).
4. **Status yellow/red** as if the whole site were down, or a later
   **green** while webhooks/Pages still paused / backlog draining.
5. **Alert silence** after locking deploys, while customer path still
   wrong.
6. **Webhook processing “done”** after TTL dropped 200k events.

---

## Method observation

| # | Question | Verdict |
| --- | --- | --- |
| 1 Scope bound? | **A** | Metadata + this partition class, not all SRE |
| 2 Trace grade | **A** | Timestamped instance |
| 3 Trace change reasoning? | **A** | 43s ≠ customer impact duration |
| 4 Diagnose? | **A** | Composition |
| 5 Composition? | **A** | Primary value |
| 6 Exp vs realization | **B** | Status vs internals; not the core |
| 7 Authority vs execution | **B** | Orchestrator executed; humans owned integrity |
| 8 Encode vs novel | **B** | TTL, failover rule, untested full restore |
| 9 Intervene useful? | **B** | Same as SRE HA alignment |
| 10 Wrong-success | **A** | Topology green / 43s restore / replica lag |
| 11 Collaborative investigation | **A** | Not “automate the novel diagnosis” |
| 12 Formalize too much? | **C** | Did not push a capability catalog |
| 13 SRE already? | Most of it | |
| 14 Joins | **B** | Composite contract vs component HA |
| 15 Abstraction cost | **A** | Low; composition earned its keep |
| 16 Recurring issues | Instance-trace gap **did not** recur here | |
| 17 New issue | Incident **A** ≠ recurring-flow **A**; method text still talks about “three recent instances” | |

---

## Three-case evidence table

| | Case 1 onboarding composite | Case 2 Netflix IAM | Case 3 GitHub 2018 |
| --- | --- | --- | --- |
| Scope | A | A | A |
| Trace | C | B | **A** |
| Diagnose | A | A | A |
| Intervene | B | B | B |
| Observe | B | B | B |
| Experience/Realization | A | A | B |
| Authority/Execution | B | A | B |
| Encode/Novel | B | A/B | B |
| Composition | A (onboarding join) | seam-only | **A** |
| Wrong-success | A | A | A |
| Abstraction cost | B | A | A |

---

## Trace-issue classification (after three cases)

Not automatically “method is wrong.”

This third case shows **A is possible** when the org published an
**instance timeline**.

Cases 1–2 failed **A** because of **public evidence limitation** and
**case-selection** (composite; workflow blog), plus a possible
**method-wording** mismatch (tracing doc assumes recurring delivery
instances; incidents are one-shot). **Unrealistic instance-trace
expectation** for *all* public validation is **partially** true;
**indeterminate** whether production use inside a company would hit A
more often. Do not change the method in this pass.

---

## Candidate method issues (do not fix)

- Recurring (weaker): “three instances” vs one incident.
- New: tracing guidance is written for **recurring delivery**, not
  incident timelines — operators must improvise the mapping.

## Candidate theory issues

None requiring frozen-core change. Composition language matched the
failure without a path owner.

---

## Recommendation

**REVIEW THREE-CASE EVIDENCE**

Do not start a fourth case. Do not edit the method until that review.
