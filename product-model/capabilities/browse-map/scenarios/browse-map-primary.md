---
kind: primary
routes:
  main: Main
steps:
- text: The user opens the map and selects a filter or location.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product shows available device positions, mapped cameras, selected trace and enabled contextual layers.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Address
    - Name
    - Signal
    - Evidence
    - Position
  - entity: known-camera
    effect: reads
    facts:
    - Position
    - Kind
    - Label
    - Direction
    - Alerts ignored
  - entity: cctv-camera
    effect: reads
    facts:
    - Position
    - Description
    - Visibility
    - View area
  - entity: trace
    effect: reads
    facts:
    - Name
    - Times
    - Route
    - Devices
    - Counts
  - entity: cell-tower
    effect: reads
    facts:
    - Identity
    - Position
  - entity: aircraft
    effect: reads
    facts:
    - Identification
    - Position
    - Source
    - Evidence
    - Time
  - entity: waze-report
    effect: reads
    facts:
    - Type
    - Position
    - Age
    - Confirmations
    - Relevance
    - Confidence
    - Level
    - Source
  actor: user
  contexts:
    main:
      place: phone::map
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
---

# Browse map

## Trigger

The user opens the map and selects a filter or location.

## Outcome

The Product shows available device positions, mapped cameras, selected trace and enabled contextual layers.

## Edge cases

- Without a usable position, the map does not imply an exact location for an observed address.
- CCTV observations are map context and do not generate approach alerts.
