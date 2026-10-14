---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User long-presses the app icon and chooses Check-In / Out while not working today
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
  - text: The Product records a time entry for today at the current time with the note Quick check-in
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
  - text: The Product shows Checked-in at with the time of the time entry
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

# Check in with the app-icon quick action

## Trigger

The User wants to clock without opening the app.

## Outcome

Today has a new check-in at the current time and the app is open.

## Edge cases

- A shortcut dragged from the quick action to the home screen does the same.
- On iOS no message is shown.
