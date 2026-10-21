---
kind: primary
routes:
  main: Main
steps:
- text: The user confirms deletion of a personal theme.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product removes that appearance and returns to the system theme when it was selected.
  kind: product
  entities:
  - entity: custom-theme
    effect: removes
  - entity: preferences
    effect: changes
    facts:
    - Appearance
  actor: user
  contexts:
    main:
      place: phone::theme
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/ThemeMakerActivity.kt
---

# Delete custom theme

## Trigger

The user confirms deletion of a personal theme.

## Outcome

The Product removes that appearance and returns to the system theme when it was selected.
