---
kind: primary
routes:
  main: Main
steps:
- text: The user opens Aircraft and selects a filter.
  kind: actor
  entities:
  - entity: aircraft
    effect: reads
    facts: []
  actor: user
  contexts:
    main:
      place: phone::aircraft
- text: The Product presents available aircraft, positions, sources and evidence.
  kind: product
  entities:
  - entity: aircraft
    effect: reads
    facts:
    - Identification
    - Position
    - Source
    - Evidence
    - Time
  actor: user
  contexts:
    main:
      place: phone::aircraft
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/AircraftActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/PoliceAircraft.kt
---

# Browse aircraft

## Trigger

The user opens Aircraft and selects a filter.

## Outcome

The Product presents available aircraft, positions, sources and evidence.

## Edge cases

- Reports without usable positions are distinguished from plotted aircraft.
