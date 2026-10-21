---
kind: primary
routes:
  main: Main
steps:
- text: The user stops frame capture.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product closes the recording and offers the nonempty result for sharing.
  kind: product
  entities:
  - entity: frame-recording
    effect: changes
    from: Recording
    to: Stopped
    facts:
    - Frames
    - Stop reason
  actor: user
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

# Stop recording frames

## Trigger

The user stops frame capture.

## Outcome

The Product closes the recording and offers the nonempty result for sharing.
