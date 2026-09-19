# Practitioner Validation Protocol — v1

*Preregistered exploratory validation protocol. Must be frozen before the first
practitioner begins.*

## 1. PURPOSE

This validation tests whether engineers who did not create Convergence can
independently apply its minimal reasoning method to the same real engineering
problem without author coaching, and whether the structure provides useful
reasoning value relative to the burden it introduces.

This four-person exploratory validation cannot establish:

- statistical effectiveness;
- superiority over ordinary Staff-level engineering reasoning;
- superiority over DevOps, SRE, Platform Engineering, systems engineering, or
  another methodology;
- causal improvement in engineering outcomes;
- correctness of the source organization's retrospective;
- correctness of Convergence as a general theory; or
- practitioner agreement as proof of truth.

## 2. PRIMARY RESEARCH QUESTION

Can an engineer who did not create Convergence use the minimal method on a
real engineering problem, without being coached toward the answer, and obtain
enough useful reasoning structure to justify the additional structure the
method introduces?

This protocol evaluates three dimensions without assuming any will occur:

1. **Independent usability:** Can the practitioner understand and apply the
   method without substantive author explanation?
2. **Incremental utility:** Does the practitioner identify a concrete way the
   structure improved, clarified, externalized, or added to reasoning relative
   to how they report normally approaching such a problem?
3. **Cost or distortion:** Does the structure introduce confusion, redundant
   work, forced categorization, premature framing, omitted reasoning, or false
   confidence?

## 3. PARTICIPANTS

Four independent practitioners will be sampled from these target perspectives:

- Staff Platform Engineer
- Staff SRE / Build Engineer
- Staff Product Engineer
- Staff Application / Development Engineer

These are sampling perspectives, not populations from which this study can
make specialty-level claims. With one participant per perspective, differences
between participants must not be attributed to their specialty as a causal or
generalizable conclusion.

Record actual title/role and relevant experience descriptively. Record prior
exposure to Convergence and prior exposure to the case if known.

## 4. INDEPENDENCE CONDITIONS

Before an analysis is frozen, a practitioner must not:

- see another participant's analysis;
- see research provenance;
- see held-back retrospective evidence;
- receive the author's diagnosis;
- receive suggested interventions;
- be told what another practitioner noticed;
- be told whether reasoning is correct;
- search for the original incident; or
- supplement the packet with external incident information.

For this v1 validation, practitioner analysis must be completed without
AI-generated analysis. Ordinary note-taking/editing tools are permitted.

If any condition is violated, record the deviation. Do not silently discard a
contaminated result.

## 5. MATERIALS

Each practitioner receives exactly:

A. The minimal operational method:

```text
Scope -> Trace -> Diagnose -> Intervene -> Observe
```

B. The frozen practitioner evidence packet:

`drafts/research/delayed-content-publishing-practitioner-exercise.md`

The frozen case commit is
`d39cc1015e77fab4aa0bcce8ee3751832cb99e8a`.

Do not provide:

- provenance;
- held-back evidence;
- broader Convergence theory;
- canonical examples that reveal expected reasoning; or
- another participant's analysis.

## 6. MINIMAL METHOD PRESENTATION

### Scope

State the engineering outcome being examined and the boundaries relevant to it.

### Trace

Trace how that outcome is actually realized through the available evidence.

### Diagnose

Identify where the engineering system appears to create friction, uncertainty,
failure, or risk. Distinguish observations from hypotheses and identify missing
evidence.

### Intervene

Identify the smallest justified intervention, including no change where
appropriate. Do not assume automation, self-service, platform work,
organizational change, or any particular technical solution is required.

### Observe

State what evidence would indicate whether the intervention improved the
intended outcome, including what evidence could make an intervention appear
successful without demonstrating improvement in the intended outcome.

### Evaluation boundary

Because these behaviors are explicitly elicited by the method instructions,
their appearance in practitioner output must not later be characterized as
spontaneous discovery.

They may provide evidence about:

- whether the move is independently usable;
- how the practitioner interprets it;
- the quality or usefulness of the resulting reasoning; and
- whether the practitioner reports that the prompt caused reasoning they
  normally would not have externalized or performed.

Do not count instructed behavior itself as evidence of incremental discovery.

## 7. PARTICIPANT INSTRUCTIONS

"You are being asked to independently analyze an engineering problem using a
small reasoning method.

There is no expected diagnosis or preferred technical solution.

Use only the evidence provided. Treat information that is not provided as
unknown rather than inventing it.

Work through:

Scope -> Trace -> Diagnose -> Intervene -> Observe

Record your reasoning in your own language. You do not need to reproduce the
terminology of the method.

If the method is unclear, record what is unclear. Do not try to infer what the
author intended you to say.

If information is missing that would materially affect your analysis, record
what information you would want and why.

