---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses a supported address, name-prefix or observed fingerprint scope.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product saves the chosen matching condition with its label and provenance.
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
      place: phone::device
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

# Watch an observed address or pattern

## Trigger

The user chooses a supported address, name-prefix or observed fingerprint scope.

## Outcome

The Product saves the chosen matching condition with its label and provenance.

## Edge cases

- A randomized address is offered as an exact address rather than an inferred vendor prefix.
