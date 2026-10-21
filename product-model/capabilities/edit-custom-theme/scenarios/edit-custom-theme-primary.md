---
kind: primary
routes:
  main: Main
steps:
- text: The user saves changes to an existing personal theme.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product keeps the changes and refreshes views when that appearance is in use.
  kind: product
  entities:
  - entity: custom-theme
    effect: changes
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
---

# Edit custom theme

## Trigger

The user saves changes to an existing personal theme.

## Outcome

The Product keeps the changes and refreshes views when that appearance is in use.