An intervention may be technical, operational, organizational, procedural, or
no change at all. Do not assume that automation, a platform, self-service,
reorganization, or additional tooling is desirable.

For anything you would change, state what evidence you would use afterward to
determine whether the intended engineering outcome actually improved.

Do not search for the original incident or use outside information.

Complete the analysis independently. You will be asked about the method only
after your analysis has been frozen."

## 8. AUTHOR-COACHING BOUNDARY

Procedural clarification concerns how to participate without directing the
substance of the analysis. Substantive coaching directs or shapes the analysis.

Permitted procedural responses include:

- "Record that as an unknown."
- "If the wording is confusing, record that it is confusing."
- "Use your own terminology."
- "There is no required number of diagnoses or interventions."

Prohibited substantive coaching includes:

- directing attention to a particular timeline event;
- suggesting a diagnosis;
- suggesting an intervention;
- introducing Convergence concepts not in the minimal method;
- asking leading questions about intentional versus accidental friction;
- prompting capability naming;
- prompting Experience versus Realization;
- prompting authority versus execution;
- suggesting what successful observation should look like; or
- telling the practitioner what another participant noticed.

Record every substantive clarification or coaching event. If substantive
coaching materially affects the analysis, that result cannot support the
independent-usability claim. Do not delete the result.

## 9. CAPTURED PRACTITIONER OUTPUT

Capture the practitioner's own analysis under the following headings.

### Scope

- intended engineering/user outcome;
- analysis boundary; and
- assumptions.

### Trace

- reconstruction of how the outcome is realized;
- relevant events/dependencies/transitions; and
- uncertainties and missing evidence.

### Diagnose

- observations;
- hypotheses;
- evidence supporting distinctions; and
- missing information that could change diagnosis.

### Intervene

For each intervention:

- proposed change;
- reason;
- problem addressed;
- tradeoffs/risks; and
- evidence needed before acting.

"No intervention yet" is valid.

### Observe

For each intervention:

- expected observable result;
- evidence indicating improvement;
- evidence challenging the intervention; and
- evidence that could look successful without demonstrating improvement in the
  intended outcome.

Allow free-form material for reasoning the structure does not capture.

## 10. PROCESS METADATA

Record:

- practitioner identifier;
- actual engineering role/title;
- target sampling perspective;
- approximate relevant experience;
- prior familiarity with Convergence;
- prior familiarity with similar reasoning methods;
- prior familiarity with or recognition of the source incident;
- start time;
- completion time;
- questions asked;
- author responses;
- interruptions;
- protocol deviations;
- whether substantive coaching occurred; and
- whether analysis was completed independently.

Elapsed time is descriptive only. Do not treat faster completion as better.

## 11. FREEZE POINT

Freeze the practitioner's original analysis before:

- substantive discussion with the author;
- post-analysis questioning;
- seeing another participant's analysis;
- seeing provenance; or
- seeing held-back retrospective evidence.

Preserve the original artifact unchanged. Any later additions must be
explicitly marked as post-analysis material.

## 12. POST-ANALYSIS QUESTIONS

Use neutral questions and fixed ordering. Ask exactly:

1. How, if at all, did using this structure affect the way you approached the
   problem?

2. Which parts of the structure, if any, were useful to you? What made them
   useful?

3. Which parts, if any, were not useful to you? What made them not useful?

4. Was any part unclear or difficult to apply? If so, describe it.

5. How did this approach compare with how you would normally analyze a problem
   like this?

6. Did the structure cause you to include, exclude, emphasize, or de-emphasize
   anything compared with your normal approach? If so, what?

7. Did using the structure change any question, uncertainty, diagnosis,
   intervention, or observation criterion you would otherwise have produced? If
   so, describe the specific change.

8. Did the structure make any part of your reasoning harder, less precise, or
   less useful? If so, how?

9. Was there reasoning you wanted to include that did not fit naturally into
   the structure?

10. If you encountered a similar problem tomorrow, which parts of this
    structure, if any, would you deliberately use?

11. What, if anything, would you remove, change, or add?

12. What conclusion, if any, did you think the method was encouraging you to
    reach?

Do not add follow-up questions that steer toward a Convergence concept. Neutral
clarification of a participant's own answer is allowed. Record such follow-ups.

## 13. SOURCE-RECOGNITION CHECK

Before revealing the source, ask:

"Did you recognize or suspect the real incident represented by this exercise?"

If yes, ask:

"When did you recognize it, and what did you already know about it?"

Record the response before source disclosure.

Source recognition does not automatically invalidate the entire result. Prior
knowledge that exposes held-back causes or remediation contaminates the result
for source-blind diagnostic comparison and must be recorded.

## 14. RETROSPECTIVE COMPARISON

Only after:

