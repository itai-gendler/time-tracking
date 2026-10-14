---
appliesTo:
  - type: capability
    id: export-csv
  - type: capability
    id: import-csv
references:
  - kind: code
    role: implementation
    target: src/utils/csv.ts#exportToCSV
  - kind: code
    role: implementation
    target: src/utils/csv.ts#importFromCSV
---

# An exported file holds the whole history and imports back unchanged

The export holds every time entry with its date, time, note and Late entry mark, and every work hours entry, in a layout the import reads back; notes keep their commas, quotes and line breaks. Files from app versions without work hours import as before.
