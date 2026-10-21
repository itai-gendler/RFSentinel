---
appliesTo:
- type: entity
  id: waze-report
  effect: changes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
permits:
- unattended: true
---

# Waze reports are re-scored as the user moves

Between checks, the reports already fetched are re-scored every second by distance, age and driver confirmations, so a report alerts as soon as it comes into range.
