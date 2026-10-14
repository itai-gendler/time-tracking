---
entities:
  - entity: time-entry
    shows:
      - Date
      - Time
      - Note
      - Late entry
    collects:
      - Date
      - Time
      - Note
      - Late entry
references:
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# Entry

Where one time entry is added ("Add Entry") or edited ("Edit Entry"), opened from the Day, Week or Month view. The date is chosen only when adding.
