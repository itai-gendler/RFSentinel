---
kind: primary
routes:
  main: Main
steps:
- text: The user reviews the enabled report source.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::waze
- text: The Product shows current reports and the state of recent checks.
  kind: product
  entities:
  - entity: waze-report
    effect: reads
    facts:
    - Type
    - Position
    - Age
    - Confirmations
    - Relevance
    - Confidence
    - Level
    - Source
  - entity: waze-status
    effect: reads
    facts:
    - State
    - Checks
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
---

# Browse Waze reports

## Trigger

The user reviews the enabled report source.

## Outcome

The Product shows current reports and the state of recent checks.
