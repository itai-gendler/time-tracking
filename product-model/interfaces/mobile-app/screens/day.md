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
    target: src/screens/DayView.tsx#DayView
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# Day

The Day tab: one calendar day, today by default, with its entries in time order, the work and pause time between them, the worked time, the Day Balance, the Overall balance and, on today, the working status with the Check In or Check Out button.
