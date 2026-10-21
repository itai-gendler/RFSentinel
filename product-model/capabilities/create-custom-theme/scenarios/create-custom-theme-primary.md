---
kind: primary
routes:
  main: Main
steps:
- text: The user saves a new personal theme.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product retains the named appearance and selected assets.
  kind: product
  entities:
  - entity: custom-theme
    effect: creates
    facts:
    - Name
    - Appearance
    - Font
    - Banner
    - Header
    - Marker
  actor: user
  contexts:
    main:
      place: phone::theme
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/ThemeMakerActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/CustomTheme.kt
---

# Create custom theme

## Trigger

The user saves a new personal theme.

## Outcome

The Product retains the named appearance and selected assets.

## Edge cases

- The custom-theme limit prevents saving another new theme until one is deleted.
