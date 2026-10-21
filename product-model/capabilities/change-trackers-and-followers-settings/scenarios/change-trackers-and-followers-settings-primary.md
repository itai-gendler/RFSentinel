---
kind: primary
routes:
  main: Main
steps:
- text: The user changes one of the section's choices.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-trackers-and-followers
- text: The Product saves the change at once and applies it from then on.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Follower alerts
    - Follower warnings enabled
  actor: user
  contexts:
    main:
      place: phone::settings-trackers-and-followers
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Change trackers & followers settings

## Trigger

The user changes a choice in the Trackers & followers section of Settings.

## Outcome

The Product saves the change at once and applies it from then on.
