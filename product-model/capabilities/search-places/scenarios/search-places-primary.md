---
kind: primary
routes:
  main: Main
steps:
- text: The user enters a destination query.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::places
- text: The Product shows matching saved places and available external place results.
  kind: product
  entities:
  - entity: place
    effect: creates
    facts:
    - Name
    - Address
    - Position
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
  target: app/src/main/java/com/rfsentinel/app/nav/Places.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/PlaceCategories.kt
---

# Search places

## Trigger

The user enters a destination query.

## Outcome

The Product shows matching saved places and available external place results.

## Edge cases

- A coordinate pair can be used directly as a destination.
- Submitted searches combine the supported place services; typing uses the supported suggestion service.
- A failed lookup reports the failure and retains available local or prior matching results.
