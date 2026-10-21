---
kind: edge
routes:
  main: Main
steps:
- text: The user requests directions but the service cannot supply directions.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product reports the routing failure and retains the selected place for another attempt.
  kind: product
  entities:
  - entity: place
    effect: reads
    facts:
    - Name
    - Address
    - Position
    - Saved as
  actor: user
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapNav.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/CameraAvoid.kt
---

# Report that no route could be planned

## Trigger

The user requests directions but the service cannot supply directions.

## Outcome

The Product reports the routing failure and retains the selected place for another attempt.
