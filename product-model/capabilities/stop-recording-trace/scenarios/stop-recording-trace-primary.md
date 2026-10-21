---
kind: primary
routes:
  main: Main
steps:
- text: The user stops trace recording.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product saves the finished trace with its end time and final totals.
  kind: product
  entities:
  - entity: trace
    effect: changes
    from: Recording
    to: Saved
    facts:
    - Times
    - Route
    - Devices
    - Counts
  actor: user
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/TripRecorder.kt
---

# Stop recording trace

## Trigger

The user stops trace recording.

## Outcome

The Product saves the finished trace with its end time and final totals.
