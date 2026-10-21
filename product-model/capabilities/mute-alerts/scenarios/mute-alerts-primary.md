---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses the persistent mute.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The Product keeps alert sound and speech muted.
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
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Mute alerts

## Trigger

The user chooses the persistent mute.

## Outcome

The Product keeps alert sound and speech muted.
