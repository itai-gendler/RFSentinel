---
kind: primary
routes:
  main: Main
steps:
- text: The user confirms a label and selects usable observed clues.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product adds custom entries for the selected exact address or stable patterns.
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
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
---

# Learn device

## Trigger

The user confirms a label and selects usable observed clues.

## Outcome

The Product adds custom entries for the selected exact address or stable patterns.

## Edge cases

- Patterns shared by four or more observed devices are not offered as usable clues.
- An already watched clue is not added again.
- If nothing stable is available or selected, the application reports that nothing was learned.
