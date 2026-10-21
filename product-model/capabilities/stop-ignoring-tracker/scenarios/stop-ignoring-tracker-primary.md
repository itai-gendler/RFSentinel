---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses Stop ignoring.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product removes the ignore for the selected tracker address.
  kind: product
  entities:
  - entity: tracker-ignore
    effect: removes
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

# Stop ignoring tracker

## Trigger

The user chooses Stop ignoring.

## Outcome

The Product removes the ignore for the selected tracker address.
