---
kind: alternate
routes:
  main: Main
steps:
- text: An enabled receiver stops returning observations during a running scan.
  kind: condition
  unattended: true
  entities:
  - entity: scan
    effect: reads
    facts:
    - Active
    - Receiver status
  contexts:
    main:
      place: phone::nearby
- text: The Product restarts that receiver within the existing session and reports recovery when observations resume.
  kind: product
  entities:
  - entity: scan
    effect: changes
    facts:
    - Receiver status
  contexts:
    main:
      place: phone::nearby
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Recover a quiet receiver

## Trigger

An enabled receiver stops returning observations during a running scan.

## Outcome

The Product restarts that receiver within the existing session and reports recovery when observations resume.

## Edge cases

- Bluetooth recovery waits while the screen is off or the adapter is off.
- Repeated silence increases the interval between recovery attempts; receiving data resets it.
- WiFi recovery accounts for the configured scan interval.
