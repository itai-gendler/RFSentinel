---
kind: primary
routes:
  main: Main
steps:
- text: The user requests Check now.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::waze
- text: The Product schedules the next eligible report request and exposes its result or waiting condition.
  kind: product
  entities:
  - entity: waze-status
    effect: changes
    facts:
    - Checks
    - Status
  actor: user
  contexts:
    main:
      place: phone::waze
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WazeUi.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
---

# Check Waze now

## Trigger

The user requests Check now.

## Outcome

The Product schedules the next eligible report request and exposes its result or waiting condition.

## Edge cases

- A missing source setup or location is reported instead of claiming a successful check.
