---
appliesTo:
- type: entity
  id: match-history
- type: entity
  id: trace
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/history/History.kt#encounters
---

# Encounter summaries merge continuous sightings

History summaries join sightings of one address while each consecutive gap is at most ten minutes. They retain the earliest available position and count the grouped encounter once in local-time summaries.
