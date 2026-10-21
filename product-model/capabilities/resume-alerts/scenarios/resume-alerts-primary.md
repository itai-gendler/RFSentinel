---
kind: primary
routes:
  main: Main
steps:
- text: The user asks for alert sound again.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The Product clears both persistent mute and the snooze expiry.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Alert mute
    - Snoozed until
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
  target: app/src/main/java/com/rfsentinel/app/car/MoreScreen.kt
---

# Resume alert sound

## Trigger

The user asks for alert sound again.

## Outcome

The Product clears both persistent mute and the snooze expiry.
