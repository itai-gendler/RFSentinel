---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens a drone observation in the car.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product presents available Remote ID information and offers navigation to reported coordinates.
  kind: product
  entities:
  - entity: drone
    effect: reads
    facts:
    - Identification
    - Position
  actor: user
  contexts:
    main:
      place: car::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/RemoteId.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Review drone information in the car

## Trigger

The user opens a drone observation in the car.

## Outcome

The Product presents available Remote ID information and offers navigation to reported coordinates.
