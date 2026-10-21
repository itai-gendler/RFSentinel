---
kind: alternate
routes:
  main: Main
steps:
- text: The user stars the current observation.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product keeps the address as a favorite.
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

# Favorite from the car

## Trigger

The user stars the current observation.

## Outcome

The Product keeps the address as a favorite.
