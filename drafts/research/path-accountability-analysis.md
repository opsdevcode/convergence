# Path accountability — analysis against the existing corpus

*Non-canonical research note. Not part of the body of knowledge. Does not edit,*
*rename, or extend the canonical corpus. No new theory, roles, principles,*
*lifecycle stages, or names are proposed here.*

**Question under test.** Who — or what — owns the path from intent to outcome
when no single team should own all of its realization?

This note reads the canonical corpus as the source of truth (the frozen v0
essay is treated as prose, not authority) and tests whether the theory already
answers the question before anyone decides it needs changing.

Primary sources consulted: `conceptual-model.md`, principles 2, 5, 6,
`design-doctrine.md`, `composite-capabilities.md`, `03-architecture/composition.md`,
`ownership-and-authority.md`, `output-and-outcome.md`, `organizational-independence.md`,
`03-architecture/observation.md`, `coordination-and-collaboration.md`,
`federation.md`, `learning.md`, `08-anti-patterns/convergence-as-a-function.md`,
`open-questions.md`.

## 1. The apparent tension

The essay diagnoses "no one owns the traversal": optimizing each team or
capability locally does not optimize the end-to-end path. Yet the corpus
deliberately preserves distributed specialization, domain authority, capability
ownership, outcome ownership, federation, and local autonomy — and explicitly
rejects a central path/journey/orchestration owner
(`convergence-as-a-function.md`). On the surface these pull against each other:
someone must be accountable for the whole, but nothing is allowed to own the
whole.

## 2. What the existing corpus already says

The relevant machinery already exists and is more complete than the essay's
"no one owns the traversal" phrasing implies. The corpus does not model the path
as a chain of independently-owned steps. It models it as a **composite
capability**, and it assigns that composite a distinct accountability.

From `composition.md`, composition **transfers**:

- the obligation to satisfy the consumer's intent;
- accountability for the **composite's own coherence**;
- the relevant constraints of every contributor;
- **responsibility for the seams between contributors**.

And composition explicitly **does not** transfer:

- authority over the contributing domains;
- ownership of the contributing capabilities;
- privilege to bypass contributor constraints;
- domain expertise, which stays where it lives.

So the theory already contains "ownership of the whole without ownership of the
parts": the composite owner owns the composite's coherence and its seams, and
holds none of the contributors' domain authority. The composite is exactly "the
engineering system scoped to a class of intent moving toward an outcome" — the
already-stated unit of reasoning (`conceptual-model.md`, Principle 2,
`federation.md`).

Three further pieces matter:

- **Legitimate levers without domain authority.** When contributors conflict,
  `composition.md` gives the composite owner exactly four honest moves: *refuse
  to compose*, *narrow the composite's contract*, *route to an exception path*,
  and never *promise the union*. These change the composition without seizing
  authority over any contributing domain.
- **Evidence with attribution.** `observation.md` routes composition failures
  along the composition edge to the composite owner "with attribution," and
  distinguishes attribution the structure needs from exposure the consumer does
  not. It also insists silence isn't health, and that conversation and
  unemitted signals count.
- **Stewardship at the scope of the concern.** `open-questions.md` states
  "stewardship should exist at the level where the concern exists," and
  `federation.md` makes the whole model recursive: the composite/path exists at
  team, domain, enterprise, or federation scope, coherent at boundaries without
  one homogeneous authority.

## 3. A worked hostile enterprise example

A customer can submit a claim. The outcome depends on a composed path:

Product → Identity → Network → Infrastructure → Security → Platform →
Reliability.

Stipulate the hard case: every contributing capability works, meets its own
expectations, has a clear owner and valid domain authority, is well designed,
and is adequately funded and stewarded.

The composition is still bad end-to-end: latency stacks up across handoffs;
Identity's token model and Network's segmentation encode **incompatible
expectations**; Security and Platform both perform an overlapping check
(**duplicated work**); the product engineer gets a **poor experience** and must
carry context between contributors (**unnecessary coordination**). No
contributor has failed its own contract. The *composite* has failed its
coherence and its seams — precisely the thing `composition.md` says is owned,
and the thing that has no owner if the path was never modeled as a composite.

