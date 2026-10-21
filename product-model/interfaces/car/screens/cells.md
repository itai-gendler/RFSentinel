---
entities:
- entity: cell-tower
  shows:
  - Identity
  - Serving
  - Signal
  - Seen
  - Position
  - Warning
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/car/CellsScreen.kt
---

# Cell towers

The fake cell tower check status, the serving cell and its neighbours, on the car screen.
