---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User holds the phone to an NFC tag the app has written while not working today
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
  - text: The Product finds an even number of time entries for today
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
    contexts:
      app:
        place: mobile-app
  - text: The Product records a time entry for today at the current time with the note NFC check-in
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
  - text: The Product shows Checked-in at with the time of the time entry and closes the app shortly after
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Time
    contexts:
      app:
        place: mobile-app
---

# Check in with an NFC tag

## Trigger

The User arrives at or leaves work and taps the tag instead of opening the app.

## Outcome

Today has a new check-in at the current time and the app has closed again.

## Edge cases

- Reopening the app from the recent apps after a tag tap records nothing further.
- If the entry cannot be recorded, nothing is recorded and the app stays open.