This is the crux: the failure is real, it is nobody's local fault, and whether
it has an accountable home depends entirely on whether the path exists as an
**owned composite** or only as an **implicit, unowned chain**.

## 4. Where accountability currently lands

- **Recognition** lands on **outcome ownership**: the outcome owner is
  accountable for "the result closest to the intent," so the degraded end-to-end
  result is theirs to notice and to own as a bad result.
- **The composite's coherence and seams** land on **composite ownership** (the
  owner of the composed capability), per `composition.md`.
- **Each contributor's internal correctness** stays with that contributor's
  **capability owner** and **domain authority**.
- If the path is an implicit chain that no one has modeled or owned as a
  composite, seam-level accountability has **no home by default** — which is
  `observation.md`'s "owner named or the loop is drawn in the diagram and broken
  in practice," applied to the composition rather than to a leaf capability.

## 5. Where authority currently lands

- **Domain authority** (what is correct in Security, Identity, etc.) stays with
  each contributing domain and is **not** transferred upward. Composition "must
  not silently expand authority."
- **Authority to change the composition** is the composite owner's, but only at
  the seam: narrow, refuse, route-to-exception, adjust the composite contract.
- **Authority to change a contributor's internals** remains with that
  contributor. The composite owner can supply attributed evidence; it cannot
  overrule a domain.
- Nothing grants anyone authority over *all* contributing domains, by design
  (`convergence-as-a-function.md`).

## 6. How system-level evidence / learning propagates

`observation.md` is explicit: composition failures originate at the composition
edge and reach the composite owner with attribution; failures/incidents reach
the contributing capability owner *and* domain authority; security/regulatory
evidence enters "from outside the loop entirely" to domain authority, then
capability owner. `learning.md` allows evidence to change definitions,
contracts, experiences, realizations, **composition**, policy, and ownership.

The honest limit is stated in both `observation.md` and Principle 6: **learning
informs change; it does not mandate it.** The structure can make system-level
failure explicit and attributable so that *not acting is visible as a decision*.
It cannot force the contributing owner to accept a change.

## 7. Is Outcome Ownership sufficient?

Partly. Outcome ownership is **sufficient for recognition** — it gives the bad
end-to-end result an accountable home. It is **not sufficient for remedy**: the
outcome owner has no domain authority over contributors and no inherent
authority over the composition unless they also hold composite ownership. Their
non-hand-wavy levers are: consume via the composite and use its seam levers (if
they own it), route to an exception path, and inject attributed system-level
evidence into the loop. Beyond that, remedy depends on contributors acting on
that evidence — which is not guaranteed.

## 8. Is Capability Ownership sufficient?

Capability ownership answers accountability for each *node's* fitness, and — via
**composite** capability ownership — for the composed path's coherence and
seams. It is sufficient **only if the composed path is actually modeled and
owned as a composite**. It does **not** "compose upward" automatically:
`composition.md` says ownership of contributors is *not* transferred to the
composite; instead composition creates a *new, distinct* ownership locus for the
composite. Sufficiency therefore hinges on that locus being filled.

## 9. Does composition create an accountability gap?

Not conceptually — the corpus defines exactly what a composite owner is
accountable for (coherence, seams, contributor-constraint coexistence). The gap
is **organizational and conditional**: it appears precisely when a cross-domain
path exists as an emergent chain that no one has recognized, named, or owned as
a composite. In that state, the corpus's own rule applies — an unowned composite
means the loop is broken in practice — but the theory does not compel the
emergent path to acquire an owner, and it does not resolve who is *incentivized*
to become that owner when the cost lands on one contributor and the benefit is
spread across many. That second half is already parked as **incentive
compatibility** and **system-level stewardship (organizational implementation)**
in `open-questions.md`.

