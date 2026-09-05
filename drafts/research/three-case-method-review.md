# Three-case review of the initial application method

*Document-based applications only. Not field validation. Not a novelty
study. Method and theory not modified in this pass.*

Cases:

1. Public-evidence **composite** cloud workspace onboarding (Trace **C**)
2. Netflix ConsoleMe IAM permission requests (Trace **B**)
3. GitHub 2018-10-21 metadata incident (Trace **A**)

Method under review: **Scope → Trace → Diagnose → Intervene → Observe**
(initial application method, not frozen doctrine).

---

## 1. Executive finding

Across three document-based applications, the five-move method **held
together** and did not force harmful conclusions. What repeatedly
**changed decisions** was **Scope**, **Diagnose** (especially joins:
experience vs realization, authority vs execution, composition), and
**wrong-success**. **Intervene** repeatedly produced actions **materially
similar** to competent platform / IAM / SRE practice. Convergence’s
practical contribution in these cases was **selecting and rejecting
interventions** and **naming system-level failure modes at joins**, not
inventing different fixes.

There is **not** enough repeated evidence to change the five-move
structure. There **is** repeated evidence that **Trace guidance is written
too narrowly around recurring delivery instances**, which is a
**documentation-scope** issue, not a demonstrated method defect.

**Recommended decision:** **MAKE NARROW DOCUMENTATION CLARIFICATION**
(Trace wording only). Do not implement in this pass. Do not revise the
method. Do not start a fourth case until that clarification is considered.

---

## 2. Evidence matrix (five moves)

### Scope — verdict A / A / A

| | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Verdict | A | A | A |
| Decision affected | Standard workspace only; not enterprise cloud | IAM *grants* vs already-authorized Weep/console login; not whole IAM program | Metadata path + this partition class; not all SRE / not Git storage |
| Evidence | Named exclusions; composite still bounded | “I need AWS access” vs “enough permission for this role/action” | 43s network ≠ 24h customer impact class |
| Same as established practice? | Scoping a problem is ordinary | Same | Same |
| Join add? | Cross-specialty *unit* (one intent) | Split two intents that a “cloud access” analysis would mash | Customer metadata vs component HA |
| Abstraction cost | Low | Low | Low |
| Recurring issue | None | None | None |

**Innocent until otherwise:** Scope is **repeatedly useful**. Not a
method invention; still changed every pass.

### Trace — verdict C / B / A

| | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Verdict | C | B | A |
| Decision affected | Forced honesty: reconstruction ≠ instance; weak network waits | Followed the 9-step support loop; did not invent times | 43s partition ≠ customer duration; topology vs writes |
| Evidence | Explicit composite; no three instances | Netflix numbered historical approach, “multiple times a day” | Timestamped 22:52–23:03 timeline |
| Same as VSM / postmortem? | Reconstructing a path is ordinary | Same | Incident timeline is SRE ordinary |
| Join add? | Little while C | Sequence of routing vs judgment | 43s vs 24h |
| Abstraction cost | High when synthesizing | Lower | Low |
| Recurring issue | Instance-trace bar vs public sources | Same, weaker | Tracing doc assumes recurring flows |

**Trace reality** (follow what happened, not the org chart) is
**supported**. The **grade** tracks **evidence quality**, not method
failure.

### Diagnose — verdict A / A / A

| | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Verdict | A | A | A |
| Decision affected | Account/portal ≠ usable path; keep guardrails | Don’t treat wizard as the fix; don’t treat auto-approve as all-authority | Orchestrator/network/app “success” ≠ customer path |
| Evidence | Landing-zone vs AFT-not-for-apps; portal still manual | OSS admin queue vs Netflix bounded auto-approve | Postmortem: configured failover vs app latency/integrity |
| Same as established? | PE + IAM + VSM cover parts | IAM + DX cover parts | SRE postmortem covers most |
| Join add? | **Yes** (composition of workspace) | Exp/real + authority/execution | **Yes** (composite HA contract) |
| Abstraction cost | Acceptable (unused terms skipped) | Lower | Low; composition earned keep |
| Recurring issue | None on the move itself | None | None |

