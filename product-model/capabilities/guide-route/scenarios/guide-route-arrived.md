---
kind: alternate
routes:
  main: Main
steps:
- text: The phone comes within 35 m of the destination, or stops within 120 m of it for 8 seconds.
  kind: condition
  entities:
  - entity: route
    effect: reads
    facts: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product says You have arrived at your destination and ends guidance.
  kind: product
  entities:
  - entity: route
    effect: removes
    from: Guiding
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

# Arrive at the destination

## Trigger

The user comes within 35 m of the destination, or stops within 120 m of it for 8 seconds.

## Outcome

The Product says You have arrived at your destination and ends guidance; a scan it started keeps running.
