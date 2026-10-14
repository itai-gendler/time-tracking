---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User swipes a time entry toward the left in a view
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
  - text: The Product asks whether to delete this session
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::day
  - text: The User confirms Delete
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::day
  - text: The Product deletes the time entry
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: removes
    contexts:
      app:
        place: mobile-app::day
  - text: Each later entry of that day moves up one place and switches between check-in and check-out
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

# Delete a time entry

## Trigger

An entry was recorded by mistake.

## Outcome

The entry is gone and the day's worked time and balances are recalculated; deleting a check-out reopens the session it closed.

## Edge cases

- Cancel keeps the entry.
