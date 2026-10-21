---
kind: primary
routes:
  main: Main
steps:
- text: The user selects Today only for a currently heard tracker.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product stores an ignore for the current address for at most twenty-four hours.
  kind: product
  entities:
  - entity: tracker-ignore
    effect: creates
    facts:
    - Address
    - Kind
    - Mode
    - Until
    - Last heard
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceActions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/TrackerMutes.kt
---

# Ignore a tracker today only

## Trigger

The user selects Today only for a currently heard tracker.

## Outcome

The Product stores an ignore for the current address for at most twenty-four hours.
