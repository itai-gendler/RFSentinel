---
appliesTo:
- type: entity
  id: update
  effect: changes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateChecker.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateInstaller.kt
permits:
- actors:
  - user
  when:
  - entity: android-access
    fact: Install permission
    is: Granted
---

# Installing an update requires Android installation access

The local user can install the offered package after Android allows this application to request installation.
