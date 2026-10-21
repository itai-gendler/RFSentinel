---
kind: primary
routes:
  main: Main
steps:
- text: The user opens Cell towers.
  kind: actor
  entities:
  - entity: cell-tower
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: phone::cells
- text: The Product shows network identity, radio generation, serving state, channel, signal and remembered observations.
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
      place: phone::cells
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/CellTowersActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/CellTowerStore.kt
---

# Browse cell towers

## Trigger

The user opens Cell towers.

## Outcome

The Product shows network identity, radio generation, serving state, channel, signal and remembered observations.
