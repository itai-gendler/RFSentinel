---
appliesTo:
- type: entity
  id: scan
  effect: changes
  to: Running
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Permissions.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/HomeScreen.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/receiver/BootReceiver.kt
permits:
- actors:
  - user
  when:
  - entity: android-access
    fact: Scan permission
    is: Granted
- unattended: true
  when:
  - entity: android-access
    fact: Scan permission
    is: Granted
---

# Scanning starts with the required Android access

The user or an enabled automatic start can start listening only with the Android access required for scanning. Optional notification access is independent.
