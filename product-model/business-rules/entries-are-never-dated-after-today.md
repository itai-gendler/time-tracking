---
appliesTo:
  - type: entity
    id: time-entry
    effect: creates
    facts:
      - Date
references:
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
  - kind: doc
    role: context
    target: metadata/en-US/changelogs/242.txt
    title: Release notes
---

# A time entry is never added on a date after today

The date picker for a new entry offers no later date, and a later date that reaches the form is replaced by today.
