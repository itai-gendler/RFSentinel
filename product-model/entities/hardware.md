---
domain: external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/UsbWifi.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/esp/EspBoards.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/SdrRadio.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# External receiver

An ESP32 board, USB WiFi adapter, or RTL-SDR or HackRF dongle connected to the phone, or an OUI-SPY board paired over Bluetooth, with its status.

## Information kept

- **Kind** — Supported USB WiFi, ESP32, Bluetooth board or SDR receiver.
- **Status** — Waiting for access, firmware, receiving, disconnected or failed status.
- **Observations** — Reports and frames received.
- **Firmware** — Whether the selected USB adapter needs its chip firmware.
