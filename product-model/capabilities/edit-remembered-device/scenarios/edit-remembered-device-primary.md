---
kind: primary
routes:
  main: Main
steps:
- text: The user saves an own name or note.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product keeps the edited annotation for subsequent review.
  kind: product
  entities:
  - entity: remembered-device
    effect: changes
    facts:
    - Own name
    - Note
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/DeviceNames.kt
---

# Edit remembered device

## Trigger

The user saves an own name or note.

## Outcome

The Product keeps the edited annotation for subsequent review.
