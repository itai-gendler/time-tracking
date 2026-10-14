---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User chooses Export CSV in the menu
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
  - text: The Product writes the file time_tracking_export with today's date, holding every time entry newest first with its date, time, note and Late entry mark, followed by a work hours section with every work hours entry
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
          - Time
          - Note
          - Late entry
      - entity: work-hours-entry
        effect: reads
        facts:
          - Effective date
          - Daily work hours
    contexts:
      app:
        place: mobile-app
  - text: The Product opens the phone's share sheet with the file
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
  - text: The User sends or saves the file where they want it
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
---

# Export CSV

## Trigger

The User wants a report, a backup or to move to a new phone.

## Outcome

The User has a CSV file of the complete history that opens in a spreadsheet and imports back into the app.

## Edge cases

- Without work hours entries the file has no work hours section.
- If the file cannot be written, the Product says the export failed.
