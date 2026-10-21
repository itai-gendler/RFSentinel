---
kind: primary
routes:
  main: Main
steps:
- text: The user saves the selected location as Home, Work or a favorite.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::places
- text: The Product retains the location and the selected saved-place role.
  kind: product
  entities:
  - entity: place
    effect: changes
    facts:
    - Saved as
  actor: user
  contexts:
    main:
      place: phone::places
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/NavSearchActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Save place

## Trigger

The user saves the selected location as Home, Work or a favorite.

## Outcome

The Product retains the location and the selected saved-place role.
