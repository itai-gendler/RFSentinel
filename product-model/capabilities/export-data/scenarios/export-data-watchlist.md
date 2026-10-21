---
kind: alternate
routes:
  main: Main
steps:
- text: The user exports their custom entries.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::watchlist
- text: The Product supplies the custom matching conditions as a watchlist file.
  kind: product
  entities:
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
      place: phone::watchlist
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

# Export custom watchlist entries

## Trigger

The user exports their custom entries.

## Outcome

The Product supplies the custom matching conditions as a watchlist file.
