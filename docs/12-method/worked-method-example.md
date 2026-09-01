# Worked example: one full pass

One flow, all six activities, in an organization that is not starting
from scratch. The point of this document is concreteness, including the
parts that stay unresolved.

## Setting

Roughly 600 engineers. Product, Platform, SRE, Infrastructure, Security,
Identity, Networking, and a database group all exist and are competent.
No reorganization is planned. There is a portal, and today it mostly
files tickets.

Flow chosen: a product engineer needs relational storage for a new
feature. It happens perhaps twice a month, everyone complains about it,
and a product engineering lead is willing to own the result.

## 1. Trace

Three recent instances were traced. They took 9, 14, and 31 days. Working
time in all three was under a day.

| # | Interaction | Decides | Authority | Same answer every time? |
| --- | --- | --- | --- | --- |
| 1 | Ask which team owns databases | Nothing | None | Yes |
| 2 | Ticket: instance provisioning | Size class, region | Infrastructure | Yes, for standard sizes |
| 3 | Ticket: connectivity | Subnet, security group | Networking | Yes, for the standard pattern |
| 4 | Ticket: credentials | Credential issuance and rotation | Identity | Yes |
| 5 | Review: data classification | Whether this data class is permitted here | Security | No |
| 6 | Ticket: engine parameters | Backup window, parameter group | Database group | Yes, for the standard profile |
| 7 | Ask SRE about dashboards | Whether monitoring exists | SRE | Yes |

The 31-day instance differed from the others in exactly one way: the data
in interaction 5 was customer financial data, and the answer was
different.

## 2. Evaluate

| # | Recognition | Reasoning |
| --- | --- | --- |
| 1 | Routing | Decides nothing, applies no expertise, pure discovery cost |
| 2 | Duplicated interpretation | Real expertise, already settled for standard size classes |
| 3 | Duplicated interpretation | The standard pattern was chosen once and re-applied |
| 4 | Duplicated interpretation | Issuance is mechanical; the policy behind it is not |
| 5 | **Engineering and governance value** | Genuine judgment, varies by case, carries regulatory weight |
| 6 | Duplicated interpretation | Standard profile applies unless the workload is unusual |
| 7 | Routing | Monitoring either exists or it does not; asking is not the control |

Interaction 5 is the one that stays.

It is also the clearest case of value delivered in the wrong shape. The
security judgment is intentional. Requiring the consumer to discover that
the review exists, find a reviewer, and re-explain the system from
scratch is not part of the judgment. The team separated the two: keep the
decision and the authority, remove the discovery and the re-explanation.

For interactions 2, 3, 4, and 6, the domain authorities agreed the
standard cases were settled and disagreed about where "standard" ends.
That disagreement became the contract boundary rather than a blocker.

## 3. Identify

The organization can already provide eligible relational storage. It has
been doing it for years, slowly.

`ProvideRelationalStorage`

Rejected names: `DatabaseRequest` (names a queue), `RDS Provisioning`
(names a vendor), `Database Self-Service Portal` (an experience, not a
capability).

Domain authority stays with infrastructure, networking, identity,
security, and the database group. Capability ownership went to the
platform group, which owns none of those domains and does not acquire
authority over them by owning the composite.

## 4. Decide

Encoded:

| What | Form | Why this form |
| --- | --- | --- |
| Eligible engines, size classes, regions | Contract plus policy | The rule must be stated and applied consistently |
| Standard network placement | Infrastructure module | The action is mechanical and version-managed |
| Credential issuance and rotation | Automation | Mechanical, frequent, safe to repeat |
| Backup and parameter profile | Standard, with a documented exception route | Stable, but occasionally genuinely wrong |
| Data-class eligibility rules | Decision guidance | The judgment is the variable part, not the action |
| Which data classes require review | Contract | Consumers need this before they commit |

Not encoded: the data-class decision itself. The rules were written down
so consumers could predict the common answers and self-select, but the
determination for anything outside the documented classes stayed with
security. Repetition had not made that judgment mechanical; it had only
made the common cases predictable.

Also not encoded: multi-region replication. It had come up twice, the
requirements differed both times, and nobody could state a stable rule.
Recorded as deliberately deferred, with the reason.

## 5. Design

**Experience.** A declared configuration in the application repository:
size class, data class, environment, retention. The eligibility rules are
readable before committing, so a consumer learns that customer financial
data needs review at authoring time, not on day nine. Owner and domain
authorities are listed on the capability page.

**Realization.** Infrastructure module, managed database service,
automated credential issuance, standard parameter profile, monitoring
attached by default. Domain authorities own their parts and change them
without renegotiating with consumers.

**Intentional friction, designed in.** For data classes requiring review:

| Stated | Value |
| --- | --- |
| What it is for | Regulatory obligation and risk containment on sensitive data |
| Who holds authority | Security domain authority |
| When it applies | Only the data classes the contract names |
| What evidence it leaves | The decision, the reasoning, and the approver, retained on the path |

The review no longer requires the consumer to find anyone. It is
triggered by the declaration and arrives with the system context already
attached. Elapsed time for reviewed cases dropped without removing the
review.

**Exception path.** Anything outside the contract routes to the relevant
domain authority with a named owner, a logged reason, and later review.
It is expected to be rare. If it stops being rare, the contract is wrong.

## 6. Operate

After one quarter:

| Evidence | Response |
| --- | --- |
| Exceptions clustered on one size class just above the top standard tier | Contract boundary was wrong; tier added |
| Two consumers asked whether encryption was included | Documentation gap, not a capability gap |
| One incident traced to a parameter default | Realization change, consumers unaffected, no announcement needed |
| Multi-region asked twice more, still with different requirements | Still deferred; the deferral is now documented rather than forgotten |
| A database specialist was manually tuning some instances after creation | Not yet resolved; the encoding does not cover a real case |

The last row is a decay signal appearing within one quarter. It was
recorded and assigned, not explained away.

## What did not happen

- No reorganization. Every specialty still exists with the same authority.
- No platform purchase. The realization used tools already in place.
- No capability catalog. One capability page and a contract.
- No graph database, and no enterprise capability taxonomy.
- No claim that ticket count is the measure of success. It fell, which is
  a signal and not the score. See
  [design doctrine](../00-foundations/design-doctrine.md).
- The security review was not removed, and removing it was never a goal.

## What stayed unresolved

Multi-region replication, the manual tuning the encoding does not cover,
and whether the platform group is the right long-term capability owner.
Three open items after a successful pass is normal. A pass that resolves
everything usually means the trace was too shallow.
