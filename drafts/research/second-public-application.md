# Second public application of the initial method

*Netflix ConsoleMe. Method unchanged. Not proof of Convergence. Not
employer-specific.*

**Case type:** single organization (Netflix), first-party primary evidence.

**Trace evidence classification: B — documented workflow.**  
Not **A** (no named instances, no elapsed times, no “three recent
cases”). Not **C** (authors describe a lived support loop, not only
architecture). Not **D** (enough to follow intent → wait → decision).

---

## Intent / outcome

- **Consumer:** a Netflix employee who needs AWS permissions or
  console/CLI credentials to do work (blog: “internal cloud users,”
  “groups beyond software engineering”).
- **Class of intent (refined from evidence):** obtain **additional IAM
  permissions** (and, where required, related resource policies) so a
  role can perform a legitimate AWS action, without using Cloud
  Infrastructure Security’s support channel as the routine delivery
  interface.
- **Outcome that counts:** the needed permission exists and can be
  tested; security/cloud-admin **authority** over non-low-risk grants
  is not abandoned.
- **Why this method applies:** recurring specialist routing; support
  loop described as falling over at scale; mix of settled vs
  judgment-bearing requests.
- **Who owns this analysis:** this research pass.

**Boundary.** IAM permission *requests* and the security team’s
fulfillment of them. Credential retrieval for **already authorized**
roles (ConsoleMe/Weep mapping) is a **related but distinct** intent —
noted, not the primary trace.

**Exclusions.** Netflix IAM program as a whole; account vending;
networking; Repokid/Aardvark except as related least-privilege
context; federated multi-cloud (blog “what’s next” only).

**Intent level the evidence supports:** closer to “enough authorized
access for this role/action” than generic “I need AWS access.”
Credential login is “use a role I am already mapped to.”

---

## Primary sources (first-party)

| Source | Role |
| --- | --- |
| Netflix Technology Blog, Castrapel, Sanders, Kim, “ConsoleMe: A Central Control Plane for AWS Permissions and Access” (2021-03-10). <https://netflixtechblog.com/consoleme-a-central-control-plane-for-aws-permissions-and-access-fd09afdd60a8> | **Primary.** Historical 9-step loop; wizard; auto-approve of **low-risk** requests via configuration + Zelkova; qualitative outcomes. |
| Netflix/ConsoleMe GitHub (OSS, linked from the blog). <https://github.com/Netflix/ConsoleMe> | Points to docs, re:Invent talk, blog. Archive notice is later product status, not used as 2021 operational evidence. |
| ConsoleMe documentation (Netflix OSS docs site). Self-service wizard; policy request review. <https://hawkins.gitbook.io/consoleme/feature-videos/policy-management/self-service-iam-wizard> <https://hawkins.gitbook.io/consoleme/feature-videos/policy-management/policy-request-review-page> | **Documented OSS default behavior:** wizard submit → **cloud administrators** review; approve applies immediately. “In the future” route to resource owners. |
| ConsoleMe docs, role credential authorization. <https://hawkins.gitbook.io/consoleme/configuration/role-credential-authorization> | Mapping: after auth, which roles a user/group may assume (console vs CLI-only). |

**Secondary (context only, not a substitute for the loop):** Netflix
blog on Aardvark/Repokid (least-privilege *removal*, different intent).
re:Invent 2020 talk linked from the blog — not transcribed here;
blog is used as the citable first-party workflow.

---

## Current trace (pre-ConsoleMe) — documented workflow

Netflix: “Our historical approach of helping Netflix internal cloud
users looks something like this” and “We repeat this multiple times a
day.” **[documented workflow, not instance trace]**

