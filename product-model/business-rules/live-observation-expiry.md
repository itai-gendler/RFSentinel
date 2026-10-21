---
appliesTo:
- type: entity
  id: nearby-device
- type: entity
  id: remembered-device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/LiveWindow.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/DeviceRegistry.kt
---

# Live range is shorter than retained history

A Bluetooth device is in range for 8 seconds after it was last heard, a WiFi device for one scan interval plus 10 seconds. An ordinary device stays in the live list for its configured time (30 s Bluetooth and 60 s WiFi by default), a flagged one while it is in range, and favorites and followers for three minutes; the device history keeps them for longer.
