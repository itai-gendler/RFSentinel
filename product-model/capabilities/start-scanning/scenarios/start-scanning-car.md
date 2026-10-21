---
kind: alternate
routes:
  main: Main
steps:
- text: The user requests scanning from the car.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: car::home
- text: The Product starts the enabled receivers and reports when the phone screen limits Bluetooth reception.
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
  target: app/src/main/java/com/rfsentinel/app/util/Permissions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/HomeScreen.kt
---

# Start scanning from Android Auto

## Trigger

The user requests scanning from the car.

## Outcome

The Product starts the enabled receivers and reports when the phone screen limits Bluetooth reception.

## Edge cases

- A missing permission is requested on the phone; the car directs the user there if the host cannot show the request.
