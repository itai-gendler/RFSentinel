---
appliesTo:
- type: entity
  id: waze-report
  effect: removes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
permits:
- actors:
  - user
- unattended: true
---

# Pausing Waze checks clears the reports

Pausing Waze checks clears the reports from the list and map, and so do turning the Waze category off and stopping the scan.
