---
kind: alternate
routes:
  main: Main
steps:
- text: The user exports the currently retained observations.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The Product supplies current observation details, including available signal history and positions.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
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
    - Following
  - entity: remembered-device
    effect: reads
    facts:
    - Favorite
    - First seen
    - Sessions
    - Sightings
  - entity: whitelist-entry
    effect: reads
    facts:
    - Address
  actor: user
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Exporter.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/DeviceExport.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/TripExport.kt
---

# Export nearby observations

## Trigger

The user exports the currently retained observations.

## Outcome

The Product supplies current observation details, including available signal history and positions.
