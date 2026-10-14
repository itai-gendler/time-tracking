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
    target: src/screens/MonthView.tsx#MonthView
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# Month

The Month tab: one calendar month, the current one by default, with its entries grouped by day, the month's worked time, the Month Balance and the Overall balance.
