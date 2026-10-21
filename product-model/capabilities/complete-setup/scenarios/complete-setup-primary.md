---
kind: primary
routes:
  main: Main
steps:
- text: The user finishes the initial choices.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::setup
- text: The Product keeps the chosen initial preferences and returns to the main application.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Setup complete
    - Appearance
    - Detection
    - Alerts
    - Voice
    - Floating views
    - Auto start
    - Known cameras
    - Cell towers
    - Location
    - General
  actor: user
  contexts:
    main:
      place: phone::setup
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/SetupActivity.kt
---

# Complete setup

## Trigger

The user finishes the initial choices.

## Outcome

The Product keeps the chosen initial preferences and returns to the main application.
