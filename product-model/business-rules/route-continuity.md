---
appliesTo:
- type: entity
  id: route
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/nav/Navigator.kt
---

# Failed replanning keeps the current route

A failed replacement request leaves the old guidance path available, reports the failure and increases the wait before another attempt. A response from navigation that ended or was replaced is not adopted.
