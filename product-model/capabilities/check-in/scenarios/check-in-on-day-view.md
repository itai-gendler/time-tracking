---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens the Day view on today while not working
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
  - text: The User taps Check In
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
  - text: The new time entry is the day's latest check-in and the status reads Currently Working
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

# Check in on the Day view

## Trigger

The User starts work and is on today's Day view.

## Outcome

Today has a new check-in at the current time. The worked time and balances count up every minute until the next check-out.

## Edge cases

- The Check In button is shown only on today; an earlier day offers adding an entry by hand instead.
