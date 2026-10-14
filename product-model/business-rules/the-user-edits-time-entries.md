---
appliesTo:
  - type: entity
    id: time-entry
    effect: changes
permits:
  - actors:
      - user
references:
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# The User edits any time entry the app keeps

Every entry belongs to the one User of the installation, whichever way it was recorded, so the User may change its time, note and Late entry mark.
