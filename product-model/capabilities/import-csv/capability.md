---
domain: data
availability:
  - place: mobile-app
references:
  - kind: code
    role: implementation
    target: src/utils/csv.ts#importFromCSV
  - kind: code
    role: implementation
    target: src/db/database.ts#importEvents
  - kind: code
    role: implementation
    target: src/db/database.ts#importWorkHours
  - kind: code
    role: implementation
    target: src/components/MenuDrawerContent.tsx#MenuDrawerContent
  - kind: doc
    role: intent
    target: README.md
    title: README
---

# Import CSV

Read a CSV file in the app's export format, from Import CSV in the menu, and add its time entries and work hours entries to the ones already kept.
