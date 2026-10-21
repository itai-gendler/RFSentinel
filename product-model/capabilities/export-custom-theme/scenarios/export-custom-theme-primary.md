---
kind: primary
routes:
  main: Main
steps:
- text: The user exports a saved personal theme.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product supplies the shared theme file.
  kind: product
  entities:
  - entity: custom-theme
    effect: reads
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

# Export custom theme

## Trigger

The user exports a saved personal theme.

## Outcome

The Product supplies the shared theme file.
