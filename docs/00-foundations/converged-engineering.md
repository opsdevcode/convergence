# Converged Engineering

**Working definition:** Converged Engineering is an engineering model in
which specialized disciplines contribute expertise through shared,
reusable, governed capabilities and share responsibility for the outcomes
those capabilities enable.

This is a proposed model, not an established methodology.

**Converged Engineering does not eliminate specialization. It eliminates
specialization as a delivery boundary.**

## Why it is needed

If Convergence is the pressure (delivery boundaries becoming less useful),
Converged Engineering is a response: keep the specialties; change the
interface.

Without an explicit model, organizations tend to do one of three things:

1. Add a platform or DevOps layer that becomes another hop in the supply
   chain.
2. Declare "you build it, you run it" without encoding reliability,
   security, or infrastructure expertise.
3. Hope AI agents will navigate the org chart.

All three leave the customer product assembled through organizational
APIs.

## What converges

What should converge is **the path from intent to outcome**:

- how expertise is *exposed* (contracts, not queues, as the default)
- how work is *composed* (capabilities, not coordinated tickets)
- how **governance, reliability, and cost** attach (encoded, not appended)
- how **learning** returns (into capabilities, not only into team lore)
- how **responsibility for outcomes** is shared along that path

The specialties do not converge into one skill set.

## What does not converge

- Deep expertise in networking, identity, threat modeling, capacity,
  product discovery, data, or production failure
- The need for ownership of hard systems
- Novel work that is not yet a capability
- Human judgment for residual risk
- The physical and logical reality of layers in the implementation

If a diagram shows one generic "engineer" box, it is the wrong diagram.
See [Converged Engineering conceptual model](../../diagrams/converged-engineering-model.md).

## What happens to specialization

Specialization remains. Career paths, hiring, and training for SRE,
security, infrastructure, platform, product, and related roles remain.

What should shrink is the *default* use of those roles as a request
counter. Specialists increasingly encode expertise so others (and agents)
can consume it under contract. They still handle incidents, design review,
and work that is not yet encoded.

Do not create:

- a Convergence Engineering team
- a Converged Engineering silo
- a job function whose only purpose is to replace Platform Engineering
- another organizational layer that product teams must petition

A Platform Engineer can practice Converged Engineering. So can an SRE, an
infrastructure engineer, a product engineer, and a security engineer. The
model is a way of working, not a department.

## What happens to ownership

Ownership of a *capability* includes how it behaves in composition and in
production, not only ownership of a ticket queue. Product teams remain
accountable for customer-facing outcomes. Shared responsibility is
explicit in the contract, not infinite blame.

The developer is not the platform team's customer as the purpose of the
firm. The developer is part of the product value chain. Ownership should
optimize that chain.

## Role of capabilities

Capabilities are a **primary technical mechanism** of this model: a
reusable expression of engineering expertise with a defined contract,
consumable without navigating the producing organization.

They are not the only conceivable mechanism of Convergence. Culture,
funding, and staffing matter. This repository develops capabilities in
detail because they are a concrete place to encode expertise. It does not
claim that a capability catalog solves politics, understaffing, or a bad
product.

See [Capabilities](../02-capabilities/README.md).

## Distinctions

### DevOps

DevOps attacked the split between writing software and running it:
automation, shared responsibility, production feedback.

Converged Engineering agrees that wall is costly. It addresses a wider
set of specialist boundaries (platform, security, identity, network,
infrastructure as request APIs). Automating those requests is not the
model. Encoding the expertise so the request is unnecessary for standard
intents is closer.

DevOps can exist inside a still-siloed delivery chain. Converged
Engineering is specifically about that chain.

### Platform Engineering

Platform Engineering builds internal products that reduce undifferentiated
work: paved paths, portals, internal APIs.

Converged Engineering is not a rebrand of Platform Engineering. A platform
is often *how* capabilities are discovered and consumed. A portal that
routes the same tickets is not Converged Engineering. An organization
could practice the model with APIs and agent tools and a thin UI.

The platform is an enabling system, not the center of the universe and not
the definition of Convergence.

### SRE

SRE remains. Reliability should become a property of capabilities and
compositions, which requires SRE (or equivalent) expertise. Without that
expertise, "reliability in the contract" is a slogan. SRE does not
disappear into a generic role.

### Infrastructure and cloud

Substrate expertise remains. The substrate should increasingly be an
implementation detail of higher-level capabilities, which only works if
infrastructure engineers *build* those capabilities. The request catalog
should shrink as a primary interface. The skill does not.

### Product engineering

Product engineers still own customer experience and product judgment. They
should compose governed capabilities instead of integrating the company
through meetings. They do not become substitutes for security or
infrastructure expertise.

### AI

Agents are capability consumers. They make organizational interfaces
illegible. They do not autonomously run production safely by default.
Humans encode capabilities; agents call what is authorized. See
[AI-native engineering](../05-ai-native-engineering/README.md).

## What the model refuses

- "Everyone should just own everything."
- "The platform team is the customer of the business."
- "This model is whatever a vendor ships."
- The claim that the model is already an industry standard.
- A new silo named after the model.
