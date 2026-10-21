---
kind: primary
routes:
  main: Main
steps:
- text: The enabled ADS-B source supplies new ADS-B observations.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Detection
    - Radio
  unattended: true
  contexts:
    main:
      place: phone::aircraft
- text: The Product retains current aircraft information and evaluates qualifying matches.
  kind: product
  entities:
  - entity: aircraft
    effect: creates
    facts:
    - Identification
    - Position
    - Source
    - Evidence
    - Time
  contexts:
    main:
      place: phone::aircraft
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/OnlineWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/online/PoliceAircraft.kt
---

# Receive aircraft reports

## Trigger

The enabled ADS-B source supplies new ADS-B observations.

## Outcome

The Product retains current aircraft information and evaluates qualifying matches.

## Edge cases

- Online polling waits for a location and reports when all configured feed attempts fail.
- A local ADS-B source can work without the online feed.
- Registry attribution and circling observations remain evidence, not identification of a mission.
