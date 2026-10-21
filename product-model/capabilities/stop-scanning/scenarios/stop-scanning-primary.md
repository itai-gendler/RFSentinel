---
kind: primary
routes:
  main: Main
steps:
- text: The user stops listening from the application, system tile or service notification.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::nearby
- text: The Product stops receiver work and leaves the local scan stopped.
  kind: product
  entities:
  - entity: scan
    effect: changes
    from: Running
    to: Stopped
    facts:
    - Receiver status
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
---

# Stop scanning

## Trigger

The user stops listening from the application, system tile or service notification.

## Outcome

The Product stops receiver work and leaves the local scan stopped.
