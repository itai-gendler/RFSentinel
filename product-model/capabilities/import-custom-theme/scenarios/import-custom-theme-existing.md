---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses an existing theme as the import destination.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product replaces only the selected portions.
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
  target: app/src/main/java/com/rfsentinel/app/ui/ThemeImport.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/CustomTheme.kt
---

# Import into an existing custom theme

## Trigger

The user chooses an existing theme as the import destination.

## Outcome

The Product replaces only the selected portions.
