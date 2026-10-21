---
appliesTo:
- type: entity
  id: frame-recording
  effect: changes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/PcapRecorder.kt
permits:
- actors:
  - user
- unattended: true
---

# The user, the end of the scan or a limit stops a frame recording

A frame recording stops when the user stops it, when scanning stops, when writing fails or when it reaches 200 MB.
