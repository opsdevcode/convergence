# Your Org Chart Shouldn't Be Your Software Delivery API

*Draft essay — brand-neutral. Not part of the canonical body of knowledge.*

A product team wants to ship a customer-facing feature. The work is understood.
Nobody needs to invent anything. And it still takes six weeks.

If you have worked in a large engineering organization, you already know why,
and it probably isn't the reason your postmortem will name. The feature wasn't
hard. The system that had to build it was an organization, and the product team
had to traverse that organization by hand.

This essay is about that traversal — why it happens even in organizations that
did everything the last fifteen years told them to do, and what a better default
looks like. It is not an argument against specialists, teams, ownership, or
governance. It is an argument about what your teams should be an interface *to*.

## Specialization is not the problem

Start by saying the thing that too many "modern engineering" arguments skip:
deep specialization is correct.

Modern software outgrew what any single team can hold in its head. Networking,
identity, runtime platforms, data stores, threat models, and production failure
modes each grew deep enough to justify people who do only that. The results were
real. Cloud engineering turned capacity into something you provision in hours.
Security engineering lowered the cost of getting a whole class of decisions
wrong. Site Reliability Engineering brought error budgets, toil reduction, and
incident learning into places that used to treat "operations" as a lower caste.
DevOps attacked the wall between writing software and running it. Platform teams
tried to keep every product team from reinventing pipelines and environments.

None of that was a mistake. The people who hold that expertise are not a
bottleneck by virtue of existing. They are the reason the system works at all.

So this is not a "generalists win" essay, and it is emphatically not "everyone
should be full-stack." The specialists should stay specialized. The question is
narrower and, I think, more interesting: **when a specialist's knowledge is
already settled, what should the rest of the organization have to do to use it?**

## How the org chart quietly becomes an API

Here is the part that bites mature organizations specifically.

Take a product team that wants to expose a new customer workflow. To the
customer this is one thing: the feature either works or it doesn't. Inside the
company, that one thing gets decomposed into a supply chain:

- Product engineering designs the workflow and the application changes.
- Someone files for an environment, a namespace, or a cloud account.
- Networking is asked for connectivity, DNS, certificates, or firewall changes.
- Identity is asked for roles, tokens, or group mappings.
- Security is asked to review the design, the exceptions, or the scan results.
- A platform or DevOps team is asked for a pipeline or a deployment pattern.
- Reliability shows up after launch, or during the first incident.

Every one of those steps can be justified. And every one of them is also a
**handoff** — a ticket, a queue, an approval, a meeting, or a Slack thread
written in the private dialect of a particular team. The delivery time for the
customer's one outcome becomes a function of how many of these internal human
APIs the work has to pass through, and how well the product team can navigate
each one.

Now notice what does *not* fix this.

You can have CI/CD, infrastructure as code, a real platform team, cloud
automation, a security tooling budget, and an org chart drawn straight out of a
Team Topologies workshop — and still have exactly this path. I've watched it
happen. Each specialist team can be individually excellent. Each can be hitting
its SLA. The cloud team provisions accounts fast. The security team clears
reviews inside its stated window. The platform team closes its portal tickets.
Everyone's dashboard is green.

And the end-to-end path is still slow, because *no one owns the traversal.* The
product team is the only party experiencing the whole sequence, and its job in
that sequence is to be a courier — carrying context from one queue to the next,
re-explaining the same system to each team in that team's preferred format.

This is the gap between **local optimization** and **system effectiveness**. A
cloud team measured on provisioning time, an SRE team measured on incident
metrics for systems it didn't design, a platform team measured on tickets
closed, a product team measured on feature output — every one of those can be at
a local optimum while the path from a customer need to a customer outcome is
slow and fragile. Optimizing the parts is not the same as optimizing the path,
and the two can diverge for years without anyone being wrong at their own desk.

Worth being fair about history here: the two dominant responses to this didn't
fail for the reasons people usually give. DevOps didn't stall because automation
is bad; it stalled where "you build it, you run it" collided with specialized
controls that *still had to be requested by ticket.* Platform engineering didn't
stall because developer experience is bad; it stalled where the platform became
a nicer front door to the same queues — more buttons, same supply chain. If your
portal's main function is to open a ticket, you have improved the waiting room,
not the path.

## The reframe

Here is the shift I want to argue for.

For work the organization already understands, a team should primarily depend on
**what the engineering system can reliably accomplish**, not on **which part of
the organization is currently responsible for accomplishing it.**

Those sound similar. They are not. Today, in most large shops, the interface to
"get a database" is *the database team* — its intake form, its queue, its
conventions, its calendar. The interface to "get through security review" is
*the security team.* The unit you consume is an org box. The reframe says: the
thing you consume should be the accomplishable result — durable relational
storage that meets policy; an assessed and cleared design — and the org box
behind it should be something you can look up, not something you have to
assemble.

