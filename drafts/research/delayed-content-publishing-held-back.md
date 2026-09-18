# HELD BACK — POST-ANALYSIS: delayed content publishing

*Research-only comparison evidence. Do not share before the practitioner
analysis is frozen. This is not an answer key, canonical explanation, or
scoring rubric.*

## Source and status

The source is the public first-party report identified in
[research provenance](delayed-content-publishing-provenance.md). The findings
below are the source's retrospective account, not facts that a practitioner
must infer from the exercise packet.

## Discovered during or after investigation

The source reports these findings, but does not establish when investigators
identified each one:

- transcoding capacity lacked sufficient headroom for large content spikes;
- a recent quality change increased processing time and compute per episode;
  and
- a resource-scheduling defect following a hardware migration underused
  available compute and reduced throughput by about 10%.

## Retrospective interpretation

The report attributes the incident to the combination of insufficient capacity
headroom, the batch reprocessing workload, increased per-episode processing
cost, and the resource-scheduling defect.

It says the batch workload appeared acceptable earlier in the day and became
problematic when combined with increased submissions. It interprets the gap
between the first alerts and formal incident response as a failure to
recognize the broader capacity issue until queue thresholds were breached.

Repeated submission itself is practitioner-visible evidence. The source's
interpretation that the system had not confirmed receipt and queueing remains
held back.

## Post-incident intervention and follow-up

The source reports follow-up work to:

- increase transcoding capacity by approximately 67%;
- add earlier capacity-limit monitoring;
- improve capacity planning for bursts and incident recovery;
- prioritize new content ahead of background operations;
- extend rate limiting and backpressure; and
- improve notification when publishing is not working.

This post-incident material must remain held back from the practitioner
packet until analysis is frozen. Afterward, it can be compared with the
analysis to identify agreement, disagreement, and missing evidence; it must
not be used to score the analysis against a single retrospective narrative.
