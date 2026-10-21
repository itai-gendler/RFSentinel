---
kind: alternate
routes:
  main: Main
steps:
- text: Scanning starts with a retention period set, and a device in the device history that is not a favorite, has no own name and no note was last heard longer ago than that period.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Data
  unattended: true
  contexts:
    main:
      place: phone::device-history
- text: The Product removes it from the device history.
  kind: product
  entities:
  - entity: remembered-device
    effect: removes
  contexts:
    main:
      place: phone::device-history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/KnownDeviceEntity.kt
---

# Forget remembered devices past the retention period

## Trigger

A scan starts with a retention period set, and a remembered device that is not a favorite, has no own name and no note was last heard longer ago than that period.

## Outcome

The Product removes it from the device history.
