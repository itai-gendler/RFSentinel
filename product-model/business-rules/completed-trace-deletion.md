---
appliesTo:
- type: entity
  id: trace
  effect: removes
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
  when:
  - state: Saved
- unattended: true
---

# Only a saved trace can be deleted by the user

Active recordings must be stopped before the user deletes them. The Product may discard an empty recording on completion.
