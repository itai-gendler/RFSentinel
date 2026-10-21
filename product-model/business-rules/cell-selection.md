---
appliesTo:
- type: entity
  id: cell-tower
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
permits:
- unattended: true
  when:
  - entity: preferences
    fact: Cell checks enabled
    is: true
---

# Fake cell tower checks run only while their category is on

While scanning, the cell information Android exposes is checked for fake cell tower signs every 15 seconds, only while that category is on in What to detect.