| # | Initiating intent | Action | Participant | Resulting state | Wait | Why wait | Specialist judgment | Org routing | Authority | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Need AWS permission | Message support channel | User → Cloud Infrastructure Security | Request in queue/chat | Channel response | **Organizational routing** + **capacity** | No (relay) | Yes | None yet | Documented |
| 2 | Clarify need and why | Clarify, analyze risk, suggest better approaches | Security | Intent understood; maybe redirected | Analyst time | **Specialist judgment** + **missing information** | **Yes** | Support is the interface | Security | Documented |
| 3 | Express permission | Hand-craft IAM policy | Security | Policy draft | Crafting | **Specialist judgment** (JSON/expertise) **and** duplicated interpretation if similar to prior grants | Often | — | Security | Documented |
| 4 | Apply policy | Log in to account, mutate IAM | Security | Role policy changed | Login/apply | **Technical** + accidental shape (console hopping) | Low if draft exists | — | Security executes | Documented |
| 5 | Cross-account resource | Log out, log in to resource account, mutate resource policy | Security | Resource policy changed | Repeat of 4 | **Technical** + **governance** (second account) | Yes if novel | Extra hop | Security | Documented “if the request involves a cross-account resource” |
| 6 | Verify | Ask user to test | User | Unknown if sufficient | User test | **Missing information** (does it work?) | User observes errors | — | — | Documented |
| 7 | Access still denied | User returns with permissions error | User → Security | Incomplete grant | New cycle | **Missing information** | Yes (debug) | Same channel | Security | Documented |
| 8 | Iterate | Steps 3–7 (“permission whack-a-mole”) | Both | Eventually works or abandoned | Repeat | Same mix | Yes | Yes | Security | Documented |
| 9 | Next user | Repeat multiple times a day | Security | Same process | — | Scale | — | Yes | Security | Documented |

**Unknown:** elapsed time per request; fraction that were identical to
prior grants; Slack vs ticket; who else sat in the channel.

**Not manufactured:** timestamps, exact policy contents, instance IDs.

---

## Post-ConsoleMe path (as published)

**Do not treat OSS defaults as Netflix production unless the blog
agrees.**

| Path | What happens | Authority | Evidence status |
| --- | --- | --- | --- |
| Wizard | User picks role, chooses permissions in English, optional JSON edit, justification, submit | Request created | Documented (blog + OSS docs) |
| Low-risk auto-approve | “Low-risk permission requests can be automatically approved… governed by ConsoleMe’s configuration and powered by Zelkova” | **Execution** automated; **authority** still in config/rules (security-owned encoding) | **Documented at Netflix (blog).** OSS wizard page says requests **today go to cloud administrators** — that is **OSS default / generic**, not a contradiction of the blog’s Netflix claim. |
| Non-auto-approve | Submit for approval; admins approve/reject; approve applies immediately | Cloud administrators (OSS docs); blog: security as “accelerators” | Documented |
| Already-authorized credentials | Authenticate; mapping from identity/groups → roles; console or Weep (1-hour creds) | Mapping config/tags/plugin | Documented (blog + credential-authorization docs). **Different intent.** |

**Inferred (not claimed as event):** most Netflix requests are
auto-approved. **Unknown:** mix of auto-approve vs human review at
Netflix.

---

## Meaningful waits and WHY

| Wait | Why | Judgment? | Waste? |
| --- | --- | --- | --- |
| Support-channel pickup | Routing + capacity | No | Candidate accidental **shape** |
| Clarify/risk | Intentional control + missing info | Yes | Not assumed waste |
| Hand-crafting JSON | Expertise; often repeatable | Sometimes | Encode candidate if common |
| Console hopping / second account | Technical + accidental delivery | Low | Shape, not the control |
| User test / Access Denied loop | Missing information | Debug judgment | Accidental *opacity*; grant itself may be needed |
| Admin review of wizard request | Intentional unless request is in auto-approve set | Yes unless encoded as low-risk | Preserve if not encoded |

---

## Diagnostics used

**Always**

- Intent/outcome: additional IAM permissions for a role/action.
- Waits/WHY: above.
- Accidental vs intentional: channel as API and JSON-by-hand for
  common asks vs risk analysis and non-low-risk approval.
