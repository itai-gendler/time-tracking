---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens an earlier day that has a check-in without a check-out
    kind: actor
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Time
          - Kind
    contexts:
      app:
        place: mobile-app::day
  - text: The Product counts nothing for the open check-in on that earlier day while still counting the day's daily work hours against it
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Time
      - entity: work-hours-entry
        effect: reads
        facts:
          - Daily work hours
    contexts:
      app:
        place: mobile-app::day
  - text: The User adds an entry for that day at the time work ended and confirms
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::entry
  - text: The Product records the time entry for that day
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
        place: mobile-app::entry
  - text: The new time entry is the day's check-out and the session's time counts toward the Day Balance
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

# Add the check-out a day is missing

## Trigger

The User forgot to check out on an earlier day and its balance shows the whole target as missing.

## Outcome

The earlier day has a complete session and its balance, and every overall balance after it, reflect the worked time.
