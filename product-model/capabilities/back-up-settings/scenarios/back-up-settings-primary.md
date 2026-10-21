---
kind: primary
routes:
  main: Main
steps:
- text: The user selects a destination for the backup.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-data
- text: The Product writes the settings, watchlist rules, Home, Work and starred places, floating-window positions and custom themes to the chosen file, leaving out API keys and the I accept the risk choices.
  kind: product
  entities:
  - entity: preferences
    effect: reads
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
    effect: reads
    facts:
    - Match
    - Label
    - Source
    - Score
    - Category
    - Custom
  - entity: place
    effect: reads
    facts:
    - Name
    - Address
    - Position
    - Saved as
  - entity: custom-theme
    effect: reads
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

# Back up settings

## Trigger

The user selects a destination for the backup.

## Outcome

The Product writes the settings, watchlist rules, Home, Work and starred places, floating-window positions and custom themes to the chosen file, leaving out API keys and the I accept the risk choices.

## Edge cases

- Secrets, consent acknowledgments and short-lived state are not included.
- Detections, remembered devices and traces use their separate exports.
