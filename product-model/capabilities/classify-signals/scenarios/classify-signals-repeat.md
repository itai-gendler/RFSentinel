---
kind: alternate
routes:
  main: Main
steps:
- text: A device already in the live list is heard again.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product updates its signal and evidence, keeping broadcast details it sent earlier.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    from: Heard
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

# Refresh a device heard again

## Trigger

A device already in the live list is heard again.

## Outcome

The Product updates its signal and evidence, keeping broadcast details it sent earlier.
