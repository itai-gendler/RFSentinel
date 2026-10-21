---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The user finishes setup.
  kind: actor
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Setup complete
  capability: complete-setup
  actor: user
  contexts:
    main:
      place: phone::setup
- text: The Product starts listening after setup.
  kind: product
  entities:
  - entity: scan
    effect: changes
    from: Stopped
    to: Running
    facts:
    - Started by car
    - Receiver status
    - Started at
    - Active
  capability: start-scanning
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The user reviews the current observations.
  kind: actor
  entities:
  - entity: nearby-device
    effect: reads
    facts:
    - Address
    - Name
    - Vendor
    - Type
    - Sources
    - Signal
    - Evidence
    - Seen
    - Following
  capability: browse-nearby-devices
  actor: user
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/SetupActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
---

# Finish setup and see nearby devices

## Trigger

The user completes initial setup with scanning selected.

## Outcome

The user reaches the main view and can review the resulting observations.
