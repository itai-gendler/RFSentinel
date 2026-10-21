---
kind: alternate
routes:
  main: Main
steps:
- text: The user stops the current car navigation.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::map
- text: The Product ends the active directions.
  kind: product
  entities:
  - entity: route
    effect: removes
    from: Guiding
  actor: user
  contexts:
    main:
      place: car::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapNav.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/LiveMapScreen.kt
---

# End car guidance

## Trigger

The user stops the current car navigation.

## Outcome

The Product ends the active directions.
