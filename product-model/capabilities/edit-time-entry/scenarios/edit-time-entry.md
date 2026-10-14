---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User swipes a time entry toward the right in a view
    kind: actor
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Time
          - Note
          - Kind
    contexts:
      app:
        place: mobile-app::day
  - text: The Product opens Edit Entry with the time entry's time, note and Late entry mark
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Time
          - Note
          - Late entry
    contexts:
      app:
        place: mobile-app::entry
  - text: The User changes the time, the note or the Late entry mark and confirms
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::entry
  - text: The Product saves the time entry with the new time, note and Late entry mark on its original date
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: changes
        facts:
          - Time
          - Note
          - Late entry
    contexts:
      app:
        place: mobile-app::entry
---

# Edit a time entry

## Trigger

An entry was recorded at the wrong time or needs a note.

## Outcome

The entry shows the new values on the same day, and the worked time and balances follow.

## Edge cases

- Cancel closes Edit Entry and leaves the entry as it was.
- Moving the time past a neighbouring entry reorders the day and can switch entries between check-in and check-out.
