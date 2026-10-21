---
kind: alternate
routes:
  main: Main
steps:
- text: About once a minute while scanning, a device already in the device history was heard again.
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
- text: The Product moves its last sighting forward, adds one sighting, adds a session only once per scanning session, and keeps its favorite mark, own name and note.
  kind: product
  entities:
  - entity: remembered-device
    effect: changes
    facts:
    - Last seen
    - Sessions
    - Sightings
    - Name
    - Vendor
    - Type
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

# Update a remembered device heard again

## Trigger

About once a minute while scanning, a device already in the device history was heard again.

## Outcome

The Product moves its last sighting forward, adds one sighting, adds a session only the first time in this scan, and keeps its favorite mark, own name and note.
