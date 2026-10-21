---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Snooze or Mute on a car alert.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::more
- text: The Product saves a snooze using the configured duration.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Snoozed until
  actor: user
  contexts:
    main:
      place: car::more
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/MoreScreen.kt
---

# Snooze from the car

## Trigger

The user chooses Snooze or Mute on a car alert.

## Outcome

The Product saves a snooze using the configured duration.
