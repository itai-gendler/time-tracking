---
appliesTo:
  - type: capability
    id: import-csv
  - type: entity
    id: work-hours-entry
    effect: creates
references:
  - kind: code
    role: implementation
    target: src/db/database.ts#importEvents
  - kind: code
    role: implementation
    target: src/db/database.ts#importWorkHours
---

# An import adds time entries beside the kept ones and replaces work hours entries of the same date

Imported time entries never replace, merge with or skip entries already kept, so importing a file twice keeps its entries twice. A work hours entry for a date that already has one replaces it, and setting the daily work hours twice on one day does the same.
