---
kind: primary
routes:
  main: Main
steps:
- text: The user searches the active watchlist.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::watchlist
- text: The Product presents matching entries, with custom entries first and preset entries ordered by confidence.
  kind: product
  entities:
  - entity: watchlist-rule
    effect: reads
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
      place: phone::watchlist
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiListActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiEntry.kt
---

# Browse watchlist rules

## Trigger

The user searches the active watchlist.

## Outcome

The Product presents matching entries, with custom entries first and preset entries ordered by confidence.
