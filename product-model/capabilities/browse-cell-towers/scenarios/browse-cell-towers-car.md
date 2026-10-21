---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens Cell towers in the car.
  kind: actor
  entities:
  - entity: cell-tower
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: car::cells
- text: The Product shows the available serving and neighboring cell information.
  kind: product
  entities:
  - entity: cell-tower
    effect: reads
    facts:
    - Identity
    - Serving
    - Signal
    - Seen
    - Position
    - Warning
  actor: user
  contexts:
    main:
      place: car::cells
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/CellTowersActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/CellTowerStore.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/CellsScreen.kt
---

# Review cell information in the car

## Trigger

The user opens Cell towers in the car.

## Outcome

The Product shows the available serving and neighboring cell information.
