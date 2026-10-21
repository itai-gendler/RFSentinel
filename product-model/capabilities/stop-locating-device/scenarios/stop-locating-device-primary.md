---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses Stop in Locate.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product ends proximity audio for the selected observation.
  kind: product
  entities:
  - entity: nearby-device
    effect: changes
    facts:
    - Locate active
  actor: user
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
---

# Stop locating device

## Trigger

The user chooses Stop in Locate.

## Outcome

The Product ends proximity audio for the selected observation.
