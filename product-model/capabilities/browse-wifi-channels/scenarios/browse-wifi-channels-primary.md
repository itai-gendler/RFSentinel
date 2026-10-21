---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses a WiFi band or requests a refresh.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::wifi
- text: The Product shows the observed access-point channel and signal information for that band.
  kind: product
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Name
    - Signal
    - Decoded data
  actor: user
  contexts:
    main:
      place: phone::wifi
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/WifiAnalyzerActivity.kt
---

# Browse WiFi channels

## Trigger

The user chooses a WiFi band or requests a refresh.

## Outcome

The Product shows the observed access-point channel and signal information for that band.

## Edge cases

- If Android refuses a fresh scan, existing available results remain subject to their observed freshness.
