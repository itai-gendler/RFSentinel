---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Watch on a current device.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::device
- text: The Product adds an exact-address custom entry.
  kind: product
  entities:
  - entity: watchlist-rule
    effect: creates
    facts:
    - Match
    - Label
    - Source
    - Score
    - Category
    - Custom
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
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Watch an exact address in the car

## Trigger

The user chooses Watch on a current device.

## Outcome

The Product adds an exact-address custom entry.
