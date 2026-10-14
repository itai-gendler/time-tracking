---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User moves to an earlier month with the previous arrow, a swipe or the date picker
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::month
  - text: The Product lists that month's time entries and shows its worked time, the Month Balance and the Overall balance up to the end of that month
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
        place: mobile-app::month
  - text: The User taps Now to return to the current month
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::month
---

# View an earlier month

## Trigger

The User looks back at a past month.

## Outcome

The User has seen the past month's figures and is back on the current month.

## Edge cases

- Without entries the view shows No time entries this month.
- A swipe or date toward the future never goes past the current month.
