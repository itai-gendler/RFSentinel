---
appliesTo:
- type: entity
  id: requested-network
  effect: removes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/probes/ProbeListActivity.kt
permits:
- actors:
  - user
---

# The user clears requested networks

Clear requested networks removes every collected network name; names the user watches stay on the watchlist.
