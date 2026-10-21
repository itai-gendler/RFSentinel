---
kind: alternate
routes:
  main: Main
steps:
- text: Live export is enabled, its folder is available and the next thirty-second update is due during scanning.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Data
  unattended: true
  contexts:
    main:
      place: phone::settings-data
- text: The Product rewrites current-session matches and current mapped observations in the selected folder.
  kind: product
  entities:
  - entity: match-history
    effect: reads
    facts:
    - Subject
    - Observation
    - Classification
    - Position
  - entity: nearby-device
    effect: reads
    facts:
    - Address
    - Name
    - Vendor
    - Type
    - Signal
    - Evidence
    - Seen
    - Position
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/LiveExport.kt
---

# Rewrite the live export files while scanning

## Trigger

Live export is enabled, its folder is available and the next thirty-second update is due during scanning.

## Outcome

The Product rewrites current-session matches and current mapped observations in the selected folder.

## Edge cases

- A missing folder or write failure appears in live-export status and can require choosing the folder again.
