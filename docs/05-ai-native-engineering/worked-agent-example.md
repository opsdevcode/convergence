# Worked example: an agent through one capability

One intent, consumed by an agent, traced through the five needs. The point
is concreteness and realism, including where the agent stops.

This reuses the `ProvideRelationalStorage` capability from the
[method worked example](../12-method/worked-method-example.md). Nothing
about the capability changes because an agent consumes it. Only the
experience does.

## Setting

A product engineer is building a feature and directs a coding agent:
"add a Postgres database for the orders service, staging first."

The engineer is the **principal**. The agent acts for them, bounded by
their privilege.

## 1. Discovery

The agent asks what it may use for this principal, and learns that
`ProvideRelationalStorage` exists and is permitted. It does not see
capabilities the principal cannot use, and it does not learn this by
reading a wiki.

| Human would | Agent does |
| --- | --- |
| Recall the portal exists, or ask a teammate | Enumerate permitted capabilities for the principal |
| Notice unrelated tools and ignore them | Receive only what is in scope |

## 2. Contract

The agent reads a parseable contract: required inputs (size class, data
class, environment, retention), what the capability will do, and what it
will **not** do. The contract states that customer financial data
requires review and is not auto-provisioned.

The orders service uses order records, not raw financial data, so the
agent selects the eligible data class. Had it needed the restricted class,
the contract tells it so before it acts, not after.

## 3. Authorization

The agent holds the engineer's **privilege**, scoped to the delegated
task. It may provision eligible storage in staging. It may not:

| Permitted | Not permitted |
| --- | --- |
| Provision an eligible class in staging | Provision in production without the principal's production privilege |
| Use the standard size classes | Approve its own restricted-data exception |
| Retry safely | Escalate its own authority by calling another capability |

Invoking the capability granted none of this. The privilege came from the
principal. See
[Authorization and principals](authorization-and-principals.md).

## 4. Execution and blast radius

The agent submits a declared configuration. Execution is idempotent: the
declaration names a desired state, so a retry after a timeout does not
create a second database. Blast radius is bounded by contract to one
staging instance at a standard size, and the bound is enforced in
realization, not trusted to the agent.

The agent records the **intent** it was given alongside the call, because
"add a Postgres database for the orders service, staging first" explains
the action in a way the API call alone will not, six months later.

## 5. Observation

The outcome is observable to the agent and to a human: the instance
exists, connectivity and credentials were issued by the composed
capabilities, monitoring is attached. The agent reports the outcome to the
principal rather than declaring success from a 200 response.

## Where the agent stops

The engineer next says: "now do production." The production data for this
service is a restricted class, and the principal's privilege does not
cover it here.

The agent does not push through. It stops at the contract boundary and
hands back: production requires the restricted-data review, which is a
human judgment the agent holds no authority to make. This is the
[explicit exception path](../07-patterns/explicit-exception-path.md),
invoked by an agent that correctly recognizes it is outside its contract.

A human might have argued, found a shortcut, or messaged someone with
production access. That the agent cannot do any of those is a feature, and
it depends entirely on the boundary having been made explicit.

## What did not happen

- The agent acquired no authority by holding a tool.
- No separate agent capability, catalog, or graph was built. Same
  capability, different experience.
- The security review was neither removed nor delegated to the agent.
- Nothing about the capability changed to accommodate the agent.
