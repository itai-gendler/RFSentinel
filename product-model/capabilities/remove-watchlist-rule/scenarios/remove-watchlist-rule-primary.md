---
kind: primary
routes:
  main: Main
steps:
- text: The user removes a custom watch entry.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::watchlist
- text: The Product removes that custom condition and offers Undo.
  kind: product
  entities:
  - entity: watchlist-rule
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::watchlist
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiListActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Remove watchlist rule

## Trigger

The user removes a custom watch entry.

## Outcome

The Product removes that custom condition and offers Undo.
