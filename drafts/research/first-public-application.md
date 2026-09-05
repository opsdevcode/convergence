# First public application of the initial method

*Not field validation. Not employer-specific. Not a claim that Convergence
works. One pass of Scope → Trace → Diagnose → Intervene → Observe.*

**Case type:** **public-evidence composite.** The events below did **not**
occur at one company. Each step is tagged **[documented]** (named source) or
**[synthesis]** (join inferred for this pass). Unknown is recorded as
unknown.

---

## Intent / outcome

- **Consumer:** a product / feature team that is not the platform, network,
  identity, or security function.
- **Class of intent:** obtain a **standard, governed cloud workspace**
  (account or cloud project) that is identity-integrated, attached to
  org-standard networking, and eligible for a first application/CI path —
  not a novel architecture.
- **Outcome that counts:** the team can deploy a *standard* workload into
  that workspace without assembling the org chart for routine setup.
- **Why this method applies:** the intent crosses platform, cloud
  governance, networking, identity, and security; public sources describe
  weeks of setup, Slack/support as the interface, and “self-service”
  that still leaves a lot of work after an account exists.
- **Who owns the result of this analysis:** this research pass (not a
  company).

**Scope boundary.** Standard/low-variance onboarding only.

**Out of scope.** Novel network architecture, production data-class
exceptions, multi-region, mergers/shadow-IT accounts, federated
multi-cloud, and any employer.

---

## Sources

| Source | What it documents | Used as |
| --- | --- | --- |
| Spotify Engineering, “How We Improved Developer Productivity for Our DevOps Teams” (2020-08). <https://engineering.atspotify.com/2020/08/how-we-improved-developer-productivity-for-our-devops-teams> | Manual sequence: GitHub repo → make portal aware → GCP project → Jenkins pipeline → docs → Slack. ~14 days to start a campaign site; later Golden Paths + Backstage wizard → GCP project + GHE + CI in <5 minutes for that class of work. | **[documented]** instance-like sequence and elapsed-time *at Spotify for websites*, not for AWS account vending |
| Netflix Tech Blog, “ConsoleMe: A Central Control Plane for AWS Permissions and Access” (2021-03-10). <https://netflixtechblog.com/consoleme-a-central-control-plane-for-aws-permissions-and-access-fd09afdd60a8> | Cloud Infrastructure Security as arbiter of AWS permissions. Historical loop: support channel → clarify/risk → hand-craft IAM → mutate policies (incl. cross-account) → user test → permission errors → repeat. Low-risk wizard requests can auto-approve (Zelkova); others stay approval. | **[documented]** IAM/identity-security delivery path *at Netflix* |
| Wiz, “Scaling AWS account management from landing zones to account vending” (Scott Piper). <https://www.wiz.io/blog/scaling-aws-account-management-from-landing-zones-to-account-vending> | Typical landing-zone contents: CloudTrail, SCPs, IdP/SSO, encryption defaults, shared networking (Shared VPC / peering / TGW), auto-configured new accounts. After auto-create, **owners still do a lot of work** to use the account; vending should also cover repo/IaC/alerts outside the account. | **[documented]** industry pattern (vendor blog; operational, not a single customer’s tickets) |
| AWS, “Overview of AWS Control Tower Account Factory for Terraform (AFT)”. <https://docs.aws.amazon.com/controltower/latest/userguide/aft-overview.html> | GitOps account request → provision → customizations; AFT is **not** for deploying application resources (EC2 etc.). | **[documented]** account factory vs application path |
| DORA, “Loosely coupled teams”. <https://dora.dev/capabilities/loosely-coupled-teams/> | Wait times for reviews, approvals, or required work from dependent teams as a coupling signal. | **[documented]** wait *type*, not a duration for this intent |

**Not used as evidence:** SEO roundups; LinkedIn résumés; unnamed “weeks of tickets” blog fiction.

---

## Current trace

No three recent instances at one firm exist in the sources. This is a
**reconstructed representative path** for the bounded intent.

