---
kind: primary
routes:
  main: Main
steps:
- text: The user saves a replacement destination name.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::places
- text: The Product keeps the personal label for the saved location.
  kind: product
  entities:
  - entity: place
    effect: changes
    facts:
    - Name
  actor: user
  contexts:
    main:
      place: phone::places
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/RenamePlace.kt
---

# Rename place

## Trigger

The user saves a replacement destination name.

## Outcome

The Product keeps the personal label for the saved location.
