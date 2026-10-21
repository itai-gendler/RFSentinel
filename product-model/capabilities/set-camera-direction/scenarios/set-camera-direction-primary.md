---
kind: primary
routes:
  main: Main
steps:
- text: The user saves one of the offered compass directions or clears the local choice.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product keeps the local facing choice for warning evaluation and map review.
  kind: product
  entities:
  - entity: known-camera
    effect: changes
    facts:
    - Direction
  actor: user
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/CameraDirections.kt
---

# Set camera direction

## Trigger

The user saves one of the offered compass directions or clears the local choice.

## Outcome

The Product keeps the local facing choice for warning evaluation and map review.
