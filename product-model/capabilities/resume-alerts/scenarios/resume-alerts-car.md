---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Resume alert sound.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::more
- text: The Product clears mute and snooze.
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
      place: car::more
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/MoreScreen.kt
---

# Resume sound from the car

## Trigger

The user chooses Resume alert sound.

## Outcome

The Product clears mute and snooze.
