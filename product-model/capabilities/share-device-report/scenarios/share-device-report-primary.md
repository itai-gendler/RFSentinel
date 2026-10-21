---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses the full device report.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product provides the displayed device information to the Android share chooser.
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
---

# Share device report

## Trigger

The user chooses the full device report.

## Outcome

The Product provides the displayed device information to the Android share chooser.
