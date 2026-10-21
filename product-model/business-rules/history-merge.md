---
appliesTo:
- type: entity
  id: remembered-device
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/DeviceHistoryImport.kt#merge
---

# Import merges remembered addresses without adding their counts

For an existing address, import takes the earliest first sighting, latest last sighting and maximum counts. Favorite is retained if either input is starred. Existing nonempty own name and note win, and missing name, maker and type can be filled. Reimporting the same rows is idempotent.
