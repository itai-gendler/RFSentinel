---
domain: external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/PcapRecorder.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Frame recording

A .pcap recording, for Wireshark, of every frame a USB WiFi adapter or V2X board hears, with its channel and signal.

## Information kept

- **Frames** — Received frame count and bytes.
- **File** — The current or newest capture file.
- **Stop reason** — Manual stop, scan ending, size limit or write failure.

## States

### Recording

Incoming frames are being saved.

### Stopped

Capture has ended and the file is available to share.
