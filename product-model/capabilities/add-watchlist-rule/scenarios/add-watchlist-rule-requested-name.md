---
kind: alternate
routes:
  main: Main
steps:
- text: The user supplies a label for an observed requested network name.
  kind: actor
  entities:
  - entity: requested-network
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: phone::requested-networks
- text: The Product adds an exact requested-name matching condition.
  kind: product
  entities:
  - entity: watchlist-rule
    effect: creates
    facts:
    - Match
    - Label
    - Source
    - Score
    - Category
    - Custom
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
---

# Watch a requested network name

## Trigger

The user supplies a label for an observed requested network name.

## Outcome

The Product adds an exact requested-name matching condition.
