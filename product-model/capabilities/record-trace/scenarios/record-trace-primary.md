---
kind: primary
routes:
  main: Main
steps:
- text: The user starts trace recording.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::map
- text: The Product opens a new recording with a default name and begins accumulating locations and device observations.
  kind: product
  entities:
  - entity: trace
    effect: creates
    to: Recording
    facts:
    - Name
    - Times
    - Route
    - Devices
    - Counts
  actor: user
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

# Record trace

## Trigger

The user starts trace recording.

## Outcome

The Product opens a new recording with a default name and begins accumulating locations and device observations.

## Edge cases

- Only one trace is active at a time.
- Recorded locations reject poor accuracy and are spaced by movement or elapsed time.
