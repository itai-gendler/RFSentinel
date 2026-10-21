---
appliesTo:
- type: entity
  id: tracker-ignore
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/TrackerMutes.kt
---

# Today-only and mine tracker ignores last differently

Ignore it today only covers the tracker's current address until that address changes, and at most 24 hours. It's mine keeps ignoring the tag with no end and follows it when its address changes, best effort; the app says so when the user chooses it.
