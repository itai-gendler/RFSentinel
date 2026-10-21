---
kind: primary
routes:
  main: Main
steps:
- text: The user searches or filters remembered addresses.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device-history
- text: The Product shows up to five hundred newest matching addresses with their saved information.
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
      place: phone::device-history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceHistoryActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/KnownDeviceEntity.kt
---

# Browse device history

## Trigger

The user searches or filters remembered addresses.

## Outcome

The Product shows up to five hundred newest matching addresses with their saved information.

## Edge cases

- Flagged before is determined by the retained match log, so clearing or pruning that log affects this filter.
