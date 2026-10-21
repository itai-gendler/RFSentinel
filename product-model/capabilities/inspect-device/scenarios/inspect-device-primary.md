---
kind: primary
routes:
  main: Main
steps:
- text: The user opens one observed address.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product presents its signal, matches, confidence, source, decoded fields and remembered information.
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
    - Linked address
    - Locate active
  - entity: remembered-device
    effect: reads
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
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceDetailScreen.kt
---

# Inspect device

## Trigger

The user opens one observed address.

## Outcome

The Product presents its signal, matches, confidence, source, decoded fields and remembered information.
