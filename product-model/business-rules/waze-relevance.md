---
appliesTo:
- type: entity
  id: waze-report
- type: entity
  id: waze-status
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Crowd-report alerts use current relevance and category level

Reports are re-evaluated between requests using current distance, age, confirmations and optional ahead-only road relevance. The remaining guided route takes precedence when available. Per-category levels distinguish loud, notification-only and silent behavior; request freshness and alert eligibility are separate.
