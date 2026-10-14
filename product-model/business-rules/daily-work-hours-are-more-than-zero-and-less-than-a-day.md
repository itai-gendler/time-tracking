---
appliesTo:
  - type: entity
    id: work-hours-entry
    effect: creates
    facts:
      - Daily work hours
  - type: entity
    id: work-hours-entry
    effect: changes
    facts:
      - Daily work hours
references:
  - kind: code
    role: implementation
    target: src/screens/settings/SettingsScreen.tsx#SettingsScreen
  - kind: code
    role: implementation
    target: src/utils/csv.ts#importFromCSV
---

# Daily work hours are more than zero and less than a day

Settings refuses a target of zero, and an imported work hours line is kept only when its daily work hours are above zero and below 24 hours.
