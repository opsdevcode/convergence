# Regulated enterprise

Illustrative: security, risk, compliance, architecture, IAM, network,
cloud, infrastructure, SRE, database/data, change controls, audit.

Example intent: deploy a customer-facing API that accesses regulated
customer data (`LaunchRegulatedAPI`).

## Traditional routing

The consumer learns which team owns networking, which queue provisions
databases, who approves identity, which CAB form is current, which Slack
channel "really" decides. Delivery is an organizational API. Governance
sits on the path as a sequence of gates.

## Converged Engineering approach

The same specialties still exist. Domain authority is not dissolved.

The **capability** is what the system can accomplish: launch an eligible
API with required controls. **Experience** may be a declared pipeline
plus an exception desk. **Realization** includes policy-as-code, identity
issuance, connectivity patterns, data-protection controls, and **human
review** where the contract says the case is exceptional.

Convergence does **not** remove governance.

**Governance moves into delivery rather than delivery moving through
governance.**

Human review and escalation remain appropriate for exceptional and
high-risk cases. Make exceptional work exceptional again. Audit evidence
can be a property of realization (what ran, who approved exceptions),
not a scavenger hunt across inboxes.

`ProtectSensitiveData` and `AssessNovelSecurityArchitecture` may both
appear: the former more repeatable, the latter human-realized and still
a first-class capability.
