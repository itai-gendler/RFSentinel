---
kind: alternate
routes:
  main: Main
steps:
- text: The selected car disconnects after it started the current scan.
  kind: condition
  entities:
  - entity: scan
    effect: reads
    facts:
    - Started by car
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product stops that car-started run; a manually started run continues.
  kind: product
  entities:
  - entity: scan
    effect: changes
    from: Running
    to: Stopped
    facts:
    - Receiver status
    - Started by car
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
  target: app/src/main/java/com/rfsentinel/app/receiver/CarAutoStart.kt
---

# Stop the scan the car started when the car disconnects

## Trigger

The selected car disconnects after it started the current scan.

## Outcome

The Product stops that car-started run; a manually started run continues.
