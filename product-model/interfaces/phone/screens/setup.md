---
entities:
- entity: preferences
  shows:
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
- entity: android-access
  shows:
  - Scan permission
  - Location permission
  - Notification permission
  - Nearby WiFi permission
  - Overlay permission
  - USB permission
  - Bluetooth connection permission
  - Car map support
  - Install permission
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/SetupActivity.kt
---

# Setup

Initial choices, permission status and completion of setup.
