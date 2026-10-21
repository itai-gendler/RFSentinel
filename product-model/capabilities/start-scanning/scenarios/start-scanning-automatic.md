---
kind: alternate
routes:
  main: Main
steps:
- text: An enabled boot or selected-car start trigger arrives while scanning is stopped.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Auto start
  - entity: android-access
    effect: reads
    facts:
    - Scan permission
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product starts a local session and records whether it was started by the car.
  kind: product
  entities:
  - entity: scan
    effect: changes
    from: Stopped
    to: Running
    facts:
    - Started by car
    - Receiver status
    - Started at
    - Active
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Permissions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/receiver/BootReceiver.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/receiver/CarAutoStart.kt
---

# Start scanning after a reboot or in the car

## Trigger

An enabled boot or selected-car start trigger arrives while scanning is stopped.

## Outcome

The Product starts a local session and records whether it was started by the car.
