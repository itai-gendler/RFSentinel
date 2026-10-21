---
kind: alternate
routes:
  main: Main
steps:
- text: The user opens a remembered address with no current observation.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product presents saved information and makes the absence of a current signal clear.
  kind: product
  entities:
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

# Review an address that is no longer nearby

## Trigger

The user opens a remembered address with no current observation.

## Outcome

The Product presents saved information and makes the absence of a current signal clear.
