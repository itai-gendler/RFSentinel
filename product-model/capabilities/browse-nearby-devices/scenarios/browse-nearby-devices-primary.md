---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses a nearby-device filter or search.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The Product shows the retained observations with type, signal, evidence and new or returning status.
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
    - Following
  - entity: cell-tower
    effect: reads
    facts:
    - Identity
    - Serving
    - Signal
  - entity: waze-report
    effect: reads
    facts:
    - Type
    - Position
    - Age
    - Confirmations
    - Relevance
    - Confidence
    - Level
    - Source
  actor: user
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceFilter.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/LiveWindow.kt
---

# Browse nearby devices

## Trigger

The user chooses a nearby-device filter or search.

## Outcome

The Product shows the retained observations with type, signal, evidence and new or returning status.

## Edge cases

- No matching observations produces an empty result.
- Favorites and devices that may be following stay in the list for three minutes after they were last heard.
