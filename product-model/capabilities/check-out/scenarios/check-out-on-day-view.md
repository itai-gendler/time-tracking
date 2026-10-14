---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens the Day view on today while working
    kind: actor
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Kind
    contexts:
      app:
        place: mobile-app::day
  - text: The User taps Check Out
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::day
  - text: The Product records a time entry for today at the current time, with no note and not marked as a late entry
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
        place: mobile-app::day
  - text: The new time entry is the day's latest check-out and the status reads Not Working
    kind: condition
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Kind
    contexts:
      app:
        place: mobile-app::day
---

# Check out on the Day view

## Trigger

The User stops work and is on today's Day view.

## Outcome

Today has a new check-out at the current time. The session's worked time is fixed and added to the day, week, month and overall figures.

## Edge cases

- The Check Out button is shown only on today; an earlier day offers adding an entry by hand instead.
