---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses a destination with a current location available.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::places
- text: The Product plans and begins guidance, then returns the user to the live map.
  kind: product
  entities:
  - entity: route
    effect: creates
    to: Guiding
    facts:
    - Destination
    - Stops
    - Path
    - Estimate
    - Options
    - Progress
  - entity: place
    effect: changes
    facts:
    - Saved as
  actor: user
  contexts:
    main:
      place: car::places
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapNav.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DestinationScreen.kt
---

# Start directions from a car destination

## Trigger

The user chooses a destination with a current location available.

## Outcome

The Product plans and begins guidance, then returns the user to the live map.

## Edge cases

- A route-service failure leaves the destination view available and reports why directions could not start.
