---
kind: primary
routes:
  main: Main
steps:
- text: The user adds the selected address to favorites.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product keeps the address as a favorite in remembered history.
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

# Favorite device

## Trigger

The user adds the selected address to favorites.

## Outcome

The Product keeps the address as a favorite in remembered history.
