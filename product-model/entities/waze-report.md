---
domain: waze-status
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazePolice.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
---

# Waze report

A third-party crowd report with its current local relevance.

## Information kept

- **Type** — Police, hazard, accident, closure or traffic category and subtype.
- **Position** — Reported location.
- **Age** — Report time and freshness.
- **Confirmations** — Available driver confirmations.
- **Relevance** — Distance, relative direction, trend and whether it is on the way ahead.
- **Confidence** — Locally recalculated evidence score.
- **Level** — Sound and voice, notification only or silent.
- **Source** — The chosen online report provider.
