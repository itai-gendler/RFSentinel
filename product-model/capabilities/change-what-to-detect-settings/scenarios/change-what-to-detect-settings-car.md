---
kind: alternate
routes:
  main: Main
steps:
- text: The user changes whether the applicable tracker broadcasts count as trackers.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::more
- text: The Product saves the exclusion choice.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Detection
  actor: user
  contexts:
    main:
      place: car::more
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/MoreScreen.kt
---

# Change whether AirTags count as trackers

## Trigger

The user changes whether the applicable tracker broadcasts count as trackers.

## Outcome

The Product saves the exclusion choice.
