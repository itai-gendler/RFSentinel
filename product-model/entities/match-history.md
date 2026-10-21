---
domain: history
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/data/DetectionEntity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/ui/DetectionLogActivity.kt
---

# Match history

The match log: each flagged device, cell warning or other match as it was logged, with its evidence, time and, when GPS tagging is on, position.

## Information kept

- **Subject** — Observed address or source-specific subject.
- **Observation** — Time, source and signal when applicable.
- **Classification** — Label, category, score and evidence.
- **Position** — Saved observation or reported location when GPS tagging permits it.
