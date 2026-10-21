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
      place: phone::settings-what-to-detect
- text: The Product saves the change at once and applies it from then on.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Detection
    - Aircraft enabled
    - Waze ready
    - Online aircraft enabled
    - Cell checks enabled
    - Satellite checks enabled
  actor: user
  contexts:
    main:
      place: phone::settings-what-to-detect
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Change what to detect settings

## Trigger

The user changes a choice in the What to detect section of Settings.

## Outcome

The Product saves the change at once and applies it from then on.
