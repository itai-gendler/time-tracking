---
appliesTo:
  - type: entity
    id: time-entry
    effect: changes
    facts:
      - Date
permits: []
references:
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# No one moves a recorded time entry to another date

Editing an entry changes its time, note and Late entry mark; an entry on the wrong day is deleted and added again on the right one.
