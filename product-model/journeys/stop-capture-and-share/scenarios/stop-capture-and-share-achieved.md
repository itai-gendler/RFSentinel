---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The user stops capturing.
  kind: actor
  entities: []
  capability: stop-recording-frames
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The Product closes the recording and opens sharing.
  kind: product
  entities:
  - entity: frame-recording
    effect: changes
    from: Recording
    to: Stopped
    facts:
    - Stop reason
  capability: stop-recording-frames
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
- text: The user chooses a sharing destination.
  kind: actor
  entities:
  - entity: frame-recording
    effect: reads
    facts:
    - Frames
    - File
    - Stop reason
  capability: share-frame-recording
  actor: user
  contexts:
    main:
      place: phone::settings-external-hardware
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/settings/SettingsActivity.kt
---

# Stop a frame recording and share it

## Trigger

The user finishes a nonempty frame capture.

## Outcome

The closed capture is offered through Android sharing and a recipient can be chosen.
