---
appliesTo:
- type: entity
  id: nearby-device
- type: entity
  id: match-history
references:
- kind: spec
  role: intent
  target: docs/SIGNATURES.md
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/Category.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/detect/EvidenceFusion.kt
---

# Confidence describes matching evidence

Weak is below 50, probable is 50–79 and strong is 80 or above. These tiers describe the supporting signature evidence, never proof of a person, ownership or intent.
