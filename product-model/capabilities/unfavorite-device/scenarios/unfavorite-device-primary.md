---
kind: primary
routes:
  main: Main
steps:
- text: The user removes the favorite mark.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
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
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/Favorites.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
---

# Unfavorite device

## Trigger

The user removes the favorite mark.

## Outcome

The Product clears that favorite choice.
