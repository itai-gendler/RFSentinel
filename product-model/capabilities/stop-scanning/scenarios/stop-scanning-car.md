---
kind: alternate
routes:
  main: Main
steps:
- text: The user chooses Stop in the car.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::home
- text: The Product ends the running receivers.
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
      place: car::home
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/HomeScreen.kt
---

# Stop scanning from Android Auto

## Trigger

The user chooses Stop in the car.

## Outcome

The Product ends the running receivers.
