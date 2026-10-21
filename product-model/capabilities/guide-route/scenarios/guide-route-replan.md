---
kind: alternate
routes:
  main: Main
steps:
- text: The phone has been more than 60 m off the planned way for 5 seconds, or going the wrong way along it for 8 seconds.
  kind: condition
  entities:
  - entity: route
    effect: reads
    facts: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product says Re-routing and asks for a new way from the current position, keeping the current one until it arrives.
  kind: product
  entities:
  - entity: route
    effect: changes
    from: Guiding
    to: Replanning
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

# Re-route after leaving the route

## Trigger

The user has been more than 60 m off the route for 5 seconds, or going the wrong way along it for 8 seconds.

## Outcome

The Product says Re-routing and asks for a new route from where the user is, keeping the current route until one arrives.
