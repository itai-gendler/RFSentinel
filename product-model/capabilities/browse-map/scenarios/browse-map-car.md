---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens the available car map.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::map
- text: The Product shows nearby observations and mapped cameras with available reported positions.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Position
    - Evidence
  - entity: known-camera
    effect: reads
    facts:
    - Position
    - Kind
    - Alerts ignored
  - entity: drone
    effect: reads
    facts:
    - Position
  - entity: cell-tower
    effect: reads
    facts:
    - Position
  actor: user
  contexts:
    main:
      place: car::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapShared.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/CarMapRenderer.kt
---

# Review surroundings on the car map

## Trigger

The user opens the available car map.

## Outcome

The Product shows nearby observations and mapped cameras with available reported positions.

## Edge cases

- The live navigation surface requires the supported car host; older hosts use the simpler surrounding-map view.
