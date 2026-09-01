# Agents as capability consumers

## What is realistic

Today's AI agents can call tools, follow structured contracts, and fail in
confident ways. They are not autonomous colleagues who understand your
political map. Designing as if they were is how you get unauthorized
changes and un-debuggable history.

This section assumes:

- Agents act with a principal (a user, a service account, a workflow
  identity). They do not get a parallel, weaker authorization story
  "because AI."
- Agents need **discovery** of capabilities they are allowed to use,
  **contracts** they can parse, **composition** only where policy allows,
  **execution** that is idempotent and logged, and **observation** of
  outcomes.
- Humans remain responsible for novel intent, for accepting residual risk,
  and for capability design.

## Five consumer classes, one conceptual set

| Consumer | Typical need |
| --- | --- |
| Human | Explanatory UX, exceptions, judgment |
| Product | Stable APIs, versioning, latency |
| Software system | Programmatic composition, no hallway context |
| Automation | Determinism, idempotency, no hidden prompts |
| AI agent | Tool schemas, tight authorization, blast-radius limits, traces of why a tool was called |

The [capability graph](../02-capabilities/capability-graph.md) names the
same conceptual set of capabilities. Experiences differ. Policy may restrict
agents more than humans for the same capability. That is a contract choice,
not a second org and not a required single graph product.

Invoking a capability does not grant authority. Agents still act under a
principal and privilege that the organization already decided.

See [Capability consumers](../../diagrams/capability-consumers.md).

## Discovery and contracts

An agent should be able to answer: which capabilities exist for this
principal, what inputs they require, what they will do, and what they will
not do. Natural-language handbooks are not a substitute for a contract.
They can sit beside one.

If discovery is "search Confluence," you have not built an agent interface.
You have built a search problem.

## Execution and blast radius

Safe execution for agents looks like the same engineering you already
wanted for automation: least privilege, dry-run or policy explain,
idempotency keys, rate limits, and environment promotion. Agents add a
need to record the **intent** they were given, because the call sequence
may not be obvious later.

Do not claim that agents will "run the company" if they can call
`DeployApplication`. They will call what you expose. Converged Engineering
makes the exposure explicit (authorized capabilities, not org navigation)
so that the debate is about contracts, not about whether someone pasted a
token into a chat tool.

## Humans still encode the expertise

Agents do not create SRE knowledge by consuming it. Specialists hold
expertise; the organization holds capabilities. If you skip making
capabilities explicit and hope the agent will "figure out Kubernetes like
our platform team," you have reconstructed tribal knowledge inside a
model context window. That does not survive the next incident.

Do not imply autonomous agents should bypass governance.
