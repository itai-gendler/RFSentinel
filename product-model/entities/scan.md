---
singleton: true
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/service/ScanForegroundService.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/rfsentinel/app/receiver/CarAutoStart.kt
---

# Scan

The phone's scanning session: the radios and receivers it listens with, and whether it runs. It keeps running in the background with its notification until stopped.

## Information kept

- **Started by car** — Whether car auto-start owns this run.
- **Receiver status** — Enabled receivers, listening state, last observations and restart notices.
- **Started at** — Start of the current scanning session.
- **Active** — Whether receiver work is running.

## States

### Stopped

No scan is running.

### Running

The enabled receivers are listening.
