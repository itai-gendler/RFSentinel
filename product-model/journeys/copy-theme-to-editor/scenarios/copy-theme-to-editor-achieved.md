---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The user duplicates the saved appearance.
  kind: actor
  entities: []
  capability: create-custom-theme
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product creates a copy and opens it for editing.
  kind: product
  entities:
  - entity: custom-theme
    effect: creates
    facts: &id001
    - Name
    - Appearance
    - Font
    - Banner
    - Header
    - Marker
  capability: create-custom-theme
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The user changes the copied appearance.
  kind: actor
  entities: []
  capability: edit-custom-theme
  actor: user
  contexts:
    main:
      place: phone::theme
- text: The Product saves the edited copy.
  kind: product
  entities:
  - entity: custom-theme
    effect: changes
    facts: *id001
  capability: edit-custom-theme
  actor: user
  contexts:
    main:
      place: phone::theme
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/ThemeMakerActivity.kt
---

# Duplicate a theme and edit the copy

## Trigger

The user wants a personal variant of a saved appearance.

## Outcome

A distinct copy is opened and saved with the user’s changes.
