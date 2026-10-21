---
kind: primary
routes:
  main: Main
steps:
- text: The user adds the selected place as an intermediate stop.
  kind: actor
  entities:
  - entity: place
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product obtains and adopts a replacement route with that stop.
  kind: product
  entities:
  - entity: route
    effect: changes
    facts:
    - Stops
    - Path
    - Estimate
    - Progress
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
---

# Add route stop

## Trigger

The user adds the selected place as an intermediate stop.

## Outcome

The Product obtains and adopts a replacement route with that stop.

## Edge cases

- A failed replan keeps the old route and reports that no new route was obtained.
