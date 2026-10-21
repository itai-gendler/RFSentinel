---
kind: primary
routes:
  main: Main
steps:
- text: The user restores normal tracker warnings.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-trackers-and-followers
- text: The Product clears the pause and all stored tracker ignore choices.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Tracker warnings paused until
  - entity: tracker-ignore
    effect: removes
  actor: user
  contexts:
    main:
      place: phone::settings-trackers-and-followers
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Resume tracker warnings

## Trigger

The user restores normal tracker warnings.

## Outcome

The Product clears the pause and all stored tracker ignore choices.
