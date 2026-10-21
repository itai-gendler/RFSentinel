---
kind: primary
routes:
  main: Main
steps:
- text: The user resumes source checks.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::waze
- text: The Product returns to scheduled report checks.
  kind: product
  entities:
  - entity: waze-status
    effect: changes
    facts:
    - State
    - Status
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

# Resume Waze checks

## Trigger

The user resumes source checks.

## Outcome

The Product returns to scheduled report checks.
