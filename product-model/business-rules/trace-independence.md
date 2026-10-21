---
appliesTo:
- type: entity
  id: trace
- type: entity
  id: scan
- type: entity
  id: route
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/TripRecorder.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
---

# Trace recording keeps its own route and observations

Trace recording retains route points and heard device summaries independently of match-log GPS tagging. Stopping scanning closes the active trace; stopping guidance alone does not.
