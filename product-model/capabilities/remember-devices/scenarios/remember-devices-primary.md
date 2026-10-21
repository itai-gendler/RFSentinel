---
kind: primary
routes:
  main: Main
steps:
- text: About once a minute while scanning, an address heard since the last time is not yet in the device history.
  kind: condition
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Address
    - Name
    - Vendor
    - Type
    - Seen
  unattended: true
  contexts:
    main:
      place: phone::device-history
- text: The Product adds it to the device history with its first and last sighting, one session, one sighting and its name, vendor and type.
  kind: product
  entities:
  - entity: remembered-device
    effect: creates
    facts:
    - Address
    - Name
    - Vendor
    - Type
    - First seen
    - Last seen
    - Sessions
    - Sightings
    - Favorite
    - Own name
    - Note
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

# Remember devices

## Trigger

About once a minute while scanning, an address heard since the last time is not yet in the device history.

## Outcome

The Product adds it to the device history with its first and last sighting, one session, one sighting and its name, vendor and type.
