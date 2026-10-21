---
singleton: true
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Permissions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/HomeScreen.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/UsbWifi.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateInstaller.kt
---

# Android access

The Android permissions and host support available to this installation.

## Information kept

- **Scan permission** — Required location and applicable Bluetooth scan access.
- **Location permission** — Precise location access.
- **Notification permission** — Permission to show Android notifications.
- **Nearby WiFi permission** — Nearby WiFi access on versions that require it.
- **Overlay permission** — Permission to display floating views over other apps.
- **USB permission** — Access to the attached receiver.
- **Bluetooth connection permission** — Access to paired Bluetooth devices and board connections.
- **Car map support** — The car host supports the live map surface.
- **Install permission** — Android allows this application to request package installation.
