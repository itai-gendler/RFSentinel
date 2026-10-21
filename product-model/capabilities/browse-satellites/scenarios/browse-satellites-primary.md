---
kind: primary
routes:
  main: Main
steps:
- text: The user opens GPS and satellites.
  kind: actor
  entities:
  - entity: satellite-status
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: phone::satellites
- text: The Product shows available satellite observations and heuristic warning evidence.
  kind: product
  entities:
  - entity: satellite-status
    effect: reads
    facts:
    - Satellites
    - Signal
    - Warning
  actor: user
  contexts:
    main:
      place: phone::satellites
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/GnssActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/GnssWatch.kt
---

# Browse GPS and satellites

## Trigger

The user opens GPS and satellites.

## Outcome

The Product shows available satellite observations and heuristic warning evidence.