## 10. Is "the path" already represented, or a genuinely missing concept?

Already represented. "The path" is plain-English shorthand for **a composite
capability scoped to a class of intent** — equivalently, "the engineering system
scoped to a class of intent moving toward an outcome," which is the stated unit
of reasoning. Composite ownership already *is* path accountability; the
narrow/refuse/route levers already *are* the way to change a path without
seizing domain authority; observation-with-attribution already *is* path-level
evidence. "The path" does **not** appear to be a missing construct. What is
missing is not a concept but the assembly of these pieces into a clear statement,
plus the two already-parked organizational questions. Turning "path" into a new
formal construct would risk manufacturing the very central path-owner the corpus
rejects.

## Answers to the 12 sub-questions (condensed)

1. **Who recognizes the failure?** Outcome ownership (owns the degraded result);
   observation is what surfaces it.
2. **Who can change the composition?** The composite owner, at the seam
   (narrow / refuse / route / fix seams) — not domain internals.
3. **Does outcome ownership answer it?** For recognition, yes; for remedy, no.
4. **How does an outcome owner improve the path without domain authority?** Only
   via seam levers (if they own the composite), exception routing, and injecting
   attributed evidence; internal contributor change still needs the contributor.
5. **Does capability ownership compose upward?** No. Composition creates a new
   composite-ownership locus; it does not transfer contributor ownership upward.
6. **Can locally-correct capabilities compose into a globally-bad system?** Yes,
   explicitly ("safety of parts does not guarantee safety of the composition").
7. **Where does emergent failure live?** With the composite owner (coherence +
   seams) — or nowhere, if the composite is unowned.
8. **Optimize the path without a central path owner?** Yes — composite ownership
   is scoped, recursive, and federated; it owns seams, not domains.
9. **What must be observable?** Composition-edge failures with attribution
   (which contributor, which owner can act, composite-vs-part fault) without
   consumer exposure; plus abandonment, semantic drift, and conversation.
10. **How does composed-level learning reach contributors?** Via attribution
    along composition edges to composite owner, capability owner, and domain
    authority; it informs but does not mandate.
11. **Who authorizes a locally-worse / globally-better trade?** *Unresolved.* The
    corpus requires incentive compatibility but prescribes no mechanism; no
    element is granted authority to force a contributor to accept a worse local
    metric for a better system outcome.