### Intervene — verdict B / B / B

| | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Verdict | B | B | B |
| Decision affected | Encode settled composition; keep specialist review; reject IDP-first, experience-only, automate-all-IAM, reorg, change-nothing | Same shape as ConsoleMe; reject catalog-first and unbounded auto-approve | Align failover with composite contract; keep human integrity; don’t add more blind automation; N+1 larger than smallest |
| Evidence | Compared to Spotify/Netflix/Wiz historical directions | “Materially similar” to Netflix | “Materially similar” to Orchestrator config + testing |
| Same as established? | **Yes** — paved road, IAM pipeline, landing-zone vs vending | VSM + IAM least privilege | SRE HA review |
| Join add? | **Rejection** of wrong fixes more than a new fix | Same | Same |
| Abstraction cost | Intervene menu can pull toward “encode/wizard” | Resisted | Did not invent path owner |
| Recurring issue | Distinctive *action* not found | Same | Same |

### Observe — verdict B / B / B

| | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Verdict | B | B | B |
| Decision affected | Did **not** change the intervention (prospective plan only) | Same; qualitative blog outcomes not used as proof | Wrong-success sharpened what “green” would hide; still prospective for future |
| Evidence | Explicit: Observe failed to change intervention | Same | Status/ETA/TTL as observation objects |
| Same as established? | SLIs / postmortem follow-up | Same | Same |
| Join add? | Wrong-success list (see §7) | Same | Same |
| Abstraction cost | Low | Low | Low |
| Recurring issue | Document-based cases cannot show learning-in-action | Same | Cannot audit whether GitHub shipped N+1 |

**Wrong-success** (always-used check, often written before/with
Intervene) is **stronger** than Observe-as-a-move in these three
document cases. The **move** still has a job (what to watch; learning
does not mandate action). Collapsing it is **not** warranted by
repeated failure—only by “didn’t change the pick” in #1–#2.

---

## 3. Diagnostic classification (from these applications)

