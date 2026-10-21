---
kind: primary
routes:
  main: Main
steps:
- text: The phone or a connected receiver hears a device for the first time while scanning.
  kind: condition
  entities:
  - entity: scan
    effect: reads
    facts:
    - Receiver status
  - entity: preferences
    effect: reads
    facts:
    - Detection
  - entity: watchlist-rule
    effect: reads
    facts:
    - Match
    - Label
    - Source
    - Score
    - Category
    - Custom
  unattended: true
  contexts:
    main:
      place: phone::nearby
- text: The Product lists it with its address, name, vendor, type, radio and signal, checks it against the signatures and the watchlist, and shows its strongest match with evidence, source and confidence.
  kind: product
  entities:
  - entity: nearby-device
    effect: creates
    to: Heard
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
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/EvidenceFusion.kt
---

# Classify a newly heard device

## Trigger

The phone or a connected receiver hears a device for the first time while scanning.

## Outcome

The Product lists it with its address, name, vendor, type, radio and signal, checks it against the signatures and the watchlist, and shows its strongest match with evidence, source and confidence.

## Edge cases

- Independent supported clues can corroborate a match; patrol grouping does not corroborate the clues it was derived from.
- A private address can be linked to a recent observation by broadcast fingerprints; the link remains an inference.
