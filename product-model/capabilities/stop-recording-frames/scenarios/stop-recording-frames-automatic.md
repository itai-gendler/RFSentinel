---
kind: edge
routes:
  main: Main
steps:
- text: The scan stops, capture reaches two hundred MiB, or a frame write fails.
  kind: condition
  entities:
  - entity: scan
    effect: reads
    facts: []
  unattended: true
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product closes the recording and exposes any automatic stop reason.
  kind: product
  entities:
  - entity: frame-recording
    effect: changes
    from: Recording
    to: Stopped
    facts:
    - Frames
    - Stop reason
  contexts:
    main:
      place: phone::settings-external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/usb/PcapRecorder.kt
---

# Stop recording frames when the scan stops, at 200 MB or on a failure

## Trigger

The scan stops, capture reaches two hundred MiB, or a frame write fails.

## Outcome

The Product closes the recording and exposes any automatic stop reason.
