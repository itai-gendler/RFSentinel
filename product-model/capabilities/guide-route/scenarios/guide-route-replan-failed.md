---
kind: edge
routes:
  main: Main
steps:
- text: Re-routing fails, for example with no signal, while guidance is still on.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product keeps the old route on screen, shows that no new route was found and waits a little longer before each next try.
  kind: product
  entities:
  - entity: route
    effect: changes
    from: Replanning
    to: Guiding
    facts:
    - Progress
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

# Keep the old route when re-routing fails

## Trigger

The request for a new route fails, for example with no signal, while guidance is still on.

## Outcome

The Product keeps the old route on screen, shows that no new route was found and waits a little longer before each next try.
