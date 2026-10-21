---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses the twenty-four-hour tracker-follow pause.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product saves the pause expiry.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Tracker warnings paused until
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Pause tracker warnings

## Trigger

The user chooses the twenty-four-hour tracker-follow pause.

## Outcome

The Product saves the pause expiry.
