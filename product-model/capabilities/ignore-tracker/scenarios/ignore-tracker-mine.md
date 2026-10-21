---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses It's mine - keep ignoring it for the tracker.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::device
- text: The Product stores an enduring ignore that can follow a best-effort address continuation.
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

# Mark a tracker as mine

## Trigger

The user chooses It's mine - keep ignoring it for the tracker.

## Outcome

The Product stores an enduring ignore that can follow a best-effort address continuation.
