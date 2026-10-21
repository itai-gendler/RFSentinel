---
kind: alternate
routes:
  main: Main
steps:
- text: The application returns to the foreground and an automatic release check is due.
  kind: condition
  unattended: true
  entities: []
  contexts:
    main:
      place: phone::updates
- text: The Product checks the latest release and offers a newer version when one is available.
  kind: product
  entities:
  - entity: update
    effect: creates
    facts:
    - Version
    - Release notes
    - Package
    - Progress
  contexts:
    main:
      place: phone::updates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateChecker.kt
---

# Check updates on startup

## Trigger

The application returns to the foreground and an automatic release check is due.

## Outcome

The Product checks the latest release and offers a newer version when one is available.

## Edge cases

- Automatic checks normally wait six hours between attempts and remain quiet for no update or failure.
- A failed check becomes eligible for retry after thirty minutes.
