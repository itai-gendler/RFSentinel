---
appliesTo:
- type: entity
  id: update
  effect: creates
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/UpdateChecker.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/util/Prefs.kt
permits:
- actors:
  - user
- unattended: true
  when:
  - entity: preferences
    fact: General
    is: Automatic update checks enabled
---

# The automatic update check follows its selected setting

Check for updates runs whenever the user asks. The automatic check is off by default; when it is on, it runs as the app comes to the front, at most every six hours (thirty minutes after a check that could not reach GitHub), and says something only when a newer release is out.
