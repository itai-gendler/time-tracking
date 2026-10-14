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
    target: src/screens/WeekView.tsx#WeekView
  - kind: code
    role: implementation
    target: src/screens/MonthView.tsx#MonthView
---

# The Overall balance covers every day up to the end of the viewed day, week or month

The Overall figure in each view adds up the balance of every day from the first entry to the end of the viewed day, week or month, plus today's open session up to now.
