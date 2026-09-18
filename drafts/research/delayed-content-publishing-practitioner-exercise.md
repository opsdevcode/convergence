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