It helps to name one distinction and then get out of the way of it: the
difference between **what** the system can do and **how** it currently does it.

"Provide durable relational storage that satisfies our data-class rules" is a
*what*. It stays stable across years. The *how* — a DBA provisioning by hand,
Terraform against a managed cloud service, an internal platform, an external
provider, human approval plus automation — changes constantly, and *should* be
free to change, owned by the people with authority over that domain. When a
consumer's interface is welded to the *how*, every change in fulfillment
ripples out as relearning for everyone downstream. When the interface is the
*what*, the specialists can re-engineer the *how* underneath without dragging
the whole company through it.

I want to be careful about one word before it runs away from us. When I say the
thing you consume, I don't mean an API, a service, a portal button, or an
automated pipeline. Those are all fine ways to *offer* it, but none of them are
required. A novel security architecture assessment that is delivered entirely
through the judgment of one senior architect is still, in this sense, something
the engineering system can do. It has a stable *what* — "assess this design and
tell us where the real risk is" — even though its *how* is a human being. The
reframe is not "turn everything into software." It's "stop making the
organizational location of the knowledge the thing people have to navigate."

## Two sides of the same thing: how it's used vs. how it's fulfilled

If you keep that *what/how* line, a second distinction falls out of it that is
worth making explicit, because keeping the two apart is most of the practical
value.

There is **how a consumer interacts** with something, and there is **how the
organization fulfills it.** These can and should move independently.

How it's used might be a page of documentation, a CLI, an API, a portal, a pull
request, a config declaration, a chat workflow, a request handed to an AI agent,
or a direct conversation with a specialist. Behind any of those, fulfillment
might be a single expert, a whole team, a Terraform module, a managed cloud
service, a policy check, a workflow, or some combination that changes quarter to
quarter.

The point of separating them is this: you can improve *how something is used*
without forcing consumers to relearn *who does it*, and you can change *who does
it, and how* without breaking everyone who uses it. The security team can
replace a manual review step with an automated check for the routine 80% and
keep human judgment for the rest — and the product teams asking for review don't
need to know the internals changed. The database *how* can migrate to a
different managed service without every consuming team filing new tickets to
learn the new shape of the org.

Most organizations couple these tightly by accident. The interface *is* the
team, so any change to the team, its tools, or its process becomes a change to
everyone who depends on it. Pulling them apart is unglamorous and it is where
most of the real leverage lives.

## Abstract the routing, not the accountability

This is the part most likely to be misread, so I'll be blunt about what I am
*not* saying.

I am not saying teams disappear. I am not saying ownership disappears. I am
certainly not saying accountability disappears or gets diffused into a warm
collective fog where no one is responsible for anything.

What should disappear from a consumer's daily path is the *routing*: "Security
Team B owns this control, so I need to file SEC-103, in this format, and wait for
their Thursday triage." That is organizational trivia the consumer is forced to
learn because the org chart is doubling as an API. It carries no engineering
value for the person doing routine work.

What should stay — and stay *visible* — is everything that actually matters:
who owns this, who has authority over what "correct" means in this domain, where
it came from, who's accountable when it breaks, and how you'd audit it. The rule
of thumb I'd offer: **ownership should be discoverable without being required
for routing.** You should always be able to find out who's behind something. You
shouldn't have to know that in order to use it.

It also helps to keep a few things apart that organizations habitually fuse:

- **Authority** — who gets to decide what "correct" means in a domain — does not
  imply **execution**. The security team can own the standard without personally
  performing every check.
- **Execution** — who or what actually performs the action — does not imply
  authority. An automated pipeline running a control has not been granted the
  right to redefine the control. An AI agent invoking something has not been
  handed authority just because it was able to call it.
- **Contribution** does not require **shared accountability.** Five teams can
  touch a delivery path without all five being accountable for the outcome.

Distributing *who does the work* across people, automation, and platforms is
healthy. Blurring *who is accountable* is not, and nothing in this reframe asks
you to.

## Not everything should be self-service

There's a failure mode lurking here, and it's the one that turns a reasonable
idea into a bad platform initiative. It's the assumption that the goal is to
encode everything, automate everything, and route every interaction through a
self-service portal until humans are never in the loop.

That is not the goal, and treating it as the goal is how you get brittle
automation wrapped around decisions that needed a person.

The honest heuristic is: **encode what is repeatable; collaborate on what is
novel.** When the organization has genuinely settled how to do something — the
intent is familiar, the risk is characterized, the outcome is predictable enough
to describe — then having a scarce specialist re-derive it by hand, ticket after
ticket, is waste. That knowledge can be captured as documentation, a standard, a
pattern, a policy, a template, a library, an infrastructure module, or
automation. Which form is an engineering choice, not a maturity ranking;
well-written documentation can be a perfectly good encoding, and code is not
automatically superior to it.

