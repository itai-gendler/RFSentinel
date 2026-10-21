---
kind: alternate
routes:
  main: Main
steps:
- text: A requested replacement route succeeds for the current navigation.
  kind: condition
  entities:
  - entity: route
    effect: reads
    facts: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product adopts the new path and resumes guidance.
  kind: product
  entities:
  - entity: route
    effect: changes
    from: Replanning
    to: Guiding
    facts:
    - Path
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

# Continue on the replacement route

## Trigger

A requested replacement route succeeds for the current navigation.

## Outcome

The Product adopts the new path and resumes guidance.
