---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Stop ignoring in the car.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product removes the selected tracker ignore.
  kind: product
  entities:
  - entity: tracker-ignore
    effect: removes
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
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Stop ignoring from the car

## Trigger

The user chooses Stop ignoring in the car.

## Outcome

The Product removes the selected tracker ignore.
