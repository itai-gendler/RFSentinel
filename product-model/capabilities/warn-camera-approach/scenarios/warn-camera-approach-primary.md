---
kind: primary
routes:
  main: Main
steps:
- text: Successive location fixes show approach to an enabled, nonignored camera on the relevant facing direction.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Known cameras
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product issues the qualifying camera warning and records its repeat time.
  kind: product
  entities:
  - entity: known-camera
    effect: reads
    facts:
    - Position
    - Kind
    - Label
    - Direction
    - Alerts ignored
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/alpr/KnownCameras.kt
---

# Warn of camera approach

## Trigger

Successive location fixes show approach to an enabled, nonignored camera on the relevant facing direction.

## Outcome

The Product issues the qualifying camera warning and records its repeat time.

## Edge cases

- The first nearby fix alone does not warn; distance must decrease by more than three metres.
- Each camera has a thirty-minute repeat interval, and at most one camera warns per fix.
- Plate readers use about twenty seconds of travel; speed and red-light cameras use about thirty seconds, within bounded warning ranges.
