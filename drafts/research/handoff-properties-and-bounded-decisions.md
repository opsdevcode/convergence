# Handoff Properties and Bounded Decisions

*Research draft. Not canonical methodology; not field validated; does not add
elements to the conceptual model; and does not prescribe an evidence schema,
exception schema, workflow engine, policy engine, IDP, or automation
architecture.*

## 1. Research question

**Hypothesis, not a Convergence principle:**

> An organizational handoff may be carrying engineering properties in addition
> to transferring work. Before removing or encoding the handoff, identify which
> properties are necessary, which are accidental, and how necessary properties
> will survive the change.

The hypothesis must earn value beyond the existing accidental-versus-intentional
friction lens. It fails if it only relabels “preserve judgment and authority;
remove routing and duplicated interpretation.”

## 2. Corpus boundary

The current corpus already supplies substantial coverage:

| Existing concept | Coverage of this question | Research disposition |
| --- | --- | --- |
| Accidental vs intentional friction | Asks what value an interaction provides; preserves authority, judgment, accountability, context, and constraints while reducing routing and duplication. | A. Already present |
| Encode repeatable / collaborate on novel | Separates settled reapplication from unresolved judgment; human realization remains valid. | A. Already present |
| Authority vs execution | Prevents an executor or automation from acquiring a domain decision right. | A. Already present |
| Human realization | Treats people, standards, and organizational knowledge as legitimate fulfillment. | A. Already present |
| Organizational independence | Removes consumers’ need to navigate the organization while retaining discoverable ownership, authority, provenance, and auditability. | A. Already present |
| Capability contracts | Names expectations, constraints, policy, ownership, exceptions, and proportional rigor without a mandatory schema. | A. Already present |
| Policy attachment | Locates eligibility, enforcement, and composition constraints without prescribing an engine. | A. Already present |
| Composition / composite accountability | Keeps the whole accountable for coherence and seams without transferring contributor authority. | A. Already present |
| Observation | Attaches evidence to capabilities and composition edges; requires attribution without consumer exposure. | A. Already present |
| Learning | Defines learning as evidence capable of changing beliefs, while refusing to guarantee action. | A. Already present |
| Provenance | Is discoverable where needed, but knowledge provenance is explicitly an open question rather than a required record. | B. Useful refinement to test |
| Wrong-success | Tests local artifact or component success against the intended outcome and preserved constraints. | A. Already present |
| Handoff mechanism versus carried property | Makes explicit that a control’s value and its organizational delivery shape can differ. | B. Useful refinement to test |
| Evidence lenses below | May make an observation question more specific; they must not silently duplicate Observation. | B. Useful refinement to test |
| Bounded human decision | May clarify authorization for realization after a human decision; authority/execution and contracts already cover much of it. | B. Useful refinement to test |

No distinction here is a new model element. “Handoff property” is an analysis
phrase, not a replacement name for contract, policy, authority, realization,
or observation.

## 3. Evidence lenses

Evidence may overlap across these questions:

| Lens | Question it may answer | Existing overlap and limit |
| --- | --- | --- |
| Outcome | Did the intended result occur? | Outcome and wrong-success already ask this. |
| Decision | Why was a consequential determination made? | Authority, judgment, and exception paths already cover parts of it. |
| Realization | What actually fulfilled or attempted to fulfill the intent? | Realization and trace already cover this. |
| Attribution | Where did observed behavior originate? | Observation explicitly requires attribution across composition edges. |
| Provenance | Where did the governing knowledge, assumption, rule, or encoding come from? | Knowledge provenance is parked as an open question because maintaining it may cost more than it returns. |

These are **not five evidence types**, required fields, or a mandatory
checklist. “Learning evidence” is not a sixth peer: Learning consumes
evidence capable of changing what the engineering system believes or does.

Current research disposition:

- five-category ontology: **REJECT**;
- mandatory checklist: **REJECT**;
- overlapping evidence lenses: **RETAIN FOR RESEARCH**;
- conceptual-model change: **NOT JUSTIFIED**.

The critical test is whether asking one of these questions changes a
Convergence diagnosis beyond Observation. If a lens merely says “collect
telemetry,” “retain an audit trail,” or “write an ADR,” it duplicates
established observability, audit, and decision-record practice and adds no
Convergence value.

## 4. Three-case hostile test

### Case A — low-risk routine capability

A temporary development database uses known configuration and ordinary
authorization.

| Lens | Possible value | Hostile reading |
| --- | --- | --- |
| Outcome | Reveals provisioning success versus a usable database. | This is already outcome versus output / wrong-success. |
| Decision | Could show why eligibility was granted. | May add nothing when a settled rule already applies. |
| Realization | Can distinguish requested database from actual fulfillment. | Ordinary telemetry and the existing realization distinction may be enough. |
| Attribution | Can identify a failed contributor. | Adds little for a simple, single-owner path. |
| Provenance | Can identify the governing rule. | Adds little unless that rule is contested, stale, or consequential. |