- practitioner analysis is frozen;
- post-analysis questions are complete; and
- source-recognition check is complete.

Then the source retrospective may be compared. The retrospective is not an
answer key.

Compare:

- practitioner findings also present in retrospective;
- practitioner findings absent from retrospective;
- retrospective findings absent from practitioner analysis;
- differences explained by evidence intentionally withheld;
- practitioner hypotheses that remain plausible;
- practitioner claims unsupported by available evidence; and
- retrospective claims that are interpretations rather than observations.

Agreement is not automatically success. Disagreement is not automatically
failure.

## 15. CROSS-PARTICIPANT COMPARISON

After all four analyses are frozen, compare:

- problem scope;
- system trace;
- evidence discipline;
- information requests;
- diagnoses;
- proposed interventions;
- intervention restraint;
- observation criteria;
- method usability;
- method redundancy;
- participant-reported incremental reasoning;
- method-induced confusion;
- method-induced distortion;
- reasoning that did not fit the structure; and
- perceived steering.

Participant differences may be described. Do not infer that a difference was
caused by engineering specialty. Do not rank practitioners. Do not score
terminology fidelity. Do not treat agreement as inherently better than
disagreement.

For behavior directly requested by the method, such as producing observation
criteria or considering apparent success that does not demonstrate outcome
improvement, evaluate usability and resulting reasoning. Do not describe the
existence of that behavior as independent discovery caused by Convergence.

## 15A. OPERATIONAL DEFINITIONS FOR DECISION RULE

### Recognizable application of all five moves

A practitioner has completed a recognizable application when the frozen
analysis contains an identifiable attempt at each of:

- Scope: states an intended outcome and an analysis boundary;
- Trace: reconstructs at least part of how the outcome is realized from the
  supplied evidence;
- Diagnose: identifies at least one observation, uncertainty, problem, risk,
  or hypothesis grounded in the supplied evidence;
- Intervene: explicitly proposes an intervention, explicitly defers
  intervention pending additional evidence, or explicitly concludes that no
  intervention is currently justified; and
- Observe: identifies evidence that would be used to evaluate the proposed,
  deferred, or no-change decision.

Terminology fidelity is not required.

Analytical correctness is not required for this classification.

A weak application may still be recognizable.

This classification measures whether the move could be independently applied,
not whether the researcher agrees with the result.

### Concrete incremental benefit

A concrete incremental benefit exists only when, during the fixed
post-analysis questions, the practitioner identifies a specific example of
reasoning that using the structure:

- added;
- clarified;
- externalized;
- reorganized in a useful way; or
- caused them to examine differently

relative to how they report they would normally approach the problem.

A generic positive statement such as:

- "it was useful";
- "I liked it";
- "it was structured";
- "it seems good"

does not qualify without a specific example.

Behavior that merely satisfies an explicit participant instruction does not
qualify by itself.

The classification is based on the practitioner's recorded post-analysis
account, not the researcher's inference that the method must have helped.

### Method-induced distortion

A method-induced distortion is a specific instance where the practitioner
reports, or the frozen analysis directly demonstrates, that use of the
five-move structure:

- introduced an assumption not supported by the evidence;
- prematurely constrained the problem framing;
- suppressed or displaced reasoning the practitioner considered materially
  relevant;
- created unjustified confidence;
- created pressure to recommend an intervention despite insufficient
  evidence; or
- materially reduced the precision or usefulness of the analysis.

Mere disagreement with the researcher, another practitioner, or the source
retrospective is not distortion.

A diagnosis that later differs from the source retrospective is not distortion
by itself.

### Materially similar distortion

Distortions are materially similar only when they concern the same method move
or the same underlying mechanism of distortion.

Broad labels such as "confusing" or "different reasoning" are insufficient by
themselves to classify two distortions as materially similar.

When similarity is ambiguous, classify it as NOT ESTABLISHED rather than
combining the observations.

Record the underlying observations used to make the similarity determination.

### Most participants

For this four-practitioner v1 validation:

"most participants" means at least 3 of 4 practitioners.

Do not reinterpret this phrase after results are observed.

## 16. PRE-REGISTERED DECISION RULE

This is a research decision rule, not a practitioner score and not a
statistical effectiveness measure.

Classify the v1 result into one of three research dispositions.

### CONTINUE UNCHANGED

Use only if all are true:

- at least 3 of 4 practitioners complete a recognizable application of all
  five moves without substantive author coaching;
- at least 2 of 4 practitioners identify at least one concrete incremental
  benefit attributable, in their own post-analysis account, to using the
  structure rather than merely complying with an explicit instruction; and
- no materially similar method-induced distortion appears independently in 2
  or more practitioner results.

### REVISE BEFORE FURTHER VALIDATION

Use when independent usability is substantially present, but:

