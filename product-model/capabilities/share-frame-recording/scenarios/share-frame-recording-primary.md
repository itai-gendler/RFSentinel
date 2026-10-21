---
kind: primary
routes:
  main: Main
steps:
- text: The user asks to share the capture.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product supplies the recorded file for sharing.
  kind: product
  entities:
  - entity: frame-recording
    effect: reads
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
---

# Share frame recording

## Trigger

The user asks to share the capture.

## Outcome

The Product supplies the recorded file for sharing.

## Edge cases

- A recording with no received frames reports that nothing was recorded.
