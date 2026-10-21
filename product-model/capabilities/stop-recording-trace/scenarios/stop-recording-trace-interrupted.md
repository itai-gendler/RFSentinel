---
kind: edge
routes:
  main: Main
steps:
- text: The application opens after a previous recording was interrupted.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::traces
- text: The Product closes the unfinished trace from its persisted points and device summaries.
  kind: product
  entities:
  - entity: trace
    effect: changes
    from: Recording
    to: Saved
    facts:
    - Times
    - Route
    - Counts
  contexts:
    main:
      place: phone::traces
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/TripRecorder.kt
---

# Keep a trace recorded before an interruption

## Trigger

The application opens after a previous recording was interrupted.

## Outcome

The Product closes the unfinished trace from its persisted points and device summaries.
