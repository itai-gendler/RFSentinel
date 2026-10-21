---
kind: primary
routes:
  main: Main
steps:
- text: The user ends navigation.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product clears the active route and stops guidance.
  kind: product
  entities:
  - entity: route
    effect: removes
    from: Guiding
  actor: user
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapNav.kt
---

# Stop guidance

## Trigger

The user ends navigation.

## Outcome

The Product clears the active route and stops guidance.
