---
kind: alternate
routes:
  main: Main
steps:
- text: A Bluetooth device has not been heard for 8 seconds, or a WiFi device for one WiFi interval plus 10 seconds.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: "The Product marks it out of range: a flagged device stops alerting at once, and the device stays in the list for its configured time."
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    from: Heard
    to: Stale
    facts: []
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

# Mark a device out of range

## Trigger

A Bluetooth device has not been heard for 8 seconds, or a WiFi device for one WiFi interval plus 10 seconds.

## Outcome

The Product marks it out of range: a flagged device stops alerting at once, and the device stays in the list for its configured time.
