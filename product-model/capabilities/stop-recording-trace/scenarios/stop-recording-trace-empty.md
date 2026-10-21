---
kind: alternate
routes:
  main: Main
steps:
- text: Recording ends with no location points and no devices.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::map
- text: The Product removes the empty recording.
  kind: product
  entities:
  - entity: trace
    effect: removes
    from: Recording
  contexts:
    main:
      place: phone::map
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/MapActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/TripRecorder.kt
---

# Discard an empty trace

## Trigger

Recording ends with no location points and no devices.

## Outcome

The Product removes the empty recording.
