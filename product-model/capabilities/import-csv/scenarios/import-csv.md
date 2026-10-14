---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User chooses Import CSV in the menu and picks a CSV file
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
  - text: The Product adds a time entry for every row with a date and a time, keeping its note and Late entry mark
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: creates
        facts:
          - Date
          - Time
          - Note
          - Late entry
    contexts:
      app:
        place: mobile-app
  - text: The Product adds a work hours entry for every line of the work hours section whose daily work hours lie between 0 and 24 hours
    kind: product
    actor: user
    entities:
      - entity: work-hours-entry
        effect: creates
        facts:
          - Effective date
          - Daily work hours
    contexts:
      app:
        place: mobile-app
  - text: The Product says how many events and work hours entries it imported
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
---

# Import CSV

## Trigger

The User restores a backup or moves history from another phone.

## Outcome

The imported entries appear in the views beside those already kept, and balances use the imported work hours.

## Edge cases

- An imported work hours entry replaces the one already kept for the same effective date.
- Rows without a time and work hours lines outside the range are skipped.
- Importing the same file again adds its time entries a second time.
- Closing the file picker imports nothing and shows no message.
- If the file cannot be read, the Product says the import failed.
