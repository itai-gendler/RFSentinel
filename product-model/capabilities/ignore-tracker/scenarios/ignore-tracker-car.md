---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Today only or Mine in the car tracker choices.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product records the selected tracker ignore mode.
  kind: product
  entities:
  - entity: tracker-ignore
    effect: creates
    facts:
    - Address
    - Kind
    - Mode
    - Until
    - Last heard
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
  target: app/src/main/java/com/rfsentinel/app/data/TrackerMutes.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/TrackerIgnoreScreen.kt
---

# Ignore a tracker from the car

## Trigger

The user chooses Today only or Mine in the car tracker choices.

## Outcome

The Product records the selected tracker ignore mode.
