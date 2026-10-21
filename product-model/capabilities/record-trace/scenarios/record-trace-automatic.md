---
kind: alternate
routes:
  main: Main
steps:
- text: A new scan starts with automatic trace recording enabled.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Location
  - entity: scan
    effect: reads
    facts: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product starts a new trace recording.
  kind: product
  entities:
  - entity: trace
    effect: creates
    to: Recording
    facts:
    - Name
    - Times
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

# Record a trace with each scan

## Trigger

A new scan starts with automatic trace recording enabled.

## Outcome

The Product starts a new trace recording.
