---
kind: primary
routes:
  main: Main
steps:
- text: The user selects a valid backup and chooses which sections to restore.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-data
- text: The Product replaces the selected supported choices and restarts with them.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Setup complete
    - General
    - Appearance
    - Scanning
    - Auto start
    - Detection
    - Alerts
    - Voice
    - Floating views
    - Follower alerts
    - Navigation
    - Map
    - Known cameras
    - Cell towers
    - External hardware
    - Radio
    - Location
    - Data
    - Alert mute
    - Snoozed until
    - Tracker warnings paused until
  - entity: watchlist-rule
    effect: changes
    facts:
    - Match
    - Label
    - Source
    - Score
    - Category
    - Custom
  - entity: place
    effect: changes
    facts:
    - Name
    - Address
    - Position
    - Saved as
  - entity: custom-theme
    effect: changes
    facts:
    - Name
    - Appearance
    - Font
    - Banner
    - Header
    - Marker
  actor: user
  contexts:
    main:
      place: phone::settings-data
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/SettingsBackup.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Restore settings

## Trigger

The user selects a valid backup and chooses which sections to restore.

## Outcome

The Product replaces the selected supported choices and restarts with them.

## Edge cases

- An invalid or unsupported backup is refused before applying its settings.
- A missing backed-up value within a selected section returns to its default.
- Live-export folder access and service consent choices must be established again.
