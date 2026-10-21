---
kind: alternate
routes:
  main: Main
steps:
- text: A device marked out of range is heard again before it is dropped.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product puts it back in range with fresh signal and evidence.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    from: Stale
    to: Heard
    facts:
    - Address
    - Name
    - Vendor
    - Type
    - Sources
    - Signal
    - Evidence
    - Seen
    - Decoded data
    - Position
    - Linked address
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/EvidenceFusion.kt
---

# Bring a device back in range

## Trigger

A device marked out of range is heard again before it is dropped.

## Outcome

The Product puts it back in range with fresh signal and evidence.
