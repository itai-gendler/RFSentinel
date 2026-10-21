---
kind: alternate
routes:
  main: Main
steps:
- text: The scan ends while recording has accumulated data.
  kind: condition
  entities:
  - entity: scan
    effect: reads
    facts: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product closes and saves the active trace.
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

# Stop the trace when scanning stops

## Trigger

The scan ends while recording has accumulated data.

## Outcome

The Product closes and saves the active trace.
