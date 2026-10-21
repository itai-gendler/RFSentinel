---
kind: alternate
routes:
  main: Main
steps:
- text: The user imports a file containing an address already kept locally.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device-history
- text: The Product keeps earliest first sighting, latest last sighting, maximum counts, either favorite mark, and
    existing nonempty annotations.
  kind: product
  entities:
  - entity: remembered-device
    effect: changes
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
  target: app/src/main/java/com/rfsentinel/app/util/DeviceHistoryImport.kt
---

# Merge an address already remembered

## Trigger

The user imports a file containing an address already kept locally.

## Outcome

The Product keeps earliest first sighting, latest last sighting, maximum counts, either favorite mark, and existing nonempty annotations.
