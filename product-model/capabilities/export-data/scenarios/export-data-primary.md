---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses an export scope and a supported format.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-data
- text: The Product produces the selected local data and opens the share chooser.
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
  - entity: match-history
    effect: reads
    facts:
    - Subject
    - Observation
    - Classification
    - Position
  - entity: watchlist-rule
    effect: reads
    facts:
    - Match
    - Label
    - Source
    - Score
    - Category
    - Custom
  actor: user
  contexts:
    main:
      place: phone::settings-data
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

# Export data

## Trigger

The user chooses an export scope and a supported format.

## Outcome

The Product produces the selected local data and opens the share chooser.

## Edge cases

- Empty scopes report that no data is available.
- A map format requiring coordinates reports missing positions.
- Write or memory failures are reported as export failures.
- Remembered history offers CSV and JSON; traces offer GPX, KML, GeoJSON and CSV; the combined export is JSON.
