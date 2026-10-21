---
kind: primary
routes:
  main: Main
steps:
- text: The user requests an update check.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::updates
- text: The Product reports the available newer release or that the application is up to date.
  kind: product
  entities:
  - entity: update
    effect: creates
    facts:
    - Version
    - Release notes
    - Package
    - Progress
  actor: user
  contexts:
    main:
      place: phone::updates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateChecker.kt
---

# Check for updates

## Trigger

The user requests an update check.

## Outcome

The Product reports the available newer release or that the application is up to date.

## Edge cases

- An unreachable release service produces a manual-check failure message.
- An edition signed by its alternative distributor directs updates through that distributor.
