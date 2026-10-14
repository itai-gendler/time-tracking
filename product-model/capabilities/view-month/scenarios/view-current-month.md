---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens the Month tab
    kind: actor
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
          - Time
          - Note
          - Late entry
          - Kind
    contexts:
      app:
        place: mobile-app::month
  - text: The Product lists the time entries of the current month in time order as check-ins and check-outs with the work or pause time between neighbours on the same day
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
          - Time
          - Kind
    contexts:
      app:
        place: mobile-app::month
  - text: The Product shows the worked time, the Month Balance against the daily work hours of each day with a time entry, and the Overall balance up to the end of that month
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
          - Time
      - entity: work-hours-entry
        effect: reads
        facts:
          - Effective date
          - Daily work hours
    contexts:
      app:
        place: mobile-app::month
  - text: An open check-in of today counts up to now in the worked time and both balances
    kind: condition
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Kind
    contexts:
      app:
        place: mobile-app::month
---

# View the current month

## Trigger

The User wants to know how the current month stands against the target.

## Outcome

The User sees the month's entries, worked time, Month Balance and Overall balance.

## Edge cases

- Without entries the view shows No time entries this month.
- The next arrow and Now are unavailable here, and the date picker offers no later date.
