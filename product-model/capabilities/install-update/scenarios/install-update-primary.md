---
kind: primary
routes:
  main: Main
steps:
- text: The user chooses Install now on an offered update.
  kind: actor
  entities: []
  actor: user
  contexts:
    main:
      place: phone::updates
- text: The Product downloads the package and passes it to Android for installation while preserving local application
    data.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Progress
  actor: user
  contexts:
    main:
      place: phone::updates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateChecker.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateInstaller.kt
---

# Install update

## Trigger

The user chooses Install now on an offered update.

## Outcome

The Product downloads the package and passes it to Android for installation while preserving local application data.

## Edge cases

- The application explains required Android install access and continues after the user returns.
- Cancellation or failed download or installation is reported with a retry or release-page path.
- Scanning stops during installation.
