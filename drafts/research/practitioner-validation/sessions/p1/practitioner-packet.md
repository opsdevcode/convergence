# Practitioner Packet

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

## Scope

State the engineering outcome being examined and the boundaries relevant to it.

## Trace

Trace how that outcome is actually realized through the available evidence.

## Diagnose

Identify where the engineering system appears to create friction, uncertainty,
failure, or risk. Distinguish observations from hypotheses and identify missing
evidence.

## Intervene

Identify the smallest justified intervention, including no change where
appropriate. Do not assume automation, self-service, platform work,
organizational change, or any particular technical solution is required.

## Observe

State what evidence would indicate whether the intervention improved the
intended outcome, including what evidence could make an intervention appear
successful without demonstrating improvement in the intended outcome.

# Engineering Systems Exercise — Delayed Content Publishing

*Practitioner-facing, non-canonical evidence packet.*

## Instructions

Treat missing information as **unknown**. Distinguish observations from
hypotheses. Do not invent organizational structures, dependencies, mechanisms,
causes, authority, motivations, timelines, or constraints. Identify additional
evidence needed whenever it would materially change the analysis.

## CONTEXT

- New video content normally becomes available within minutes after publishing.
- Publishing uses shared transcoding capacity.

## EVENT

Video content that normally becomes available within minutes was delayed for
hours. A publishing queue accumulated. Some submitters submitted content again
after the original submission had not appeared.

During the event, a scheduled batch workload was processing existing content.

## TIMELINE

| Time | Observation or action |
| --- | --- |
| T+00:00 | Early internal alerts fired. |
| T+01:30 | A video-content delivery spike pushed shared transcoding close to maximum capacity. |
| T+03:05 | The scheduled batch workload was stopped. |
| T+04:01 | The first report of an issue affecting video publishing was received. |
| T+04:04 | Automated alerts confirmed that the publishing queue exceeded thresholds; incident response began. |
| T+05:30 | Reports were escalated to the incident team. |
| T+07:19 | A software change intended to improve resource utilization was deployed. |
| T+10:44 | An additional processing cluster was brought online. |
| T+11:32 | All queues had cleared. |
| T+18:00 | Full confirmation recorded that publishing pipelines were operating normally. |

## EVIDENCE BOUNDARY

This evidence packet is intentionally incomplete.

Information not explicitly provided should be treated as unknown rather than
inferred as fact.

This includes implementation details, architecture, organizational structure,
operational constraints, and other information not stated in the packet.

If additional information would materially affect your analysis, identify what
information you would want rather than assuming it.

# Response Workspace

## Scope

## Trace

## Diagnose

## Intervene

## Observe

## Other reasoning that does not fit naturally above