The lenses must not produce a new record system for this case. If the
capability is usable and the known constraint was correctly enforced, extra
machinery is a cost, not evidence of maturity.

### Case B — governed cross-specialty capability

A production deployment crosses product, platform, identity, networking,
security, infrastructure, and delivery boundaries.

The lenses may expose local-success versus composite-outcome failure,
authority separated from execution, materially different realization paths,
attribution across composition seams, and stale encoded specialist knowledge.
But existing concepts already produce much of this: composition identifies
seams and non-transferred authority; Observation supplies attribution;
realization distinguishes a portal from fulfillment; Learning challenges stale
encoding. Decision and provenance add value only if they identify a governing
decision or assumption that changes what should happen next.

### Case C — novel human capability

A novel security/data architecture assessment uses unsettled knowledge.

Decision and provenance may remain useful because the responsible authority
needs to explain a bounded conclusion and later challenge its assumptions.
Detailed realization evidence may add little beyond recording that qualified
human judgment occurred. Over-attribution can distort collaborative reasoning
into a search for an individual cause. Outcome evidence may be delayed or
ambiguous. Human realization remains legitimate.

This is a case where a lens can add **no value** or cause harm: demanding
fine-grained realization or attribution records can turn necessary
collaboration into performative workflow.

## 5. Prior-art boundary

The concerns overlap heavily with observability and distributed tracing; SRE;
audit and accountability; architecture and decision records; systems
engineering; governance; and provenance and knowledge management.

This research does not claim that Convergence invented any of them. The
narrower possible synthesis/application contribution is:

> When unnecessary organizational coordination is removed from a delivery
> path, preserve the engineering properties that coordination was legitimately
> carrying at a level proportional to consequence and accountability.

This remains synthesis/application unless independent evidence later establishes
something stronger.

## 6. Concrete handoff-property analysis

The existing standard governed cloud-workspace case spans a product/consumer,
platform/cloud, identity, security/governance, networking, and CI/application
delivery path. The public-evidence case is a composite reconstruction, so
unknowns remain unknown.

| Handoff | Work transferred | Candidate carried property | Necessary? | Is the organizational interaction necessary? | How the property could survive a changed interaction |
| --- | --- | --- | --- | --- | --- |
| Consumer → platform/cloud | Request for standard workspace | Intent/context; baseline eligibility | Usually for the standard class | Often no; manual discovery and request routing may not be | Declared intent plus stated eligibility and baseline contract |
| Platform/cloud → identity | Identity attachment | Policy/constraint; execution | Often | Standard routing often no; novel mapping may require collaboration | Encoded identity rule, explicit exception route, realization evidence |
| Platform/cloud → networking | Standard connectivity | Constraint; domain authority | Often | Standard placement lookup may not be | Contracted network constraint; domain refusal or exception for novel placement |
| Consumer/platform → security/governance | Workload permission or risk decision | Expertise, authority, independent challenge, decision accountability | Varies | High-risk or unsettled cases may require human interaction | Bounded decision, recorded rationale where proportional, automated realization only within authority |
| Platform → CI/application delivery | Deploy path | Execution, outcome visibility, provenance of encoded standard | Often | Per-team reconstruction of settled CI usually no | Standard realization with observable outcome and challengeable encoding |

Candidate properties to test—not automatically accept—are intent/context,
translation, expertise, authority, policy/constraint, judgment, independent
challenge, execution, exception handling, decision accountability, provenance,
attribution, outcome visibility, and composite coherence.

The existing case supports treating manual lookup of settled rules, duplicate
context entry, queueing, and organizational routing as mechanisms with no
inherent engineering value. It does not support treating every handoff as
accidental. Security review of nonstandard permissions and novel architecture
may carry judgment and independent authority even when its intake path is
poorly realized.

## 7. Security exception counter-case

Consider a production workload needing a nonstandard third-party outbound
connection across a trust boundary, carrying sensitive data or credentials,
where settled rules do not currently reduce the case.

The following are **research distinctions, not a canonical taxonomy or
mandatory checklist.**

**Properties that may justify retaining human interaction:**

- unsettled judgment;
- independent domain authority;
- adversarial challenge;
- context discovery; and
- responsibility for defining a bounded exception.

These are reasons to keep human interaction, not reasons to preserve every
manual mechanism around it.

**Properties that may need to survive the interaction but do not themselves
require the interaction to remain human:**

- context;
- constraints;
- decision evidence;
- provenance;
- attribution;
- outcome visibility;
- accountability; and
- composite coherence.

The interaction may still shed organizational discovery, duplicate forms,
unnecessary queues, manual transcription, repeated translation of settled
decisions, and manual realization after the decision is made.

