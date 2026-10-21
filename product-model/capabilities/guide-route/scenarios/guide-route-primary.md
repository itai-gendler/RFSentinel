---
kind: primary
routes:
  main: Main
steps:
- text: A new location fix arrives during guidance.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product updates progress and the arrival estimate and supplies due guidance instructions.
  kind: product
  entities:
  - entity: route
    effect: changes
    facts:
    - Progress
    - Estimate
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Prompts.kt
---

# Guide along the route

## Trigger

A new location fix arrives during guidance.

## Outcome

The Product updates progress and the arrival estimate and supplies due guidance instructions.