| # | Interaction | Decides | Authority (as documented) | Same answer every time? | Why it waits (hypothesis) | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Discover how to get a cloud project/account | Nothing (lookup) | None | Yes (tribal) | **Organizational routing** / missing information | Spotify: docs + Slack; “make the developer portal aware, manually” |
| 2 | Create repo | Repo exists | Consumer | Mechanical | **Technical** (Git) | Spotify |
| 3 | Request/create cloud project or account | Placement in org / baseline | Cloud/platform or landing-zone automation | For standard: often yes | Mix: **governance** (org baseline) + **capacity/process** if ticketed | Spotify: GCP project *manually*; Wiz/AWS: Control Tower/AFT *can* automate enrollment |
| 4 | Attach identity (SSO / who can assume roles) | Who may act in the workspace | Identity + security | Standard mappings often repeat; exceptions vary | **Governance** + **specialist judgment** when the ask is not a known pattern | Netflix: security arbiter; Wiz: IdP integration as landing-zone item |
| 5 | Attach standard networking (shared VPC / TGW / subnets) | Placement, isolation | Networking | Standard pattern often repeats | **Technical dependency** + **intentional control** (isolation) | Wiz: shared networking as landing-zone item; no public wait times |
| 6 | Baseline logging/guardrails (CloudTrail, SCPs, encryption) | Org-wide constraints | Security / cloud governance | Yes for org standard | **Intentional governance** | Wiz; AWS AFT customizations |
| 7 | IAM / permissions for the actual workload | Least-privilege policy | Security (Netflix) | **No** until the app’s needs are known; then often trial-and-error | **Specialist judgment** + **missing information** (whack-a-mole) | Netflix 9-step loop |
| 8 | CI / pipeline so the app can deploy | Pipeline exists | Platform or team | Standard web/backend: Spotify later encoded; historically manual Jenkins | **Accidental process** when every team rebuilds Jenkins | Spotify |
| 9 | Test and return with Access Denied / missing integration | Whether the path actually works | Mixed | Often no on first try | **Missing information** (opaque denies); **technical** | Netflix steps 6–8; Spotify “read a bunch of documentation” |

**Unknown (not invented):** elapsed days for network attach or SSO at Netflix or Spotify; who holds composite accountability for “workspace ready”; ticket vs Slack mix outside those two firms.

---

## Meaningful waits and dependencies

| Wait | Why (overlapping OK) | Specialist judgment? | Who/what must act |
| --- | --- | --- | --- |
| Finding the process | Routing / missing information | No | Whoever currently answers Slack/docs |
| Manual portal/CMDB registration | Accidental process (Spotify) | No | Consumer + whoever owns the catalog |
| Cloud project/account | Governance (baseline) ± process | Low if standard; yes if exception | Platform/cloud governance |
| Network attach | Technical + intentional isolation | Usually no for *standard* shared pattern; yes if new pattern | Networking |
| IAM for the workload | Judgment + missing info (Netflix) | **Yes** until pattern is known | Security; consumer tests |
| CI setup | Accidental if every team rebuilds | No for standard | Historically the squad (Spotify) |
| Opaque Access Denied | Missing information | Sometimes | Security/platform + consumer |

**Not assumed waste:** SCP/CloudTrail/SSO/network isolation; Netflix risk analysis for non-standard IAM; DORA-style approvals that carry independent judgment.

---

## Diagnostics used

**Always**

- **Intent / outcome:** as scoped.
- **Waits and WHY:** table above.
- **Accidental vs intentional:** discovery, Slack, manual portal awareness, per-team Jenkins, and IAM trial-and-error are mostly accidental *shape*. Isolation, SCPs, SSO, logging, and non-low-risk IAM review are intentional *constraint*.
- **Experience vs realization:** Spotify Backstage/Golden Path wizard = **experience**; GCP project + repo + CI = **realization**. Netflix ConsoleMe wizard = **experience**; policy mutation in accounts = **realization**. Landing-zone “account exists” can succeed as experience while realization of *usable* identity/network/CI remains a queue (Wiz).
- **Wrong-success:** see below.

**Conditional (activated)**

- **Capability (light name only):** the org can already satisfy “standard workspace + first deploy path” (Spotify after encoding; Netflix still could grant IAM, slowly). Name used here: `ProvideStandardGovernedCloudWorkspace`. Not a catalog entry.
- **Encode vs novel:** Spotify’s 14-day path was low-variance setup → encode. Netflix: common IAM requests wizard + auto-approve **low-risk only**; novel/cross-account stays human. Activated.
- **Authority vs execution:** Netflix security remains arbiter; execution of policy application can move without moving authority. AFT/Control Tower execute account baselines; they do not (per AWS) deploy the application. Activated.
- **Composition:** workspace = account/project **plus** identity **plus** network **plus** CI. Parts can succeed (account vended; IAM later fails; AFT explicitly not for app resources). Activated.
- **Organizational independence:** Spotify “ops in squad” still had to walk tools/docs/Slack; independence is a spectrum. Activated.

**Not used:** federation, capability graph, maturity spectra, agent contracts.

---

## Intentional constraints

Preserve (do not delete in the name of flow):

- Org guardrails (SCPs, logging, encryption defaults) — **security / cloud governance**.
- Standard network isolation (prod/dev not freely meshed) — **networking**.
- Identity integration (no long-lived static keys; Netflix prefers roles) — **identity/security**.
- Human review of **non-low-risk** IAM / novel architecture — **security** (Netflix auto-approve is bounded).

Unknown: exact data-class rules for this composite (N/A — not in sources).

---

## System problem

Consumers of **routine** “give me a standard place to run this app” still
assemble **several specialist realizations** (project/account, identity,
network, CI, IAM) through lookup, Slack, and trial-and-error. Landing-zone
or portal steps can complete while the **composed** intent is not
satisfied. The specialties are necessary; the org walk is the delivery
interface.

---

## Proposed intervention

