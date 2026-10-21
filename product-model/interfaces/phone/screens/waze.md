---
entities:
- entity: waze-status
  shows:
  - State
  - Checks
  - Status
- entity: waze-report
  shows:
  - Type
  - Position
  - Age
  - Confirmations
  - Relevance
  - Confidence
  - Level
  - Source
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WazeStatusActivity.kt
---

# Waze status

Waze status: whether checks are running or paused, what is sent and when, and the reports in range.
