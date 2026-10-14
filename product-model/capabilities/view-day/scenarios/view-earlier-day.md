---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User moves to an earlier day with the previous arrow, a swipe or the date picker
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::day
  - text: The Product lists that day's time entries and shows its worked time, the Day Balance and the Overall balance up to the end of that day
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
          - Time
          - Kind
      - entity: work-hours-entry
        effect: reads
        facts:
          - Effective date
          - Daily work hours
    contexts:
      app:
        place: mobile-app::day
  - text: An earlier day offers no Check In or Check Out and shows no working status; a check-in without a check-out counts no time
    kind: condition
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Kind
    contexts:
      app:
        place: mobile-app::day
  - text: The User taps Now to return to today
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::day
---

# View an earlier day

## Trigger

The User looks back at a past day.

## Outcome

The User has seen the past day's figures and is back on today.

## Edge cases

- Without entries the view shows No time entries for this day.
- A swipe or date toward the future never goes past today.