- incremental value is weak, mixed, or primarily redundant with existing
  reasoning; or
- materially similar confusion, redundancy, or distortion appears in 2 or more
  results; or
- a part of the method is interpreted inconsistently enough to require
  clarification.

### CURRENT FORMULATION FAILS THIS VALIDATION

Use if any are true:

- fewer than 3 of 4 practitioners can complete a recognizable application of
  the five moves without substantive author coaching;
- substantive author coaching is necessary for most participants to apply the
  method; or
- materially similar method-induced distortion appears in 3 or more
  practitioner analyses.

Do not convert these thresholds into percentages or claims of statistical
effectiveness.

If an unforeseen result does not fit these dispositions cleanly, report it as
an unresolved result rather than changing the decision rule after seeing the
data.

## 17. NEGATIVE / FALSIFYING OUTCOMES

Explicitly preregister these as evidence against the current formulation.

### A. Independent application fails

Repeated substantive author explanation is needed to apply the method.

### B. No identifiable incremental value

Practitioners report that the structure largely renames reasoning they already
perform and cannot identify concrete additional utility.

Do not reinterpret "experts already think this way" as evidence of incremental
practitioner value.

### C. Premature framing

The method causes practitioners to force unavailable evidence into expected
organizational, capability, coordination, self-service, platform, or other
Convergence-shaped interpretations.

### D. Specialty reasoning is obscured

Useful practitioner reasoning is suppressed or made harder because it does not
fit the five moves.

### E. False confidence

The completed structure causes weak hypotheses or missing evidence to appear
more certain than justified.

### F. Observe becomes ceremonial

Practitioners can populate Observe but the resulting evidence would not
meaningfully distinguish outcome improvement from activity, recovery, or local
success.

Because Observe explicitly requests this reasoning, this tests the usefulness
and quality of the move, not spontaneous discovery.

### G. Intervene creates solution pressure

Practitioners feel compelled to recommend changes despite insufficient evidence
or are systematically pushed toward automation, platformization, self-service,
tooling, or reorganization.

### H. Structure obscures rather than clarifies

Practitioners consistently report that mapping their reasoning into the five
moves makes it less precise or useful.

### I. Results depend on author involvement

Useful application primarily occurs after author explanation or redirection.

### J. Source leakage

Prior source knowledge explains reproduction of held-back findings.

### K. Method operations have no stable shared meaning

Conclusions may differ, but if practitioners interpret Scope, Trace, Diagnose,
Intervene, and Observe so differently that the moves do not provide a
recognizable shared reasoning structure, the method is underspecified.

## 18. INTERPRETATION BOUNDARIES

Do not reduce the four practitioners to an effectiveness score.

Do not claim:

- Convergence is proven;
- Convergence is validated generally;
- Convergence produces better engineers;
- Convergence produces better diagnoses;
- Convergence is superior to another methodology;
- Convergence caused better engineering outcomes;
- specialty differences observed here generalize to those specialties;
- agreement proves truth; or
- disagreement proves failure.

Distinguish:

- independent-usability evidence;
- participant-reported incremental-utility evidence;
- redundancy evidence;
- cost/confusion evidence;
- distortion evidence; and
- source-retrospective comparison.

Multiple evidence types may coexist in the same practitioner result.

"I already reason this way" is legitimate data.

## 19. PREREGISTRATION FREEZE RECORD

Before Practitioner #1 begins, record:

- protocol version;
- protocol commit SHA;
- frozen practitioner-case commit SHA;
- exact minimal-method presentation;
- exact practitioner instructions;
- participant inclusion criteria;
- intended four sampling perspectives;
- post-analysis questions;
- comparison dimensions;
- decision rule;
- negative/falsifying outcomes;
- author-coaching definition;
- source-recognition handling; and
- known protocol deviations, if any.

This uncommitted v1 protocol has no protocol commit SHA. Record its commit SHA
before Practitioner #1 begins.

Any methodological change after Practitioner #1 begins must be versioned and
disclosed. Do not silently revise v1 in response to observed results.

## 20. RESEARCHER DEGREES OF FREEDOM

The researcher must not, after seeing results:

- redefine "independent";
- redefine substantive coaching;
- redefine concrete incremental benefit;
- redefine recognizable application;
- redefine materially similar distortion;
- redefine most participants;
- change the 3-of-4 or 2-of-4 thresholds;
- introduce new success criteria;
- remove preregistered negative outcomes;
- reinterpret directly instructed behavior as spontaneous discovery;
- discard inconvenient participants without documenting why;
- attribute individual differences to specialty without additional evidence;
- treat the source retrospective as an answer key; or
- silently alter the practitioner packet or method between participants.

Unexpected observations may be reported as exploratory findings but must be
clearly distinguished from preregistered outcomes.
