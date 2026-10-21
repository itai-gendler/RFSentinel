---
appliesTo:
- type: entity
  id: route
- type: entity
  id: scan
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt#startScanToo
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/receiver/CarAutoStart.kt
---

# Guidance and scanning have independent endings

Guidance may start a local scan when its setting and access allow it. Failure to start scanning does not prevent guidance, and arrival or Stop guidance does not stop that scan. Car disconnection stops only a scan started by car auto-start.
