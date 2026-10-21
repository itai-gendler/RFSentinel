---
kind: primary
routes:
  main: Main
steps:
- text: The user supplies a valid matching condition and a label.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::watchlist
- text: The Product retains the custom rule and makes it available to subsequent classification.
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
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/oui/OuiWatchlist.kt
---

# Add watchlist rule

## Trigger

The user supplies a valid matching condition and a label.

## Outcome

The Product retains the custom rule and makes it available to subsequent classification.

## Edge cases

- The form rejects an empty label or invalid matching condition.
- Undo restores the previous entry or removes the newly added entry.
