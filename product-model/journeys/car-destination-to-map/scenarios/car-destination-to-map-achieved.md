---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The user chooses the destination.
  kind: actor
  entities:
  - entity: place
    effect: reads
    facts:
    - Name
    - Address
    - Position
    - Saved as
  capability: start-guidance
  actor: user
  contexts:
    main:
      place: car::places
- text: The Product obtains directions and returns to the live map.
  kind: product
  entities:
  - entity: route
    effect: creates
    to: Guiding
    facts: &id001
    - Destination
    - Stops
    - Path
    - Estimate
    - Options
    - Progress
  capability: start-guidance
  actor: user
  contexts:
    main:
      place: car::map
- text: The user reviews surroundings on the guidance map.
  kind: actor
  entities:
  - entity: route
    effect: reads
    facts: *id001
  capability: browse-map
  actor: user
  contexts:
    main:
      place: car::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DestinationScreen.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/LiveMapScreen.kt
---

# Choose a car destination and follow the map

## Trigger

The user selects a destination in the car.

## Outcome

Guidance starts and the car returns to the live navigation map.
