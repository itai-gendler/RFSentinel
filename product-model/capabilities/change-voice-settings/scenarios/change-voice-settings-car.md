---
kind: alternate
routes:
  main: Main
steps:
- text: The user changes car speech or short spoken alerts.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::more
- text: The Product saves the chosen car voice preferences.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Voice
  actor: user
  contexts:
    main:
      place: car::more
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/MoreScreen.kt
---

# Change car spoken alerts

## Trigger

The user changes car speech or short spoken alerts.

## Outcome

The Product saves the chosen car voice preferences.
