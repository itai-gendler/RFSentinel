---
kind: alternate
routes:
  main: Main
steps:
- text: A receiver supplies another part of a Remote ID broadcast.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::device
- text: The Product merges the reported fields into the current drone information.
  kind: product
  entities:
  - entity: drone
    effect: creates
    facts:
    - Identification
    - Position
    - Operator position
    - Last heard
  contexts:
    main:
      place: phone::device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/RemoteId.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DeviceDetailActivity.kt
---

# Decode a drone's Remote ID broadcast

## Trigger

A receiver supplies another part of a Remote ID broadcast.

## Outcome

The Product merges the reported fields into the current drone information.
