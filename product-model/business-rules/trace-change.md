---
appliesTo:
- type: entity
  id: trace
  effect: changes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/TripsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/TripRecorder.kt
permits:
- actors:
  - user
- unattended: true
---

# The user renames and stops traces; the end of the scan stops them too

The user renames a trace or stops recording it. Stopping the scan also stops the recording, and a trace with no recorded position and no device is discarded.
