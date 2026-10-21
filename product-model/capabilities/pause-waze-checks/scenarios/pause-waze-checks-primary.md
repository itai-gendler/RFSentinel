---
kind: primary
routes:
  main: Main
steps:
- text: The user pauses the source checks.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::waze
- text: The Product pauses subsequent requests and removes currently displayed reports.
  kind: product
  entities:
  - entity: waze-status
    effect: changes
    facts:
    - State
    - Status
  - entity: waze-report
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::waze
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WazeStatusActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
---

# Pause Waze checks

## Trigger

The user pauses the source checks.

## Outcome

The Product pauses subsequent requests and removes currently displayed reports.
