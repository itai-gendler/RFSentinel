---
kind: primary
routes:
  main: Main
steps:
- text: The user reviews a decoded drone broadcast.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product presents reported identification, motion and available drone or operator positions.
  kind: product
  entities:
  - entity: drone
    effect: reads
    facts:
    - Identification
    - Position
    - Operator position
    - Last heard
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/RemoteId.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
---

# Review drone report

## Trigger

The user reviews a decoded drone broadcast.

## Outcome

The Product presents reported identification, motion and available drone or operator positions.
