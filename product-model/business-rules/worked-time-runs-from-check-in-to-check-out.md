---
appliesTo:
  - type: capability
    id: view-day
  - type: capability
    id: view-week
  - type: capability
    id: view-month
references:
  - kind: code
    role: implementation
    target: src/db/database.ts#getOverallStats
  - kind: code
    role: implementation
    target: src/screens/DayView.tsx#DayView
---

# Worked time is the time from each check-in to the next check-out on the same day

A day's worked time adds up each check-in to its following check-out; the time between a check-out and the next check-in is a pause. An open check-in counts up to now only on today; on an earlier day it counts nothing.
