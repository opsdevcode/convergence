# Portal as ticket router

A portal is built as the front door to engineering. Behind every form, the
submission becomes a ticket in the same queue as before.

## Why it is tempting

It is achievable. Building a portal requires no negotiation with domain
authorities about what their rules actually are, no agreement on
eligibility, and no change to how work is fulfilled. It ships in a
quarter and it demos well.

Encoding the underlying expertise requires specialists to state rules
they may not have written down, and to accept that the encoded version
will be applied without them. That takes much longer and can be
politically expensive.

## What it costs

| Cost | Detail |
| --- | --- |
| Nothing improves | Elapsed time is unchanged, because the queue was the constraint |
| Credibility | Consumers conclude the model is cosmetic, making the next attempt harder |
| A new dependency | The portal now needs maintenance and adds a component to the path |
| False signal | Portal adoption rises, so the effort looks successful |

The false signal is the expensive part. Adoption metrics improve while
the delivery path is unchanged, which delays the discovery that nothing
was solved.

## How to recognize it

- Elapsed time for a routine intent has not moved.
- Every form submission produces a ticket assigned to a human.
- Consumers still ask in chat whether their request has been picked up.
- The specialists' workload is identical, arriving through a new channel.

## What to do instead

A portal is an [experience](../02-capabilities/experience.md), and there
is nothing wrong with it. The problem is a portal substituted for
[realization](../02-capabilities/realization.md) work.

Pick one intent. Ask the domain authorities what the settled cases are.
Encode those, keeping the judgment that genuinely varies as an
[explicit exception path](../07-patterns/explicit-exception-path.md). One
intent that actually completes without a queue is worth more than twenty
forms.

## Related

[Evaluating interactions](../12-method/evaluating-interactions.md)
distinguishes a control that carries value from routing that only looks
like one.
