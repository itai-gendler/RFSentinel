---
kind: primary
routes:
  main: Main
steps:
- text: The user selects the desired portions of a readable shared appearance.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product retains those portions in a new personal theme.
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
  target: app/src/main/java/com/rfsentinel/app/ui/ThemeImport.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/CustomTheme.kt
---

# Import custom theme

## Trigger

The user selects the desired portions of a readable shared appearance.

## Outcome

The Product retains those portions in a new personal theme.

## Edge cases

- A damaged or unsupported file is reported as not imported.
- Unticked portions of an existing theme remain unchanged.
