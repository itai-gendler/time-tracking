---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User taps Add on the Day, Week or Month view
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::day
  - text: The Product opens Add Entry with the viewed date, the current time, an empty note and Late entry ticked
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::entry
  - text: The User picks a date up to today and a time, writes a note if wanted, and confirms
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::entry
  - text: The Product records the time entry with the chosen date, time, note and Late entry choice
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
  - text: The time entry takes its place among that day's entries in time order as a check-in or a check-out
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

# Add a time entry by hand

## Trigger

The User forgot to clock, or clocks for a day that has passed.

## Outcome

The day has the new entry, listed with "(Late Entry)" when marked, and its worked time and balances include it.

## Edge cases

- A date after today cannot be picked; a later date reaching the form is replaced by today.
- Cancel closes Add Entry without recording anything.
- An entry placed between existing ones switches every later entry of that day between check-in and check-out.