Notice the quiet assumption hiding in the word *settled*, though: someone has to
**decide** that a case is settled. "Repeatable" and "novel" are not objective
states a system can detect on its own. Deciding that a class of work is
understood well enough to represent — and safe enough to hand to an encoding — is
itself an act of domain expertise. Repetition is *evidence* that the knowledge
might be ready to capture; it is not proof that it is. The people with authority
over a domain have to stay in the position of making that call, and of revisiting
it, because a case that was settled last year can quietly become novel again when
the risk, the evidence, the technology, the regulation, or the underlying
assumptions move. This doesn't call for a central committee to adjudicate what
counts as "settled." It asks two things: that the judgment stay with the
expertise that can actually make it, and that the system never mistake "we have
formalized this before" for "this is certainly still true."

But repetition is a *signal to look*, not a rule to automate. Some repeated work
is still cheaper and safer as a conversation. And for genuinely novel or
high-risk work — a new architecture, an unusual threat model, a decision the
existing encodings don't cover — pulling a specialist directly into the work is
not a process failure. It is good engineering, and it is what you *free up* the
specialists to do when you stop spending them on the settled cases. The aim is to
**make exceptional work exceptional again**, not to pretend everything is
routine.

## Some friction is the point

The same care applies to friction. It is tempting, once you start removing
handoffs, to treat every gate and every wait as waste to be eliminated. That's
wrong, and it's dangerous.

The useful question is never "is there friction here?" It's "**what is this
friction for?**" Independent approval for a high-risk change to a regulated
production system is not accidental drag. It can be providing independent
authority, separation of duties, risk containment, a moment of human judgment,
and the evidence trail a regulator will later ask for. You do not delete that
because it slows a deploy. You *design* it — make it explicit, give it a named
authority, give it a break-glass path with logging and later review — instead of
leaving it as improvised tribal process.

So the line I'd draw is: **remove accidental friction; design intentional
friction.** A boundary is accidental when the only thing it's protecting is a
historical org shape — when its entire function is "you must discover which of
five teams owns this and ask them in their format." A boundary is intentional
when removing it would remove real authority, real risk containment, or real
judgment. A control is not accidental *just because* it slows delivery, and it is
not intentional *just because* it's always been there. You have to ask what value
it provides, and the answer is contextual, not universal.

## Encoded knowledge is not frozen truth

One more failure mode, because it's the one that shows up two years after the
good version of this succeeds.

Suppose you do the work. You encode the settled cases. You separate the *what*
from the *how*. Routine delivery gets faster. There's a real temptation, at that
point, to treat the encoded knowledge as reality — to believe that because a
policy is written down and a contract is automated, the thing it describes is
now true and can be left alone.

It can't. An encoding is a *representation* of what specialists currently
understand. It is never a perfect model of the world, and the world moves.
Usage patterns, failures, incidents, exceptions, rising cost, security findings,
new threats, a regulatory change, a platform migration, or a "routine" request
that keeps *not* fitting the routine path — all of these are evidence that what
the system believes might now be wrong.

So the encoded knowledge has to stay *challengeable*, and there has to be a live
path for that evidence to change it. Encoded expertise with no living expertise
behind it doesn't stay correct; it slowly becomes legacy that everyone follows
and no one trusts. The specialists don't get to stop specializing once they've
written things down. Their job shifts from re-deriving settled cases toward
tending, challenging, and evolving what's been encoded — which is, not
incidentally, a better use of them.

To be precise about the claim: evidence should be *able* to change what the
system does. It doesn't automatically force change — organizations have politics
and incentives that can sit on good evidence for a long time, and pretending
otherwise would be naive. But if there's no mechanism by which reality can talk
back to the encoding, you haven't built a faster engineering system. You've built
a faster way to keep doing last year's thing.

## The stable part isn't free

There's an objection I've been walking past, and it's the one that actually
kills these efforts in practice, so let me put it in the middle of the table.
Everything above assumes that *someone* has defined the stable thing consumers
depend on and keeps it stable while its fulfillment churns underneath. That
someone has to define it, describe how it's used, watch how it behaves in the
wild, absorb the evidence when it's wrong, and evolve it. None of that is free,
and none of it happens by itself.

