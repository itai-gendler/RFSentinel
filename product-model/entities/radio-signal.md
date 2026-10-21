---
domain: radio
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/RadioLog.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/sdr/RadioWatch.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
---

# Radio signal

A received RF transmission measurement on a monitored frequency.

## Information kept

- **Frequency** — Frequency and band.
- **Strength** — Signal above noise and movement trend.
- **Evidence** — Category, confidence and optional frequency label.
- **Time** — When the channel was heard.
