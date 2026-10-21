---
entities:
- entity: nearby-device
  shows:
  - Address
  - Name
  - Vendor
  - Type
  - Sources
  - Signal
  - Evidence
  - Seen
  - Following
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/NearbyDevicesScreen.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/DeviceListScreen.kt
---

# Nearby devices

Nearby devices on the car screen with the phone's filters and live counts; each row says which radio heard it.
