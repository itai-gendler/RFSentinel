---
kind: primary
routes:
  main: Main
steps:
- text: The user selects an encounter period or equipment category.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::history
- text: The Product groups observations into encounters and presents their available locations and time patterns.
  kind: product
  entities:
  - entity: match-history
    effect: reads
    facts:
    - Subject
    - Observation
    - Classification
    - Position
  - entity: trace
    effect: reads
    facts:
    - Name
    - Times
    - Route
    - Devices
    - Counts
  actor: user
  contexts:
    main:
      place: phone::history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/HistoryActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/history/History.kt
---

# Browse encounter history

## Trigger

The user selects an encounter period or equipment category.

## Outcome

The Product groups observations into encounters and presents their available locations and time patterns.

## Edge cases

- A continuous chain of sightings of the same address separated by no more than ten minutes is one encounter.
- An encounter uses the first available position; unpositioned encounters still contribute to the time summaries.
