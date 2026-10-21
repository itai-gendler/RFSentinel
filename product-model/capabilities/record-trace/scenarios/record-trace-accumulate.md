---
kind: alternate
routes:
  main: Main
steps:
- text: Location fixes and device observations arrive during recording.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product updates the recorded travel path, device summaries, requested names and counts.
  kind: product
  entities:
  - entity: trace
    effect: changes
    facts:
    - Route
    - Devices
    - Counts
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

# Add positions and devices to a trace

## Trigger

Location fixes and device observations arrive during recording.

## Outcome

The Product updates the recorded travel path, device summaries, requested names and counts.
