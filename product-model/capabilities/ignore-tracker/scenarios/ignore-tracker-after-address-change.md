---
kind: alternate
routes:
  main: Main
steps:
- text: A tag marked as mine changes its address.
  kind: condition
  entities: []
  unattended: true
  contexts:
    main:
      place: phone::device
- text: The Product carries the ignore to the new address and refreshes the last-heard evidence.
  kind: product
  entities:
  - entity: tracker-ignore
    effect: changes
    facts:
    - Address
    - Last heard
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

# Keep ignoring a tracker after its address changes

## Trigger

A tag the user marked as mine changes its address.

## Outcome

The Product carries the ignore to the new address and refreshes the last-heard evidence.
