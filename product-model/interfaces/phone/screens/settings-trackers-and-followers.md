---
entities:
- entity: preferences
  shows:
  - Follower alerts
  - Tracker warnings paused until
  - Follower warnings enabled
  collects:
  - Follower alerts
  - Follower warnings enabled
- entity: tracker-ignore
  shows:
  - Address
  - Kind
  - Mode
  - Until
  - Last heard
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Trackers & followers

The Trackers & followers section of Settings: follower warnings and their time and distance.
