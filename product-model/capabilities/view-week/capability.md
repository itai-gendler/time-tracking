---
availability:
  - place: mobile-app
references:
  - kind: code
    role: implementation
    target: src/screens/WeekView.tsx#WeekView
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

# View week

See one Monday-to-Sunday week: its entries grouped by day, the week's worked time, the Week Balance and the Overall balance up to the end of that week. The User moves between weeks with the arrows, a swipe or a date picker, and back to the current week with Now.