This is the part teams routinely underestimate. The good version of this is not
"write the abstraction once and move on." A stable *what* laid over a changing
*how* is a standing commitment: the expectations have to be maintained, the way
it's used has to be kept usable, the evidence has to be watched, and the thing
has to change when reality does. Skip that, and you don't get a durable
interface — you get another half-maintained abstraction layer that people learn
to route around, which is strictly worse than the honest queue it replaced. And
it has to be worth it in the first place: formalizing something the organization
does three times a year, three different ways, for three different reasons, can
easily cost more than the friction it removes. **The effort of turning a piece of
work into a stable, stewarded interface should not exceed the complexity that
interface actually takes off the table.** Some things should stay a conversation
precisely because stewarding them as a shared interface would cost more than it
saves.

The harder half of this isn't technical, it's economic, and it lives in the
incentives. The team best positioned to steward a shared ability is usually not
the team that captures most of its value — the value shows up *somewhere else in
the system*, spread thin across every consumer who no longer has to walk the org
to get a result. Local incentives rarely reward that. A team measured on its own
output has every reason to solve its own problem and none to carry a dependency
on everyone else's behalf. **You cannot sustainably optimize the whole
engineering system against incentives that only reward local optimization.** And
a shared ability that no one is actually funded to steward is not, in any durable
sense, shared — it's a dependency waiting to rot: a name in a wiki with no one
home.

I'm deliberately not going to tell you how to pay for it. Chargeback, showback, a
central platform budget, a dedicated team, enterprise-architecture ownership —
those are all *possible* answers, and which one fits depends entirely on where
you are. What doesn't change is the obligation underneath them: **if you want
people to depend on a stable, system-level ability, you have to intentionally
fund and steward that ability at the scope where the dependency and the value
actually live.** A startup can meet that obligation with a convention and one
person who cares. A single domain can meet it inside its own team. A large
enterprise, or a federation of them, will need something more explicit. The
mechanism is local and negotiable. The obligation is not optional — and the
failure mode is always the same: an organization that wants the benefit of
shared abilities without deciding who is accountable for keeping them alive.

## What this is and isn't

Let me draw the boundaries hard, because an argument like this attracts
misreadings.

This is **not**:

- eliminating specialization, or wishing specialists away;
- everyone becoming full-stack;
- a reorg — you do not have to redraw the org chart to do any of this;
- another rename of DevOps;
- a replacement for Team Topologies, which is about how to structure teams and
  their interactions and which sits comfortably alongside this;
- an internal developer platform, a service catalog, or a portal;
- "maximum self-service" or "maximum automation";
- AI agents replacing engineers.

A platform can *implement* a lot of this. An internal platform is one very good
way to offer a stable *what* over a changing *how*. But the platform is a means,
not the definition — and a platform that just routes the old tickets faster
hasn't changed anything that matters. The idea lives at the level of *what the
consumer depends on*, and that level is true whether you realize it with Git and
conventions and conversation, or with contracts and audit logs and a control
plane.

One more, because it's the useful test: an AI agent is the honest stress test
for all of this. A human can, grudgingly, learn which Slack channel owns
Kubernetes and which queue provisions databases. An agent can't — or rather, if
those are the only interfaces, the agent will either be blocked or dangerously
over-privileged. Humans have been quietly paying the org-navigation tax for
years. Agents make it impossible to hide. If your engineering system only works
because experienced humans know who to ask, you don't have an engineering system.
You have a very expensive oral tradition.

## Standing on other people's shoulders

None of the individual pieces here are new, and it would be dishonest to imply
otherwise.

That organizational structure gets embedded in the systems we build is Conway's
Law, observed in 1968. The stance that you have to jointly optimize the social
and the technical, rather than either alone, comes from decades of sociotechnical
systems research. DevOps is the movement that first showed, at scale, what
happens when you refuse to accept one major organizational boundary as
permanent. Continuous delivery made routine release a solved problem you can
assume. SRE made reliability an engineering discipline with its own encoded
practice. Platform engineering has spent years on self-service, golden paths, and
reducing cognitive load. Team Topologies gave us a serious vocabulary for team
structures and interaction modes. Intent-based approaches let developers state
what they want and let an automated environment work out the how.

What I'm doing here is not claiming to have invented any of that. It's pulling
them together around a single reframe and stating it plainly: **the interface to
specialized expertise should increasingly be what the engineering system can
reliably do, not the organizational structure that happens to contain that
expertise.** Others have circled this idea from different directions; I'd be glad
to be pointed at prior work that says it better.

## The one-line version

If you take nothing else from this, take the reframe and its guardrail together,
because either one alone gets misused:

> Your interface to expertise should be what the system can do, not who happens
> to own it — abstract the routing, not the accountability.

Specialists still specialize. Owners still own. Regulators still get their
evidence. The gate that's actually protecting something stays. What goes away is
the quiet assumption that the map of your organization is the map every piece of
work has to walk.

Specialization remains. The silos are the part we can let go of.
