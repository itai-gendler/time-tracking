---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User moves to an earlier week with the previous arrow, a swipe or the date picker
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::week
  - text: The Product lists that week's time entries and shows its worked time, the Week Balance and the Overall balance up to the end of that week
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
        place: mobile-app::week
  - text: The User taps Now to return to the current Monday-to-Sunday week
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::week
---

# View an earlier week

## Trigger

The User looks back at a past week.

## Outcome

The User has seen the past week's figures and is back on the current Monday-to-Sunday week.

## Edge cases

- Without entries the view shows No time entries this week.
- A swipe or date toward the future never goes past the current Monday-to-Sunday week.
