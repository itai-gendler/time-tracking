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
    target: src/utils/workHours.ts#sumDailyTargets
  - kind: code
    role: implementation
    target: src/db/database.ts#getOverallStats
---

# A balance expects the daily work hours only on days that have entries

The Day, Week, Month and Overall balances are the worked time minus the daily work hours of each day in the period that has at least one entry. Days without entries, such as weekends, holidays or sick days, add nothing, and a day with entries counts its whole target even when its session was never closed.
