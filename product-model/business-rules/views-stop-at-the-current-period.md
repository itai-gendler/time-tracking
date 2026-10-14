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
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# The views never move past the current day, week or month

The next arrow, swiping and the date picker stop at today, the current week or the current month, and Now is offered only while an earlier period is shown.
