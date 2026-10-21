---
kind: primary
routes:
  main: Main
steps:
- text: The user clears a saved favorite.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::places
- text: The Product removes its starred-place status.
  kind: product
  entities:
  - entity: place
    effect: changes
    facts:
    - Saved as
  actor: user
  contexts:
    main:
      place: phone::places
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/NavSearchActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Remove saved place

## Trigger

The user clears a saved favorite.

## Outcome

The Product removes its starred-place status.
