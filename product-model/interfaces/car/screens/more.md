---
entities:
- entity: preferences
  shows:
  - Alert mute
  - Snoozed until
  - Voice
  - Detection
  - Tracker warnings paused until
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
  target: app/src/main/java/com/rfsentinel/app/car/MoreScreen.kt
---

# More

More on the car screen: snooze, spoken alerts, short spoken alerts, whether AirTags count as trackers, cell towers and hardware.
