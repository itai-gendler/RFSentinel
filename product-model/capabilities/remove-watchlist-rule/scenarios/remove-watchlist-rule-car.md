---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Unwatch.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product removes the exact-address custom entry.
  kind: product
  entities:
  - entity: watchlist-rule
    effect: removes
  actor: user
  contexts:
    main:
      place: car::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiListActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Unwatch an address in the car

## Trigger

The user chooses Unwatch.

## Outcome

The Product removes the exact-address custom entry.
