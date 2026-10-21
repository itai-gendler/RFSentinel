---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses a snooze duration.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The Product saves the snooze expiry and stops queued alert speech.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Snoozed until
    - Alert mute
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
  target: app/src/main/java/com/rfsentinel/app/receiver/AlertActionReceiver.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Snooze alerts

## Trigger

The user chooses a snooze duration.

## Outcome

The Product saves the snooze expiry and stops queued alert speech.

## Edge cases

- Available snooze lengths range from five to sixty minutes.
- Expiry restores alert sound automatically unless the persistent mute remains set.
