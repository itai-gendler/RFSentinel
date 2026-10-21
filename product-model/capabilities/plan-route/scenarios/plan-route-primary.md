---
kind: primary
routes:
  main: Main
steps:
- text: The user asks for directions to a selected destination.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product offers available route alternatives with distance, duration and camera information.
  kind: product
  entities:
  - entity: route
    effect: creates
    to: Preview
    facts:
    - Destination
    - Stops
    - Path
    - Estimate
    - Options
    - Progress
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

# Plan route

## Trigger

The user asks for directions to a selected destination.

## Outcome

The Product offers available route alternatives with distance, duration and camera information.

## Edge cases

- A missing location keeps route planning pending with an explanation.
- If an options change cannot obtain a replacement, previously offered routes remain available.
- Camera avoidance uses mapped coverage and does not promise that every camera can be avoided.
