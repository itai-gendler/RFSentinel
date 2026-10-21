---
kind: primary
routes:
  main: Main
steps:
- text: The user selects a recorded journey.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::traces
- text: The Product shows its saved travel path and device summary.
  kind: product
  entities:
  - entity: trace
    effect: reads
    facts:
    - Name
    - Times
    - Route
    - Devices
    - Counts
  actor: user
  contexts:
    main:
      place: phone::traces
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/TripsActivity.kt
---

# Browse recorded traces

## Trigger

The user selects a recorded journey.

## Outcome

The Product shows its saved travel path and device summary.
