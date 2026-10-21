---
appliesTo:
- type: entity
  id: frame-recording
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
permits:
- actors:
  - user
  when:
  - entity: scan
    fact: Active
    is: true
---

# Frame recording starts only during scanning

Record frames saves every frame the USB WiFi adapter or V2X board hears, with its channel and signal, and starts only while a scan is running.
