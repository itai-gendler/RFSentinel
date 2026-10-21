---
entities:
- entity: match-history
  shows:
  - Subject
  - Observation
  - Classification
  - Position
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DetectionLogActivity.kt
---

# Match history

The match log: every logged match, searchable, filtered to today or by kind, with its evidence, time and saved position.
