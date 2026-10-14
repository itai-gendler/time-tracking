---
domain: settings
references:
  - kind: code
    role: implementation
    target: src/utils/workHours.ts#WorkHoursEntry
  - kind: code
    role: implementation
    target: src/db/database.ts#setDailyTargetMinutes
  - kind: doc
    role: context
    target: metadata/en-US/changelogs/241.txt
    title: 'Release notes: different working hours'
---

# Work hours entry

The daily work-hours target from one date onward. Every change of the daily work hours is kept as its own entry, so earlier days keep the target that applied to them; the CSV import and export call them "work hours entries".

## Information kept

- **Effective date** — the first day the target applies to; there is at most one entry per date
- **Daily work hours** — the hours and minutes expected on each day with entries from the effective date on
