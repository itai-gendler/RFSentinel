---
kind: alternate
routes:
  main: Main
steps:
- text: A received advertisement or beacon matches an enabled built-in or custom condition.
  kind: condition
  unattended: true
  entities: []
  contexts:
    main:
      place: phone::nearby
- text: The Product records the matching name, payload, service identifier, company identifier or vendor-prefix
    evidence and its source.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    facts:
    - Evidence
    - Decoded data
    - Type
  contexts:
    main:
      place: phone::nearby
references:
- kind: spec
  role: intent
  target: docs/SIGNATURES.md
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/SignatureEngine.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Match a broadcast signature

## Trigger

A received advertisement or beacon matches an enabled built-in or custom condition.

## Outcome

The Product records the matching name, payload, service identifier, company identifier or vendor-prefix evidence and its source.

## Edge cases

- Equipment categories include body cameras, plate readers, audio sensors, public-safety gear, trackers, drones, glasses, skimmer candidates and optional camera or hacking-tool clues.
- Ordinary devices can retain decoded identity clues without a flagged match.
