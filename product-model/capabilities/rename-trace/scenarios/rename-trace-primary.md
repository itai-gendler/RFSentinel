---
kind: primary
routes:
  main: Main
steps:
- text: The user saves a new recording name.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::traces
- text: The Product keeps the trimmed name, using Trace when it is empty.
  kind: product
  entities:
  - entity: trace
    effect: changes
    facts:
    - Name
  actor: user
  contexts:
    main:
      place: phone::traces
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/TripsActivity.kt
---

# Rename recorded trace

## Trigger

The user saves a new recording name.

## Outcome

The Product keeps the trimmed name, using Trace when it is empty.
