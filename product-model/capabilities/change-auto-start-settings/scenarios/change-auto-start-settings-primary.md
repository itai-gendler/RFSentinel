---
kind: primary
routes:
  main: Main
steps:
- text: The user changes one of the section's choices.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-auto-start
- text: The Product saves the change at once and applies it from then on.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Auto start
  actor: user
  contexts:
    main:
      place: phone::settings-auto-start
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Change auto-start settings

## Trigger

The user changes a choice in the Auto-start section of Settings.

## Outcome

The Product saves the change at once and applies it from then on.
