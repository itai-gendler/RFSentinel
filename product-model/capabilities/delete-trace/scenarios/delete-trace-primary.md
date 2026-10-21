---
kind: primary
routes:
  main: Main
steps:
- text: The user confirms deleting a completed recording.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::traces
- text: The Product removes the saved travel path and its recorded device list.
  kind: product
  entities:
  - entity: trace
    effect: removes
    from: Saved
  actor: user
  contexts:
    main:
      place: phone::traces
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/TripsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/Trips.kt
---

# Delete recorded trace

## Trigger

The user confirms deleting a completed recording.

## Outcome

The Product removes the saved travel path and its recorded device list.
