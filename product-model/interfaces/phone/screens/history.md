---
entities:
- entity: match-history
  shows:
  - Subject
  - Observation
  - Classification
  - Position
- entity: trace
  shows:
  - Name
  - Times
  - Route
  - Devices
  - Counts
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/HistoryActivity.kt
---

# History map & timeline

The history map and timeline: where flagged equipment showed up, and at what hour of the day and day of the week.
