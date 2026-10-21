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
      place: phone::settings-appearance
- text: The Product saves the change at once and applies it from then on.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Appearance
  actor: user
  contexts:
    main:
      place: phone::settings-appearance
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Change appearance settings

## Trigger

The user changes a choice in the Appearance section of Settings.

## Outcome

The Product saves the change at once and applies it from then on.
