---
kind: alternate
routes:
  main: Main
steps:
- text: The user submits a destination search in Android Auto.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::places
- text: The Product shows matching saved and online places within the host’s result limit.
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
      place: car::places
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
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DestinationScreen.kt
---

# Submit a destination search in the car

## Trigger

The user submits a destination search in Android Auto.

## Outcome

The Product shows matching saved and online places within the host’s result limit.

## Edge cases

- Typing alone does not send a car destination query.
