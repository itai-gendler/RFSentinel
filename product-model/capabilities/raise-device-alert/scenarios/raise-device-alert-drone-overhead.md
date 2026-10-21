---
kind: alternate
routes:
  main: Main
steps:
- text: A decoded drone position is within the overhead range and its five-minute repeat interval has elapsed.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product raises a drone-overhead warning using the broadcast position.
  kind: product
  entities:
  - entity: drone
    effect: reads
    facts:
    - Identification
    - Position
    - Operator position
    - Last heard
  - entity: nearby-device
    effect: reads
    facts:
    - Address
    - Signal
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/NotificationHelper.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/AlertPlayer.kt
---

# Warn about a drone overhead

## Trigger

A decoded drone position is within the overhead range and its five-minute repeat interval has elapsed.

## Outcome

The Product raises a drone-overhead warning using the broadcast position.
