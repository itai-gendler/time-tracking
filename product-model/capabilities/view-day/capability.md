---
domain: day
availability:
  - place: mobile-app
references:
  - kind: code
    role: implementation
    target: src/screens/DayView.tsx#DayView
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
  - kind: code
    role: implementation
    target: src/db/database.ts#getOverallStats
  - kind: doc
    role: intent
    target: README.md
    title: README
---

# View day

See one calendar day: its entries in time order as check-ins and check-outs with the work and pause time between them, the worked time, the Day Balance, the Overall balance up to that day and, on today, whether the User is currently working. The User moves between days with the arrows, a swipe or a date picker, and back to today with Now.
