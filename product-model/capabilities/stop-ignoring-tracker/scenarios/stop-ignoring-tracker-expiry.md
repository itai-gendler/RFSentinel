---
kind: alternate
routes:
  main: Main
steps:
- text: A temporary ignore has expired when tracker observations are processed.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::device
- text: The Product removes the expired ignore.
  kind: product
  entities:
  - entity: tracker-ignore
    effect: removes
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

# End a today-only ignore after 24 hours

## Trigger

A temporary ignore has expired when tracker observations are processed.

## Outcome

The Product removes the expired ignore.
