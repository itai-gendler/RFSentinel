---
kind: alternate
routes:
  main: Main
steps:
- text: The user removes the custom entry associated with the selected observation.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product removes that custom matching condition.
  kind: product
  entities:
  - entity: watchlist-rule
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiListActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Remove a matching custom condition from device details

## Trigger

The user removes the custom entry associated with the selected observation.

## Outcome

The Product removes that custom matching condition.
