---
appliesTo:
  - type: entity
    id: work-hours-entry
  - type: capability
    id: view-day
  - type: capability
    id: view-week
  - type: capability
    id: view-month
references:
  - kind: code
    role: implementation
    target: src/utils/workHours.ts#resolveDailyTarget
  - kind: code
    role: implementation
    target: src/utils/workHours.ts#DEFAULT_DAILY_TARGET_MINUTES
---

# Each day uses the daily work hours in effect on that day

A day's target is the daily work hours of the latest work hours entry effective on or before it, and 8 hours when there is none. A change made today therefore leaves every earlier day's balance as it was.