12. **Are the concepts distinct?** Yes, and without needing five roles:
    capability ownership (a node's/composite's fitness), outcome ownership (the
    result nearest intent), stewardship of a composition (= composite ownership
    of coherence/seams), domain authority (what is correct in a domain), and
    system optimization (Principle 2's unit + design doctrine) are distinct
    accountabilities that one team may hold in combination.

## Adversarial tests

**A. Centralization — passes.** The answer never creates authority over every
contributing domain. Composite ownership owns seams and coherence, not domains;
it is scoped and recursive. The centralized version is exactly the rejected
`convergence-as-a-function.md` anti-pattern.

**B. Accountability without authority — present, and named explicitly.** The
outcome owner is accountable for a result they cannot unilaterally fix; the
composite owner can act at the seam but not inside a contributor. The corpus's
non-hand-wavy answer is seam levers plus attributed evidence — *not*
"collaborate harder." The honest residue: when remedy requires a contributor to
change internally, the composite/outcome owner has evidence but not authority,
and action depends on the contributor. This is the sharpest surviving condition.

**C. Shared accountability — passes.** The corpus does not say "everyone owns the
outcome." Outcome ownership is singular ("the result closest to the intent");
composite ownership is a distinct singular locus; "shared contribution does not
require shared accountability" holds. Accountability stays explicit.

**D. Local optimization — system can still fail, and the theory explains the
propagation but not the enforcement.** Evidence flow (observation → learning)
is the mechanism by which local targets *could* change; the theory concedes it
cannot guarantee they *will*. The enforcement half is the parked incentive
question.

**E. Federation — passes.** The same reasoning runs at team, domain, enterprise,
and cross-organization scope. Composite ownership and coherence-at-boundaries do
not require one authority above everything; `federation.md` is explicit that no
coordinating body is required.

**F. Regulation — passes strongly.** A contributor whose independent authority
exists to resist delivery pressure is preserved: composition cannot expand or
override authority, and the honest responses are narrow / refuse-to-compose /
route-to-exception — never override. "Converge where outcomes require coherence;
preserve autonomy where they don't" protects exactly this.

**G. Economics — unresolved, and it is the same residue as B/D/11.** Cost in
Team A, benefit across B–Z, maps directly to the essay's stewardship/funding
concern and to the parked **incentive compatibility** and **system-level
stewardship** questions. The corpus states incentive compatibility is *required*
and deliberately prescribes no budgeting/chargeback/role.

## 11. Strongest argument AGAINST adding any new theory

The literal question is already answered by existing constructs used together:
composite capability (the path), composite ownership (accountable for coherence
and seams), the narrow/refuse/route levers (change without seizing authority),
observation-with-attribution (path-level evidence), and stewardship-at-scope
(recursive, federated, non-central). Adding a "path owner," "journey owner," or
any new construct would (a) duplicate composite ownership, (b) risk becoming the
centralized authority the corpus explicitly rejects, and (c) convert a
plain-English word ("path") into a formal element the model does not need. The
remaining unknowns are already correctly filed as open questions, not as holes
in the conceptual model.

## 12. Strongest argument FOR adding something

The strongest case is not for new *theory* but for the fact that the answer is
currently **latent and distributed** across five documents, while the most
natural description of the failure ("no one owns the traversal") points readers
away from it. Two conditions genuinely lack a resolved answer, not merely a
clearer one:

- **Emergent, unowned compositions.** The theory says an unowned composite
  breaks the loop, but nothing compels an emergent cross-domain path to *acquire*
  an owner at the right scope. Recognition of the composite is currently assumed,
  not caused.
- **Trade authority under misaligned incentives.** Nothing in the model gives
  anyone legitimate authority to make Team A accept a worse local metric for a
  better system outcome. The model requires incentive compatibility and stops
  there.

A minimalist could argue these two justify a small clarification (not a new
concept) about how a composition acquires an owner and how cross-level trades
are legitimated.

## 13. Final verdict

**B. Existing theory answers it but needs clarification.**

The structural question — who/what owns the path when no team owns all
realization — is answered: **the composite capability is the path, and composite
ownership is path accountability** (coherence + seams), wielding
narrow/refuse/route levers and attributed observation, at the scope where the
concern exists, without acquiring domain authority and without a central owner.
The concepts are distinct and non-contradictory, so this is neither a genuine
missing concept (C) nor a contradiction (D), and it is more than A because two
adjacent questions remain genuinely open.

**Smallest conceptual issue that would need resolution (not to be fixed now):**

> The corpus never states plainly that *the end-to-end path is a composite
> capability and that composite ownership already is path accountability.*
> Once that is said, the only genuinely unresolved residue is **not conceptual
> but organizational/economic** — (a) how an emergent, currently-unowned
> cross-domain composition acquires an owner at the right scope, and (b) what
> legitimates a locally-worse / globally-better trade across independent
> domains. Both are already parked as *system-level stewardship (organizational
> implementation)* and *incentive compatibility* in `open-questions.md`. The
> smallest resolution is a clarification that names composite ownership as the
> home of path accountability and points the residual — explicitly — at those
> two existing open questions, rather than introducing any new owner, role, or
> construct.

## Recurring natural language (observations only — not name proposals)

Language that surfaced repeatedly while reasoning about this, recorded as
observations, not candidates:

- path
- traversal
- composition / composed path
- seam / seams
- coherence
- composite owner / composite ownership
- scope
- attribution
- stewardship
- trade / trade-off
- emergent (failure, composition)
