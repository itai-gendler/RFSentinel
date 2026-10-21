---
kind: primary
routes:
  main: Main
steps:
- text: The user searches or filters logged matches.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::match-history
- text: The Product shows up to one thousand newest matching observations.
  kind: product
  entities:
  - entity: match-history
    effect: reads
    facts:
    - Subject
    - Observation
    - Classification
    - Position
  actor: user
  contexts:
    main:
      place: phone::match-history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DetectionLogActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/DetectionDao.kt
---

# Browse match history

## Trigger

The user searches or filters logged matches.

## Outcome

The Product shows up to one thousand newest matching observations.

## Edge cases

- Opening an online match uses its current location or its saved position; an unavailable unsaved position is reported.