- **Experience vs realization:** **material here.** Wizard/typeahead =
  experience (consumer need not know JSON or which account to log into).
  Policy apply in AWS, auto-approve engine, and admin approve-applies =
  realization. OSS “email cloud admins” can be **new experience, same
  queue**. Blog auto-approve changes realization for a **subset**.
- Wrong-success: below.

**Conditional (activated because they change reasoning)**

- **Capability (light):** organization can already grant IAM
  permissions (human-realized). Encoding changes leverage, not
  existence. Name: `AdjustIamPermissionsForARole` — optional label.
- **Encode vs novel:** common wizard choices and low-risk auto-approve
  = encode; risk analysis and non-standard JSON = collaborate. Blog
  supports split; **exact encoded set UNKNOWN**.
- **Authority vs execution:** auto-approve **executes** a configured
  rule; it does **not** document that ConsoleMe *decides every*
  request. OSS still routes to administrators. **Prevents** “automation
  therefore has authority over all access.”
- **Organizational independence:** consumer need not know which account
  to log into for apply; ownership of roles still in mapping/tags.

**Composition:** **activated only for the documented seam** “IAM role
policy + cross-account resource policy when required.” Not because
ConsoleMe, Weep, Config, and Zelkova all exist.

**Unused:** federation.

---

## Expertise test

| Question | Answer | Status |
| --- | --- | --- |
| Settled enough to encode? | Common permission choices (configurable wizard); IAM JSON generation; low-risk class | Documented as *intent* of wizard + auto-approve |
| Evidence | Blog: configurable for most common requests; auto-approve low-risk via config + Zelkova | Documented |
| Remains contextual | Clarify need/why; “better approaches”; non-low-risk; advanced JSON | Documented |
| Who retains authority | Cloud Infrastructure Security historically; cloud administrators on OSS review; config owners for auto-approve | Documented |
| Challenge / escalate | Submit for approval; modify generated JSON; future resource-owner routing | Documented (future = not yet) |
| Reduce routing without pretending certainty gone | Auto-approve only *low-risk*; else approval | Documented at Netflix (blog). **UNKNOWN** how often that fires |

---

## Automating execution vs delegating authority

False inference to refuse: *if a request can be auto-fulfilled,
automation has authority to decide every request.*

Evidence: auto-approve is **conditional** (low-risk, configuration,
Zelkova). Human path remains. Credential mapping is **separate**:
ConsoleMe **executes** assume-role for roles the mapping already
**authorizes**; it does not, in these sources, create that
authorization by the act of clicking Weep.

---

## Documented historical intervention

ConsoleMe (+ Weep): central control plane for permissions and access;
wizard; policy editors; resource locator; role clone for admins;
least privilege via roles not users, inline policies, RepoKid
conjunction. Security team described as moving from gatekeepers to
“cloud development accelerators.”

---

## Convergence-derived intervention

Given **only** the pre-path: smallest change would be (1) stop using
the support channel as the *routine* interface, (2) encode common
permission requests (form/wizard + apply without console hopping),
(3) **keep** security judgment for risk/novel, (4) **not** automate
all grants, (5) **not** buy a catalog first, (6) change nothing is
unjustified given “multiple times a day” + falling over at scale.

---

## Comparison

**Materially similar.** A competent IAM/platform/security team could
reach ConsoleMe-shaped work from VSM + IAM least-privilege practice
without Convergence vocabulary. Convergence would **also** insist on
experience ≠ realization (wizard that still emails admins) and
execution ≠ authority (auto-approve ≠ universal authority). Those
discriminations match the **split** between blog Netflix behavior and
OSS-default admin queue.

---

## Documented outcomes (not treated as method validation)

Blog: wizard “has reduced our response time in servicing access
requests, provided more consistency in our IAM policies, and
simplified AWS permissions for our users.” **No durations or
counts.** Future work includes easier Access Denied debugging — implies
opacity **remained**.

---

## Prospective Convergence observations