| Diagnostic | Class | Notes |
| --- | --- | --- |
| Intent / outcome | **CORE IN PRACTICE** | Every case; Scope’s payload |
| Wait WHY | **CORE IN PRACTICE** | Prevented treating all waits as waste (#1–#3) |
| Accidental vs intentional | **CORE IN PRACTICE** | Guardrails, IAM risk, integrity hold vs Slack/JSON-hopping/43s partition |
| Experience vs Realization | **FREQUENT CONDITIONAL** in effect, **always-used in the method** | **A** in #1–#2; **B** in #3 (status vs internals). Strong in platform/IAM; not the core of reliability |
| Wrong-success | **CORE IN PRACTICE** | **A** all three; see §7 |
| Capability naming | **LOW VALUE SO FAR** | Optional labels only; catalog/graph unused |
| Encode vs novel | **FREQUENT CONDITIONAL** | Actionable in #1–#3; encoded *set* often UNKNOWN |
| Authority vs execution | **FREQUENT CONDITIONAL** | **A** in #2; **B** in #1 and #3; prevents a specific false inference |
| Composition | **FREQUENT CONDITIONAL** | **A** when the whole can fail while parts succeed (#1, #3); seam-only in #2 |
| Organizational independence | **CASE-SPECIFIC** | Used in #1–#2; N/A in #3 |
| Federation | **NOT TESTED ENOUGH** | Unused all three (correct skip) |

Do not promote federation or formal capability names from this set.

---

## 4. Emerging-pattern tests

| Pattern | Verdict | Evidence |
| --- | --- | --- |
| **A.** Scope consistently useful | **SUPPORTED** | A/A/A; each changed a bound |
| **B.** Diagnose consistently useful | **SUPPORTED** | A/A/A; each changed a conclusion |
| **C.** Intervene similar to competent practice | **SUPPORTED** | B/B/B; paved road / ConsoleMe / Orchestrator constraint |
| **D.** Value more in diagnosing joins than inventing interventions | **SUPPORTED** | All three comparisons say extra is the join / rejection, not a new gadget |
| **E.** Exp vs realization strong in platform/IAM, less central in reliability | **SUPPORTED** | A/A vs B in #3; still *some* status-vs-realization value |
| **F.** Authority vs execution when specialized authority + delegated execution | **SUPPORTED** | Strongest in #2 auto-approve; present in #1 AFT/IAM; #3 Orchestrator executed vs human integrity |
| **G.** Composition when locally valid parts, invalid whole | **SUPPORTED** | #1 landing-zone green; #3 Orchestrator/app/network; #2 only when resource+IAM policies |
| **H.** Wrong-success useful across domains | **SUPPORTED** | A/A/A; different false greens |
| **I.** Abstraction cost falls as scope narrows and evidence strengthens | **SUPPORTED** | B → A → A on abstraction; #3 composition “earned keep” |

None of A–I is **contradicted**. **E** is not “exp/real failed in
reliability”; it was **less central**.

---

## 5. Trace issue analysis

Recorded grades: **C / B / A**.

| Question | Conclusion | Class |
| --- | --- | --- |
| 1. Is “trace reality” still supported? | **Yes.** Org-chart-first was avoided; following sequence changed #2 and #3. #1’s C was honest about not having reality. | **NO ISSUE** with the *principle* |
| 2. Multiple recent instances for **every** application? | **Not supported as a universal requirement.** Method README still asks for “two or three recent instances” in Scope evidence; tracing doc: “Trace specific instances.” #3 is one incident. #2 is a repeated workflow without three named cases. | **DOCUMENTATION SCOPE ISSUE** (and a bit of **VALIDATION-DATA ISSUE** for public blogs) |
| 3. Is `tracing-a-flow.md` overly written around recurring delivery? | **Yes, as awkwardness, not as a failed move.** #3 operators mapped an incident timeline onto a delivery-trace template. | **DOCUMENTATION SCOPE ISSUE** |

**Not a METHOD DEFECT** of “Trace as a move.”  
**Not** enough to drop Trace.  
Calling **B** or **C** an instance trace would have been a method
**failure**; the applications **avoided** that.

---

## 6. Intervene analysis

| | Diagnosed | Recommended | Historical / competent practice |
| --- | --- | --- | --- |
| #1 | Org walk; portal ≠ usable composition | Encode settled composition; keep review; reject IDP-first | Spotify golden path / landing-zone vs vending / Netflix split |
| #2 | Channel as API; JSON hopping; judgment still needed | Encode common grants; keep security authority; no unbounded auto-approve | ConsoleMe + bounded auto-approve |
| #3 | Composite HA contract failed; local success | Align encoded failover with app contract; keep integrity judgment | Orchestrator no cross-region promote + chaos |

**Primary practical value in this evidence (combination):**

1. **Preventing wrong interventions** (IDP-first, experience-only portal,
   automate-all-IAM, more blind failover, change-nothing, path owner)
2. **Exposing system-level failure modes** (account ≠ workspace;
   wizard ≠ realization; topology ≠ customer path)
3. **Selecting among known interventions** (encode the settled join;
   keep human for novel)
4. **Shared reasoning across specialties** (same record, different
   domains)

**Not supported:** generating **different** interventions as the main
contribution.

Acceptable result: *Convergence often recommends familiar engineering
actions but improves the reasoning used to select or reject them.*

---

## 7. Wrong-success analysis

Checks that **repeatedly** appeared:

| Failure mode | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Artifact vs outcome | Portal / catalog | Wizard / open-source control plane | Orchestrator “valid topology” |
| Local vs system | Landing-zone green; team SLA | Security queue time vs Access Denied | 43s network; East primaries vs replica lag |
| Automation replacing authority | Unbounded auto-approve / you-build-it | Auto-approve without low-risk bound | (Weaker; Orchestrator executed encoded rule) |
| Experience hiding realization | Portal still tickets | OSS email-admins | Status yellow/red/green vs mixed availability |
| Recovery hiding weakness | — | Weep as “IAM solved” | Webhook “done” after TTL drop |

**Always-used status:** **keep.** Repeated **A**. Do **not** promote
further (no new principle, no extra move). It already sits in Diagnose
and Observe; that overlap is **documentation**, not a defect requiring
a new check.

---

## 8. Strongest argument against the five-move method

A competent engineer could get the **same interventions** from VSM +
platform engineering + IAM practice + SRE postmortem **without** five
named moves. Intervene is **B** three times. Observe often did not
change the pick. Trace’s published bar (“instances”) is a poor fit
for both public blogs and incidents, so the method **looks** more
demanding than the analyses actually needed. The distinctive work is
**Diagnose + wrong-success + rejection**, which could be taught as a
lens on existing practice rather than a five-step method. Five moves
risk **ceremony** relative to the size of the extra cut.

That argument is **serious** and **not refuted** by these cases. It is
also **not** sufficient, on three document-based passes, to collapse or
remove a move: each move still **did work** when evidence allowed;
removing Trace would have hidden #1’s C-honesty and #3’s 43s-vs-24h;
removing Scope would have mashed intents in #2–#3.

---

## 9. Candidate method / documentation issues

| Candidate | A/B/C/D | Notes |
| --- | --- | --- |
| Drop or collapse a five-move | **D** | Falsification attempted; not enough to remove a move |
| Intervene as “must invent a new action” | **D** | Evidence says otherwise; method already allows familiar actions |
| Formal capability names always | **D** | Low value; already conditional |
| Trace: allow labeled workflow / incident / composite without calling them instance traces | **C** | Repeated across #1–#3 |
| `tracing-a-flow.md`: one paragraph that incident timelines are valid traces of *that instance* | **C** | #3 |
| Method README Scope “two or three recent instances” vs “at least one followable path (instances, documented workflow, or incident timeline), labeled” | **C** | Do not weaken “don’t invent instances” |
| How to split OSS-default vs one firm’s production (#2) | **B** | One case; validation/data + light method note later |
| Composite reconstruction protocol (#1) | **B** | One case; don’t encode composites as first-class traces |
| Collapse Observe into Diagnose | **B** | #1–#2 Observe didn’t change pick; #3 still used watch-list; **not A** |

No **A** (change the method now).

---

## 10. Candidate theory issues

**None** from these three applications: no contradiction, no unusable
distinction that failed to map, no principle that pushed a harmful
conclusion (integrity hold, non-low-risk IAM, isolation, SCPs were
preserved).

Three document cases **do not validate** theory.

---

## 11. What the evidence DOES support

- The method can be **applied** to platform onboarding (awkwardly), IAM,
  and a reliability incident **without** changing theory.
- **Scope, Diagnose, wrong-success** repeatedly sharpened decisions.
- **Joins** (exp/real, authority/execution, composition) are where extra
  reasoning showed up.
- **Intervene** matches competent existing practice and **rejects**
  several anti-patterns the method already lists.
- **Trace quality tracks source quality** (C/B/A).
- Abstraction cost can stay acceptable if unused terms stay unused.
- Timeboxes, field usability, and causal improvement are **untested**.

---

## 12. What the evidence DOES NOT support

- Field effectiveness or independent practitioner repeatability
- Causal improvement from using the method
- Organizational adoption
- Accuracy of 30 / 60–120 minute design goals
- That Convergence produces **better interventions** than PE/IAM/SRE
- That the five-move structure is **necessary** (only that it was
  **usable**)
- That Trace **must** be grade A for the method to be used (B was
  decision-changing in #2)
- Theory validation
- Distinctiveness / uniqueness of Convergence

---

## 13. Recommended next action

**MAKE NARROW DOCUMENTATION CLARIFICATION** (not implemented here):

Clarify in method/tracing **only** that a pass may rest on (and must
**label**): instance timeline, documented workflow, or (weakest)
reconstruction — and must **not** relabel C as A.

Keep five moves, always-used wrong-success, conditional composition /
authority / encode, no new steps, no theory edits, no fourth case until
that clarification is explicitly accepted or rejected.

If that clarification is rejected, the fallback is **KEEP METHOD
UNCHANGED**.

**Not chosen:** REVIEW SPECIFIC METHOD CHANGE (no A-class method
change). **Not chosen:** METHOD REQUIRES SUBSTANTIAL REVISION.
