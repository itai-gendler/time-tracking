---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens the Day tab
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
        place: mobile-app::day
  - text: The Product lists the time entries of today in time order as check-ins and check-outs with the work or pause time between neighbours on the same day
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
        place: mobile-app::day
  - text: The Product shows the worked time, the Day Balance against the daily work hours of each day with a time entry, and the Overall balance up to the end of that day
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
        place: mobile-app::day
  - text: While a check-in has no check-out, the status reads Currently Working and the figures count up every minute; otherwise it reads Not Working
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

# View today

## Trigger

The User opens the app to see how the working day is going.

## Outcome

The User sees today's entries, worked time, Day Balance, Overall balance and working status.

## Edge cases

- Without entries today the view shows No time entries today.
- The next arrow and Now are unavailable here, and the date picker offers no later date.
