---
kind: alternate
routes:
  main: Main
steps:
- text: A location fix arrives during projected guidance.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: car::map
- text: The Product updates remaining distance, time and the next instruction in the car.
  kind: product
  entities:
  - entity: route
    effect: changes
    facts:
    - Progress
    - Estimate
  contexts:
    main:
      place: car::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Prompts.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/LiveMapScreen.kt
---

# Guide on the car screen

## Trigger

A location fix arrives during projected guidance.

## Outcome

The Product updates remaining distance, time and the next instruction in the car.
