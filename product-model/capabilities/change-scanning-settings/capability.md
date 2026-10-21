---
availability:
- place: phone
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
---

# Change scanning settings

Change the Scanning section of Settings: Bluetooth and WiFi scanning, Bluetooth intensity, the WiFi interval, scanning in the background, how long an ordinary device stays in the list after it was last heard (30 s Bluetooth and 60 s WiFi by default) and hiding trusted devices. A running scan picks up the changes.
