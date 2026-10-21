---
kind: alternate
routes:
  main: Main
steps:
- text: The user stops watching a requested name.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::requested-networks
- text: The Product removes the corresponding custom matching condition.
  kind: product
  entities:
  - entity: watchlist-rule
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::requested-networks
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiListActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Stop watching a requested network

## Trigger

The user stops watching a requested name.

## Outcome

The Product removes the corresponding custom matching condition.
