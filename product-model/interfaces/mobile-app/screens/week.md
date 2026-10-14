---
entities:
  - entity: time-entry
    shows:
      - Date
      - Time
      - Note
      - Late entry
      - Kind
references:
  - kind: code
    role: implementation
    target: src/screens/WeekView.tsx#WeekView
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# Week

The Week tab: one Monday-to-Sunday week, the current one by default, with its entries grouped by day, the week's worked time, the Week Balance and the Overall balance.
