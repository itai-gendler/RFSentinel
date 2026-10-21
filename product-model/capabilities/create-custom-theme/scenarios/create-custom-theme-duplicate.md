---
kind: alternate
routes:
  main: Main
steps:
- text: The user duplicates a saved personal theme.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product creates a distinct copy and opens it for editing.
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

# Duplicate a custom theme

## Trigger

The user duplicates a saved personal theme.

## Outcome

The Product creates a distinct copy and opens it for editing.
