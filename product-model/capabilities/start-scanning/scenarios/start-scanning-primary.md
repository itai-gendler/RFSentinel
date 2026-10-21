---
kind: primary
routes:
  main: Main
steps:
- text: The user requests scanning.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The Product starts a fresh local session, clears the previous live observations and shows the enabled receiver
    status.
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
  actor: user
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Permissions.kt
---

# Start scanning

## Trigger

The user requests scanning.

## Outcome

The Product starts a fresh local session, clears the previous live observations and shows the enabled receiver status.

## Edge cases

- If Android refuses the service start, the application reports that scanning could not start.
- Turning Bluetooth off stops that receiver; turning it on while scanning restarts it.
- The scan tile opens the phone application for permissions when they are missing.
