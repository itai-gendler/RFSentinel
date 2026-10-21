---
kind: alternate
routes:
  main: Main
steps:
- text: The user clears the current favorite.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product clears that favorite choice.
  kind: product
  entities:
  - entity: remembered-device
    effect: changes
    facts:
    - Favorite
  actor: user
  contexts:
    main:
      place: car::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/Favorites.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Remove a favorite from the car

## Trigger

The user clears the current favorite.

## Outcome

The Product clears that favorite choice.