**Smallest justified change:** encode the **settled standard composition**
(workspace baseline + identity attach + standard network attach + CI
skeleton) so the consumer expresses intent once at that level, **and** keep
**explicit specialist review** for IAM/network/security that is not in the
documented standard (Netflix low-risk auto-approve pattern; Spotify golden
path as optional, not a mandate).

Realization may stay human for exceptions. Experience may be a wizard,
GitOps file, or a conversation with a checklist — **not prescribed**.

**Change nothing** is rejected: Spotify and Netflix both documented repeated
low-leverage specialist/consumer toil on this class of work.

### Rejected alternatives

| Alternative | Why rejected |
| --- | --- |
| Platform / IDP purchase first | Catalog-first; Wiz already separates “account exists” from usable ecosystem; method forbids IDP as prerequisite |
| Experience-only portal | Spotify still had “make the portal aware, manually”; Netflix still had policy **realization** in accounts |
| Automate all IAM | Netflix kept risk analysis and non-auto-approve; would move authority to the consumer |
| Reorganization | Not in evidence; Principle 3 |
| Encode novel network/IAM | Would freeze unsettled judgment |
| Observation-only | Would not change the assembled path; observe *after* encoding the standard |

---

## Wrong-success condition

**What could look like success while the engineering system did not actually
improve?**

1. **Portal / Backstage / Service Catalog launched; registration is still
   manual** (Spotify’s “make the developer portal aware, manually”).
2. **Account/project vended (landing zone green); team still spends days on
   SSO, network attach, IAM, and CI** (Wiz: owners still do a lot of work;
   AFT not for application resources).
3. **IAM request volume / ticket count drops because a wizard files the same
   security queue** (experience changed; realization is still the arbiter
   hop for *routine* cases).
4. **Auto-approve or “you build it, you run it” without encoded bounds** —
   local velocity up, blast radius/authority confused (opposite of Netflix
   Zelkova-bounded auto-approve).
5. **Platform team SLA improves; product e2e still waits on networking or
   Access Denied** (DORA: local vs dependent-team wait).

---

## Evidence to observe

**Prospective only. No post-intervention results are claimed.**

- Elapsed time vs working time for *standard* workspace-to-first-deploy
  (Spotify published 14 days → <5 minutes *for their website class*; do not
  generalize that number).
- Exception/off-path rate (if common, the encoding is wrong).
- Whether specialists still perform the **standard** path beside the
  encoded one (decay / portal-as-router).
- Access Denied loops after “success” of account creation.
- Who can change SCPs/network/IAM encodings (authority still with domains).
- Learning: ignore vs act — a method cannot force action.

---

## Method observation

Evaluate the **method**, not Convergence theory.

| # | Question | Verdict | Note |
| --- | --- | --- | --- |
| 1 | Most value | **A** | **Diagnose** (esp. experience vs realization + composition of landing-zone vs usable path) |
| 2 | Least value | **C** | **Trace** as written wants three *instances*; public sources gave two firm sequences plus a pattern blog — had to synthesize |
| 3 | Move failed to change a decision? | **B** | Observe is only a plan here (correctly); it did not change the intervention |
| 4 | Conditionals that activated naturally | encode vs novel; authority vs execution; composition; light capability name; org independence | |
| 5 | Forced? | Capability *catalog* / graph / federation — **not used**. Formal capability name was optional; used one phrase for the record only. |
| 6 | Record enough? | **B** | Enough for a decision; weak on network wait evidence |
| 7 | Missing from record? | Named **unknowns** for network/SSO durations; no owner of the *composite* in public sources |
| 8 | Premature solutioning? | **B** | Intervene menu pulls toward encode; resisted IDP/portal-first. Still easy to over-specify “wizard” |
| 9 | Preserved governance/authority? | **A** | Kept SCPs/isolation/non-low-risk IAM review |
| 10 | Easier than architecture / PE / VSM? | **B** | Same answer as paved-road + VSM + IAM pipeline; **join** (account ≠ usable composition) was the extra cut |
| 11 | Established practices already? | Platform engineering paved path; Netflix ConsoleMe; DORA waits; AWS AFT | |
| 12 | Value at the joins? | **A/B** | Landing-zone vs application factory (AFT note); experience vs realization; authority ≠ execution |
| 13 | Abstraction cost | **B** | Acceptable because most terms stayed unused |
| 14 | Five-move structure | **B** | Held; Trace strained on public evidence quality |
| 15 | Second case unchanged? | **Yes** | See recommendation |

**Candidate issue (method — do not fix)**

Public application often cannot produce “three recent instances.” The method
allows **unknown** and “stop widening,” but does not say how to label a
**composite reconstruction**. Risk: readers treat synthesis as a trace.
Record only.

**THEORY OBSERVATION → Candidate contradiction**

None. No frozen-core change indicated.

---

## Recommendation for validation program

**RUN SECOND CASE UNCHANGED**

Prefer a second *narrower* public case with a denser instance trace (e.g.
IAM-only like Netflix, or website-only like Spotify) to test Trace without
a composite. Do not change the five moves based on this pass.
