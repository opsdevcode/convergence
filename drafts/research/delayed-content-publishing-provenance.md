# Delayed content publishing — research provenance

*Research-only provenance. Do not provide this file, its source link, or its
source identity with the practitioner exercise before analysis is frozen.*

## Public source

- Spotify Engineering, “Content Ingestion & Podcast Video Incident Report,”
  published July 20, 2026:
  <https://engineering.atspotify.com/2026/7/content-ingestion-and-podcast-video-incident-report>

This first-party public report is the provenance for the paired practitioner
exercise. Public evidence is the basis for this public-research case.

## Temporal normalization

Calendar dates and absolute UTC timestamps were normalized to relative elapsed
time for source blinding. Event ordering and elapsed intervals are preserved.
No engineering event, duration, quantity, causal relationship, or constraint
was changed by this transformation.

## Assertion-level mapping

| Practitioner-visible assertion | Source location | Source timestamp | Practitioner-relative timestamp | Transformation/generalization | Epistemic status |
| --- | --- | --- | --- | --- | --- |
| New video content normally becomes available within minutes after publishing. | “What happened?” | Not timestamped | Not applicable | “Video podcast episodes” generalized to “video content”; timing preserved. | Source-reported observation |
| Publishing uses shared transcoding capacity. | “What happened?” | Not timestamped | Not applicable | Source’s transcoding infrastructure and simultaneous processing generalized to shared transcoding capacity. | Source-reported observation |
| Video content was delayed for hours. | “What happened?” | June 24, 2026; no time stated | Not applicable | Company and product identity removed; duration preserved. | Source-reported observation |
| A publishing queue accumulated. | “What happened?” | June 24, 2026; no time stated | Not applicable | Source’s queue buildup generalized without source identity. | Source-reported observation |
| Some submitters submitted content again after the original submission had not appeared. | “What happened?” | June 24, 2026; no time stated | Not applicable | “Creators re-uploaded episodes” generalized to repeated submission; no motive or consequence transferred. | Source-reported observation |
| Early internal alerts fired. | “Timeline (UTC)” | June 24, 2026, 13:30 UTC | T+00:00 | Absolute time normalized to the relative origin. | Source-reported timeline event |
| A video-content delivery spike pushed shared transcoding close to maximum capacity. | “Timeline (UTC)” | June 24, 2026, 15:00 UTC | T+01:30 | Absolute time normalized; event wording generalized from source-specific content. | Source-reported timeline event |
| During the event, a scheduled batch workload was processing existing content. | “What happened?” | Not timestamped; start time unavailable | Not applicable | “Batch job processing existing episodes” generalized to batch workload processing existing content; no start time added. | Source-reported observation |
| The batch workload was stopped. | “Timeline (UTC)” | June 24, 2026, 16:35 UTC | T+03:05 | Absolute time normalized; “batch processing job” generalized to batch workload. | Source-recorded action |
| The first report of an issue affecting video publishing was received. | “Timeline (UTC)” | June 24, 2026, 17:31 UTC | T+04:01 | Absolute time normalized; company identity removed. | Source-reported timeline event |
| Automated alerts confirmed that the publishing queue exceeded thresholds. | “Timeline (UTC)” | June 24, 2026, 17:34 UTC | T+04:04 | Absolute time normalized; source-specific product name removed. | Source-reported timeline event |
| Incident response began. | “Timeline (UTC)” | June 24, 2026, 17:34 UTC | T+04:04 | Absolute time normalized; no organizational detail added. | Source-reported timeline event |
| Reports were escalated to the incident team. | “Timeline (UTC)” | June 24, 2026, 19:00 UTC | T+05:30 | Absolute time normalized; source identity removed. | Source-reported timeline event |
| A software change intended to improve resource utilization was deployed. | “Timeline (UTC)” | June 24, 2026, 20:49 UTC | T+07:19 | Absolute time normalized; source’s scheduling-defect detail withheld. | Source-recorded action |
| An additional processing cluster was brought online. | “Timeline (UTC)” | June 25, 2026, 00:14 UTC | T+10:44 | Absolute time normalized; source identity removed. | Source-recorded action |
| All queues had cleared. | “Timeline (UTC)” | June 25, 2026, 01:02 UTC | T+11:32 | Absolute time normalized. | Source-reported timeline event |
| Publishing pipelines were confirmed operating normally. | “Timeline (UTC)” | June 25, 2026, 07:30 UTC | T+18:00 | Absolute time normalized; source-specific product name removed. | Source-reported timeline event |

The practitioner packet deliberately does not transfer the source identity,
URL, source-specific terminology, source interpretations, causal findings, or
follow-up plan. Generalization is intended to preserve the engineering meaning
of transferred facts. Information not transferred is not thereby classified as
false; it remains unavailable to the practitioner unless separately stated.

## Interpretation boundary

The source's retrospective account is evidence to compare after a practitioner
analysis is frozen. It is not a canonical explanation, a prescribed
intervention, an answer key, or an evaluation rubric. See
[held-back post-analysis evidence](delayed-content-publishing-held-back.md).