If this were a live pass: mix of auto-approve vs review; exception
rate; still-in-Slack work beside ConsoleMe; Access Denied loops after
“approved”; who can change auto-approve config; whether resource-owner
routing shipped. Learning does not mandate action.

---

## Wrong-success

**What could look like success while the engineering system did not
actually improve?**

1. **Wizard launched; every request still waits on cloud
   administrators** (OSS default) — nicer experience, same realization
   queue.
2. **Auto-approve without a bounded low-risk definition** — velocity
   with unearned authority.
3. **Response time down on the security queue while users still loop on
   Access Denied** (blog still wants better deny debugging).
4. **Weep/console login treated as “IAM solved”** while *new*
   permissions still require the old channel.
5. **RepoKid removes unused permissions; wizard makes adding them back
   painless without settling which grants are standard** — least
   privilege as a treadmill, routing unchanged.

---

## Method observation (this case)

| # | Question | Verdict |
| --- | --- | --- |
| Trace vs instances | **B** | Workflow **A-adjacent** but not instance trace |
| Scope | **A** | Split credentials-vs-new-permissions; avoided whole IAM program |
| Diagnose | **A** | Authority/execution and exp/realization changed conclusions |
| Intervene vs IAM analysis | **B** | Similar to what Netflix did |
| Wrong-success | **A** | OSS vs Netflix auto-approve; login vs grant |
| Forced vocabulary | Composition almost unused; federation unused | |
| Abstraction cost | **A** vs case 1 | Narrower case |

---

## Comparison with case #1

1. Better evidence **did** improve Trace: first-party numbered loop vs
   multi-company synthesis. Still not **A**.
2. Workflow trace **was** useful; method’s “three instances” still unmet.
3. Scope changed a decision (not all “AWS access”).
4. Diagnose changed a decision (don’t treat auto-approve as
   all-authority; don’t treat wizard as the fix).
5. Experience vs realization **mattered again** (OSS admin queue).
6. Authority vs execution **prevented a bad conclusion**.
7. Encode vs novel **actionable** (low-risk vs rest); encoded *set*
   UNKNOWN.
8. Intervene ≈ strong IAM analysis; extra value at **joins**.
9. Wrong-success can miss “we open-sourced a control plane.”
10. Formal capability name optional.
11. Value at IAM × security × DX joins: **yes**.
12. Abstraction cost **decreased**.
13. Case #1 issue **recurred in weaker form:** still no instance-level
    trace (now workflow, not composite).
14. **New candidate issue:** first-party **blog (Netflix prod claim)**
    vs **OSS docs (generic default)** can be conflated into one path.
    Method does not say how to split product-default from one firm’s
    production. Do not fix.
15. Method should **remain unchanged** for a third application.

---

## Cross-case evidence (do not modify method)

| | Case 1 (composite onboarding) | Case 2 (Netflix IAM) |
| --- | --- | --- |
| Scope | A | A |
| Trace | C | B |
| Diagnose | A | A |
| Intervene | B | B |
| Observe | B (plan only) | B (plan + weak published outcomes) |
| Experience/Realization | A | A |
| Authority/Execution | B | A |
| Encode/Novel | B | A/B |
| Wrong-success | A | A |
| Abstraction cost | B | A (lower) |

---

## Candidate method issues (do not fix)

- Recurring: public sources rarely yield **instance** traces (**A**).
  **B** is usable; calling **B** an instance trace would be a method
  failure we avoided.
- New: **one-org OSS docs ≠ that org’s production path.**

## Candidate theory issues

None that require a frozen-core change.

---

## Recommendation

**RUN THIRD CASE UNCHANGED**

Prefer another **single-org first-party workflow** (not composite),
ideally with at least one quantitative elapsed-time or instance
anecdote, still without editing the method. If a third case still
cannot produce **A**, then **REVIEW REPEATED METHOD ISSUE** (public
validation vs instance-trace requirement) — not in this pass.
