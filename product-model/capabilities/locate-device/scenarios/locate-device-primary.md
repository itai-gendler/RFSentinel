---
kind: primary
routes:
  main: Main
steps:
- text: The user starts Locate for a live observation.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product turns on proximity audio whose interval follows signal strength.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    facts:
    - Locate active
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
---

# Locate device

## Trigger

The user starts Locate for a live observation.

## Outcome

The Product turns on proximity audio whose interval follows signal strength.

## Edge cases

- Locate ends when the view pauses or the observed signal is no longer available.
- Audio initiated by Locate follows its own control rather than the alert mute.
