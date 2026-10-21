---
kind: primary
routes:
  main: Main
steps:
- text: The user starts a frame capture while scanning.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product opens a new recording and accumulates received frames with channel and signal information.
  kind: product
  entities:
  - entity: frame-recording
    effect: creates
    to: Recording
    facts:
    - Frames
    - File
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

# Record frames

## Trigger

The user starts a frame capture while scanning.

## Outcome

The Product opens a new recording and accumulates received frames with channel and signal information.

## Edge cases

- A file-creation failure is reported without starting the capture.
