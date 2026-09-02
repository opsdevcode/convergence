# Capability graph structure

What a capability graph is and is not belongs to
[capability graph](../02-capabilities/capability-graph.md). This document
covers its structure: what the nodes and relations are, and why
partiality is a design property rather than a defect.

## Nodes

A node is a [capability](../02-capabilities/capability.md): something the
engineering system can accomplish.

Not nodes: teams, services, repositories, environments, tools, tickets,
or job titles. Each of those may appear in a
[realization](../02-capabilities/realization.md), and none of them is the
ability itself. A graph whose nodes map one to one onto the org chart has
described the organization, which is the thing consumers were supposed to
stop navigating. See
[capability as a team rename](../08-anti-patterns/capability-as-a-team-rename.md).

## Relations

Relations may eventually include ideas such as composes, requires,
constrains, governs, observes, and contributes-to.

**Do not treat this as an edge vocabulary standard.** The list is
illustrative. v0.1 defines no required graph schema, and an organization
that uses three relation types coherently is better off than one that
adopts six and applies them inconsistently.

Two relations carry more architectural weight than the rest.

| Relation | Why it matters structurally |
| --- | --- |
| composes | Carries the validity constraints in [composition](composition.md), including the rule that authority must not expand silently |
| governs | Identifies where [policy attaches](policy-attachment.md) and which authority stands behind a constraint |

## Partiality is a property, not a gap

**Useful incompleteness is better than fictional completeness.**

A capability graph may legitimately be partial, federated, scoped, or
composed from several domain views. None of those is a deficiency to be
corrected.

| Complete-looking graph | Useful partial graph |
| --- | --- |
| Every ability enumerated, most of them guessed | The abilities someone has actually traced |
| Owners assigned during a modelling exercise | Owners who know they are owners |
| Implies the system is understood | Shows what is understood and where it stops |
| Stale from the moment it is published | Grows when a real flow is examined |

An empty region of the graph is information. It says nobody has traced
that flow yet, which is true and useful. A populated region full of
assumptions asserts something false. See
[catalog first](../08-anti-patterns/catalog-first.md).

## Views over one set of abilities

Different audiences need different scopes: a product team's view, a
domain's view, an auditor's view, an agent's parseable subset. These are
views over the same underlying abilities rather than separate graphs to
reconcile.

This is why the repository speaks of a **conceptual set** of capabilities
rather than a single graph artifact. Federated and scoped views are the
normal case, not a compromise.

## Formalism should be earned

**Formalism should scale with organizational distance, risk, consequence,
reuse, and complexity.**

| Situation | Enough structure |
| --- | --- |
| One team, low risk, few consumers | A page listing abilities and owners |
| Several domains, moderate reuse | Named capabilities with written contracts and stated relations |
| Regulated, high reuse, agent consumers | Machine-readable descriptions, versioned contracts, retained evidence |

A page listing what the organization can do and who owns each item is a
capability graph. It does not become one by being loaded into software.

## Not required

- No graph database, registry, catalog, or portal.
- No single enterprise graph.
- No global capability taxonomy or canonical naming authority.
- No required node or edge schema.

Any of those may be a reasonable implementation choice. None is part of
the model, and requiring one would make Convergence dependent on
Convergence infrastructure.
