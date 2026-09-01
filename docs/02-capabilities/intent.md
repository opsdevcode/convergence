# Intent

**Intent** is the result a consumer is trying to cause, expressed at the
level of responsibility that consumer owns.

**Intent should be expressed at the highest level of abstraction the
consumer can responsibly own.**

Higher abstraction is not always better. A network engineer may
legitimately express technical networking intent because that is the
level they own. The rule exists to stop consumers being forced into
implementation details **outside** their responsibility.

## Conceptual levels (not a mandatory taxonomy)

These labels are useful for conversation. They are not a required
classification scheme.

**Business:** "Allow customers to upload claim documents."

**Product / domain:** "Provide document upload."

**Engineering:** "Provide durable object storage."

**Technical:** "Provision replicated storage."

A product engineer requesting `ProvideRelationalStorage` is expressing
engineering intent they can own. They should not have to own "which
firewall form" unless that is their job.

## Consumers of intent

Humans, products, software systems, automation, and authorized agents may
express intent. Agents still act under a principal and policy.

See [Conceptual model](../00-foundations/conceptual-model.md).
