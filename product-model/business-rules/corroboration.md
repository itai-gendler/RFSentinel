---
appliesTo:
- type: entity
  id: nearby-device
references:
- kind: spec
  role: intent
  target: docs/SIGNATURES.md
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/EvidenceFusion.kt#fuse
---

# Corroboration does not count the same clue twice

Fusion supports the strongest non-patrol match only with distinct labels in the same category scoring at least 30. Supporting confidence is discounted by half, combined using noisy-OR and capped at 90; a stronger original score is retained. Patrol grouping neither corroborates nor is corroborated by its source matches.
