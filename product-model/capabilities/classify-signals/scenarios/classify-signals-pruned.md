---
kind: alternate
routes:
  main: Main
steps:
- text: A device has not been heard for three minutes.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product drops it from the live list; it stays in the device history.
  kind: product
  entities:
  - entity: nearby-device
    effect: removes
    from: Stale
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

# Forget a device unheard for three minutes

## Trigger

A device has not been heard for three minutes.

## Outcome

The Product drops it from the live list; it stays in the device history.