A useful result must be able to say: **keep the human judgment; remove the
accidental machinery around it.** If this analysis mechanically recommends
automation, it is biased and fails its own test.

## 8. Bounded human decision contract

Automating realization does not require automating judgment. Where judgment
should remain human, enough of its bounded result may be represented for the
engineering system to realize it without reinterpreting or expanding the
authority granted.

This is not a canonical Convergence YAML schema. A machine-actionable security
exception may need the following semantic properties only when consequence and
organizational distance justify them:

| Candidate property | Why it may be necessary | Reject when |
| --- | --- | --- |
| Durable exception identity | Correlates a decision, its realization, and later revocation or review. | A durable identifier adds no accountability or lifecycle value. |
| Intent | Prevents a grant from being read as authority for a different purpose. | The intent is already unambiguously bound elsewhere. |
| Subject | States who or what may rely on the decision. | It merely repeats an organizational routing field. |
| Baseline/control excepted | Makes the rule being varied challengeable. | There is no identifiable baseline. |
| Scope | Bounds action, resource, and relevant context so realization cannot silently expand authority. | Scope becomes a speculative inventory. |
| Decision | States disposition, authority, deciding principal where appropriate, and decision time. | It duplicates a workflow approval without changing reliance or accountability. |
| Conditions | Makes contingent permission enforceable or reviewable. | Conditions are boilerplate with no operational effect. |
| Validity | Supports not-before, expiration, revocation, or supersession where risk warrants it. | A lifecycle field outlives any meaningful decision. |
| Evidence correlation | Connects the bounded decision to later observations or realization evidence. | Correlation is retained solely for surveillance. |
| Accountability | Makes exception owner and domain authority discoverable. | It turns owner discovery into a mandatory routing path. |

Distinguish:

1. **Human decision record:** why the authority reached the conclusion.
2. **Machine-actionable bounded decision:** what automated realization is
   authorized to rely upon.
3. **Realization evidence:** what actually happened under that authority.

They need not be separate physical artifacts. Fields that merely encode
organizational workflow are rejected; the point is bounded reliance, not a new
approval engine.

## 9. Critical anti-ontology constraints

Reject unless corpus evidence strongly proves otherwise:

- every capability needs five evidence classes;
- every interaction needs an audit record;
- every exception needs the same schema;
- every human decision should become machine-readable;
- every handoff should be removed;
- every settled rule should be automated;
- every authority boundary requires an approval step;
- every piece of provenance must be retained forever;
- every realization must be traceable through one technical tracing system;
- OPA or any specific policy engine is required; or
- Kubernetes, GitOps, Backstage, IDPs, workflow engines, or agents are
  required.

The methodology remains implementation-neutral.

## 10. Falsification conditions

This direction should be rejected or reduced if:

- existing Convergence concepts produce the same decisions without this
  vocabulary;
- practitioners cannot reliably distinguish a property from its handoff
  mechanism;
- property analysis becomes a longer checklist;
- it consistently biases toward automation or self-service;
- it cannot identify cases where human organizational interaction should
  remain;
- evidence lenses merely rename existing observability or audit concepts
  without changing a Convergence diagnosis;
- bounded-decision representation adds machinery without changing authority,
  accountability, safety, or realization behavior; or
- independent practitioners find the distinctions confusing or irrelevant.

## 11. Research disposition

| Item | Disposition | Reason |
| --- | --- | --- |
| Evidence lenses | RETAIN FOR RESEARCH | May sharpen Observation questions; ontology and checklist forms are rejected. |
| Handoff-property hypothesis | RETAIN FOR RESEARCH | It may make “value versus delivery shape” more inspectable, but may duplicate interaction evaluation. |
| Handoff mechanism versus carried property | RETAIN FOR RESEARCH | Useful wording for a known control-with-routing problem; not a new concept. |
| Human-interaction-retention properties | RETAIN FOR RESEARCH | Existing doctrine already preserves authority and judgment; research must show added decision value. |
| Bounded human decision concept | RETAIN FOR RESEARCH | May operationalize authority/execution separation without automating judgment. |
| Machine-readable exception schema as methodology | REJECT | Contracts are proportional and non-mandatory; a universal schema would be invented bureaucracy. |
| Canonical conceptual-model change | INSUFFICIENT EVIDENCE | Paper analysis cannot justify a new node, ontology, or principle. |

No item may be promoted to canonical doctrine solely from this paper analysis.

## Sources / corpus position

This note is based on the current public corpus at
`origin/main` commit `760622ea73c8c2b28d083c0b7d08bcb1043c6257`.
At inspection time, local `main` had four commits not in `origin/main`, and
`origin/main` had one commit not in local `main`. That origin-only commit did
not touch the inspected corpus files. This note does not treat paper cases or
prior art as field validation.
