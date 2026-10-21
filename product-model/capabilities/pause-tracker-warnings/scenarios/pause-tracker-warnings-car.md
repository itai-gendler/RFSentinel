---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses the global tracker-follow pause.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product saves a twenty-four-hour pause.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Tracker warnings paused until
  actor: user
  contexts:
    main:
      place: car::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/TrackerIgnoreScreen.kt
---

# Pause tracker warnings in the car

## Trigger

The user chooses the global tracker-follow pause.

## Outcome

The Product saves a twenty-four-hour pause.
