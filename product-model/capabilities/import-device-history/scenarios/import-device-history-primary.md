---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses a readable history file.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device-history
- text: The Product merges valid device rows and reports new, updated, unchanged and skipped counts.
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

# Import device history

## Trigger

The user chooses a readable history file.

## Outcome

The Product merges valid device rows and reports new, updated, unchanged and skipped counts.

## Edge cases

- Invalid non-device rows are skipped.
- A file without device history is reported as not imported.
- The import does not restore traces or the match log from an everything export.
