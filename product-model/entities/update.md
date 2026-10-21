---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateChecker.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateInstaller.kt
---

# Application update

A release discovered by the application’s update check.

## Information kept

- **Version** — Available version and current installed version.
- **Release notes** — The release information offered for review.
- **Package** — A compatible release artifact when offered.
- **Progress** — Check, download and installation outcome.
