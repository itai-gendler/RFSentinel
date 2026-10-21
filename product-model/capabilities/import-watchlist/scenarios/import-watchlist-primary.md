---
kind: primary
routes:
  main: Main
steps:
- text: The user selects a watchlist file.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::watchlist
- text: The Product imports valid custom entries and reports the imported count.
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
      place: phone::watchlist
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ouilist/OuiListActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
---

# Import watchlist rules

## Trigger

The user selects a watchlist file.

## Outcome

The Product imports valid custom entries and reports the imported count.

## Edge cases

- An unreadable or invalid file is reported without claiming a successful import.
- A matching custom key is replaced rather than duplicated.
