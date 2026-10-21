---
kind: alternate
routes:
  main: Main
steps:
- text: The phone moves or time advances while current crowd reports remain available.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Detection
    - Alerts
  unattended: true
  contexts:
    main:
      place: phone::waze
- text: The Product re-scores distance, age and confirmations, checks road or remaining-route relevance, and issues
    eligible level-specific alerts.
  kind: product
  entities:
  - entity: waze-report
    effect: changes
    facts:
    - Relevance
    - Confidence
  - entity: route
    effect: reads
    facts: []
  contexts:
    main:
      place: phone::waze
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazeWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/WazePolice.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Re-score Waze reports as the user moves

## Trigger

The phone moves or time advances while current crowd reports remain available.

## Outcome

The Product re-scores distance, age and confirmations, checks road or remaining-route relevance, and issues eligible level-specific alerts.

## Edge cases

- A newly relevant report can alert without waiting for another network request.
- With ahead-only enabled, an active route takes priority over road and heading estimates.
- Silent reports remain contextual data; approaching spoken callouts require the loud level.
