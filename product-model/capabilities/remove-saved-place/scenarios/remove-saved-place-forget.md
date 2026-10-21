---
kind: alternate
routes:
  main: Main
steps:
- text: The user confirms forgetting saved navigation destinations.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-navigation
- text: The Product removes the retained Home, Work, starred and recent destinations.
  kind: product
  entities:
  - entity: place
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::settings-navigation
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

# Forget saved navigation places

## Trigger

The user confirms forgetting saved navigation places.

## Outcome

The Product removes the retained Home, Work, starred and recent destinations.
